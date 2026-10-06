# 03 · IAM: cenários de laboratório e diagnóstico

16 cartões · primeira edição · 05/10/2026.


## SAA-03-001-C001

**Objetivo:** Diagnosticar AccessDenied em uma chamada a serviço

**Pergunta:** Uma API retorna AccessDenied. Qual contexto verificar antes de ampliar permissões?

**Resposta:** O principal efetivo, a ação, o recurso e as políticas aplicáveis.

**Saiba mais:** A aplicação pode estar usando uma role diferente daquela imaginada.

**Fonte:** [Troubleshoot access denied error messages - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/troubleshoot_access-denied.html)


## SAA-03-001-C002

**Objetivo:** Diagnosticar AccessDenied em uma chamada a serviço

**Pergunta:** Uma policy permite acesso, mas há Deny explícito por condição satisfeita. Qual correção conceitual é necessária?

**Resposta:** Corrigir a condição ou o bloqueio conforme a intenção de segurança.

**Saiba mais:** Adicionar outro Allow não supera a negação explícita.

**Fonte:** [Troubleshoot access denied error messages - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/troubleshoot_access-denied.html)


## SAA-03-002-C001

**Objetivo:** Interpretar role de EC2 para leitura de um bucket

**Pergunta:** Uma EC2 usa uma role com GetObject, mas o SDK utiliza chaves fixas configuradas no ambiente. Qual identidade pode estar fazendo a chamada?

**Resposta:** A identidade das chaves fixas, conforme a cadeia de obtenção de credenciais.

**Saiba mais:** A mera associação da role não apaga credenciais configuradas pela aplicação.

**Fonte:** [IAM roles for Amazon EC2 - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html)


## SAA-03-002-C002

**Objetivo:** Interpretar role de EC2 para leitura de um bucket

**Pergunta:** Por que testar leitura de um objeto não comprova permissão de listar o bucket?

**Resposta:** Ler objeto e listar bucket são operações e recursos de autorização diferentes.

**Saiba mais:** Separar s3:GetObject de s3:ListBucket ao diagnosticar.

**Fonte:** [IAM roles for Amazon EC2 - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html)


## SAA-03-003-C001

**Objetivo:** Identificar trust policy incorreta em acesso entre contas

**Pergunta:** A origem tem sts:AssumeRole, mas a role de destino não confia nela. O que revisar?

**Resposta:** A trust policy do destino.

**Saiba mais:** A permissão na origem não estabelece a confiança na outra conta.

**Fonte:** [IAM tutorial: Delegate access across AWS accounts using IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html)


## SAA-03-003-C002

**Objetivo:** Identificar trust policy incorreta em acesso entre contas

**Pergunta:** AssumeRole funciona, mas GetObject falha após a troca. Qual etapa passou e qual ainda precisa de revisão?

**Resposta:** A assunção passou; o acesso ao recurso da sessão precisa ser revisado.

**Saiba mais:** Não confundir autorização para assumir a role com autorização para todas as ações.

**Fonte:** [IAM tutorial: Delegate access across AWS accounts using IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html)


## SAA-03-004-C001

**Objetivo:** Verificar quando uma SCP limita uma permissão IAM

**Pergunta:** Um administrador de conta membro é impedido por SCP de executar uma ação. Anexar outra política administrativa resolve?

**Resposta:** Não.

**Saiba mais:** É necessário revisar o guardrail organizacional com a autoridade adequada.

**Fonte:** [Service control policies (SCPs) - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)


## SAA-03-004-C002

**Objetivo:** Verificar quando uma SCP limita uma permissão IAM

**Pergunta:** Uma SCP com Allow concede acesso a uma role sem política de permissão?

**Resposta:** Não.

**Saiba mais:** SCPs limitam o conjunto de permissões possíveis; não são a concessão de acesso.

**Fonte:** [Service control policies (SCPs) - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)


## SAA-03-005-C001

**Objetivo:** Diagnosticar condição MFA ou tag que bloqueia acesso

**Pergunta:** Uma policy depende de tag de recurso e só alguns recursos falham. O que comparar?

**Resposta:** As tags e os valores efetivamente usados na condição.

**Saiba mais:** A mesma ação pode ter decisões diferentes conforme os atributos do recurso.

**Fonte:** [IAM JSON policy elements: Condition - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html)


## SAA-03-005-C002

**Objetivo:** Diagnosticar condição MFA ou tag que bloqueia acesso

**Pergunta:** Uma chamada automatizada falha sob uma condição MFA. Por que não basta verificar apenas a senha do usuário?

**Resposta:** A avaliação usa o contexto da requisição e das credenciais.

**Saiba mais:** A condição precisa ser adequada ao tipo de sessão que a aplicação utiliza.

**Fonte:** [IAM JSON policy elements: Condition - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html)


## SAA-03-006-C001

**Objetivo:** Substituir access key embutida por credencial temporária

**Pergunta:** Uma aplicação lê chaves AWS de um arquivo na EC2. Qual migração reduz gestão de segredos estáticos?

**Resposta:** Associar uma role apropriada e usar o provedor de credenciais do SDK.

**Saiba mais:** Remover as chaves antigas do código e revogar credenciais desnecessárias faz parte da migração.

**Fonte:** [Security best practices in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)


## SAA-03-006-C002

**Objetivo:** Substituir access key embutida por credencial temporária

**Pergunta:** Por que copiar credenciais temporárias manualmente para um arquivo não é uma solução duradoura?

**Resposta:** Elas expiram e precisam de renovação.

**Saiba mais:** Usar o mecanismo de obtenção e renovação apropriado ao ambiente.

**Fonte:** [Security best practices in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)


## SAA-03-007-C001

**Objetivo:** Avaliar evidência de acesso público ou externo indesejado

**Pergunta:** Um achado de acesso externo significa necessariamente invasão ocorrida?

**Resposta:** Não. Pode indicar uma possibilidade de acesso configurada.

**Saiba mais:** Investigar intenção, principal e recurso antes de concluir que houve uso indevido.

**Fonte:** [Using AWS Identity and Access Management Access Analyzer - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)


## SAA-03-007-C002

**Objetivo:** Avaliar evidência de acesso público ou externo indesejado

**Pergunta:** Como distinguir compartilhamento intencional de exposição indesejada em uma policy?

**Resposta:** Comparar o principal autorizado e as condições com a zona de confiança esperada.

**Saiba mais:** Uma conta externa legítima pode ser permitida de forma controlada.

**Fonte:** [Using AWS Identity and Access Management Access Analyzer - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)


## SAA-03-008-C001

**Objetivo:** Explicar o resultado de um teste de menor privilégio

**Pergunta:** Um teste permite ler o objeto correto, mas também permite excluir qualquer objeto. O menor privilégio foi demonstrado?

**Resposta:** Não.

**Saiba mais:** É preciso verificar ações permitidas e ações que devem continuar negadas.

**Fonte:** [IAM policy testing with the IAM policy simulator - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)


## SAA-03-008-C002

**Objetivo:** Explicar o resultado de um teste de menor privilégio

**Pergunta:** Por que validar uma policy com testes positivos e negativos?

**Resposta:** Para comprovar que ela permite o necessário e restringe o restante esperado.

**Saiba mais:** Uma única chamada bem-sucedida não prova o isolamento completo.

**Fonte:** [IAM policy testing with the IAM policy simulator - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)

