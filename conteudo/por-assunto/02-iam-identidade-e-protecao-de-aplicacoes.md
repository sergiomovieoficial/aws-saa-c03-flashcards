# 02 · IAM, identidade e proteção de aplicações

57 cartões · primeira edição · 05/10/2026.


## SAA-02-001-C001

**Objetivo:** Usuários, grupos e roles: selecionar identidade para cada ator

**Pergunta:** Qual identidade IAM é apropriada para uma aplicação EC2 acessar serviços AWS sem chaves fixas?

**Resposta:** Uma IAM role associada à instância por um instance profile.

**Saiba mais:** A aplicação obtém credenciais temporárias da role.

**Fonte:** [IAM Identities - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)


## SAA-02-001-C002

**Objetivo:** Usuários, grupos e roles: selecionar identidade para cada ator

**Pergunta:** Qual é a função de um grupo IAM?

**Resposta:** Agrupar usuários IAM para administrar permissões em conjunto.

**Saiba mais:** Um grupo não possui credenciais nem pode assumir uma role.

**Fonte:** [IAM Identities - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)


## SAA-02-001-C003

**Objetivo:** Usuários, grupos e roles: selecionar identidade para cada ator

**Pergunta:** Uma role IAM representa obrigatoriamente uma pessoa específica?

**Resposta:** Não. É uma identidade assumível por entidades autorizadas.

**Saiba mais:** Pode atender pessoas federadas, aplicações ou serviços.

**Fonte:** [IAM Identities - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)


## SAA-02-002-C001

**Objetivo:** Credenciais temporárias e permanentes: selecionar a abordagem de acesso

**Pergunta:** Quais componentes formam credenciais temporárias AWS?

**Resposta:** Access key ID, secret access key e session token.

**Saiba mais:** O token de sessão faz parte da autenticação dessas credenciais.

**Fonte:** [Temporary security credentials in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html)


## SAA-02-002-C002

**Objetivo:** Credenciais temporárias e permanentes: selecionar a abordagem de acesso

**Pergunta:** Qual propriedade reduz o risco de exposição prolongada de credenciais temporárias?

**Resposta:** Elas expiram.

**Saiba mais:** A aplicação deve obter novas credenciais pelo mecanismo apropriado, não armazená-las como permanentes.

**Fonte:** [Temporary security credentials in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html)


## SAA-02-002-C003

**Objetivo:** Credenciais temporárias e permanentes: selecionar a abordagem de acesso

**Pergunta:** Por que não embutir access keys de um usuário IAM em uma AMI?

**Resposta:** Elas podem ser copiadas junto com a imagem e têm ciclo de vida independente das instâncias.

**Saiba mais:** Preferir roles e obtenção automática de credenciais temporárias.

**Fonte:** [Temporary security credentials in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html)


## SAA-02-003-C001

**Objetivo:** IAM policies: interpretar Effect, Action, Resource e Condition

**Pergunta:** Em uma policy IAM, qual elemento especifica as operações permitidas ou negadas?

**Resposta:** Action.

**Saiba mais:** Resource identifica os recursos; Condition restringe as circunstâncias.

**Fonte:** [IAM JSON policy element reference - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html)


## SAA-02-003-C002

**Objetivo:** IAM policies: interpretar Effect, Action, Resource e Condition

**Pergunta:** Em uma policy IAM, o que expressa Effect?

**Resposta:** Se a declaração concede Allow ou estabelece Deny.

**Saiba mais:** A decisão final ainda considera as demais políticas aplicáveis.

**Fonte:** [IAM JSON policy element reference - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html)


## SAA-02-003-C003

**Objetivo:** IAM policies: interpretar Effect, Action, Resource e Condition

**Pergunta:** Qual elemento de uma policy limita uma permissão a uma condição como tag ou origem de rede?

**Resposta:** Condition.

**Saiba mais:** A condição precisa usar chaves compatíveis com a requisição e o serviço.

**Fonte:** [IAM JSON policy element reference - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html)


## SAA-02-004-C001

**Objetivo:** Políticas de identidade e de recurso: distinguir onde conceder acesso

**Pergunta:** Onde é anexada uma política baseada em identidade?

**Resposta:** A uma identidade IAM, como usuário, grupo ou role.

**Saiba mais:** Ela descreve o que essa identidade pode fazer.

**Fonte:** [Identity-based policies and resource-based policies - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)


## SAA-02-004-C002

**Objetivo:** Políticas de identidade e de recurso: distinguir onde conceder acesso

**Pergunta:** Onde é aplicada uma política baseada em recurso?

**Resposta:** No recurso que suporta esse tipo de política.

**Saiba mais:** Uma bucket policy do S3 é um exemplo.

**Fonte:** [Identity-based policies and resource-based policies - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)


## SAA-02-004-C003

**Objetivo:** Políticas de identidade e de recurso: distinguir onde conceder acesso

**Pergunta:** Por que uma política de recurso normalmente especifica Principal?

**Resposta:** Para indicar quais entidades podem ou não acessar o recurso.

**Saiba mais:** A política está vinculada ao recurso, não a uma única identidade.

**Fonte:** [Identity-based policies and resource-based policies - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)


## SAA-02-005-C001

**Objetivo:** Allow, deny explícito e negação implícita: resolver autorização

**Pergunta:** Um Allow em uma policy supera um Deny explícito aplicável em outra?

**Resposta:** Não.

**Saiba mais:** A negação explícita prevalece na avaliação de permissões.

**Fonte:** [Policy evaluation logic - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html)


## SAA-02-005-C002

**Objetivo:** Allow, deny explícito e negação implícita: resolver autorização

**Pergunta:** O que é negação implícita no IAM?

**Resposta:** A ausência de uma concessão válida para a operação.

**Saiba mais:** Não é necessário escrever Deny para que uma operação sem permissão seja recusada.

**Fonte:** [Policy evaluation logic - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html)


## SAA-02-005-C003

**Objetivo:** Allow, deny explícito e negação implícita: resolver autorização

**Pergunta:** Adicionar AdministratorAccess sempre resolve um bloqueio causado por SCP?

**Resposta:** Não.

**Saiba mais:** Permissões de identidade continuam sujeitas aos limites organizacionais aplicáveis.

**Fonte:** [Policy evaluation logic - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html)


## SAA-02-006-C001

**Objetivo:** Trust policy e permissions policy: separar confiança de permissão

**Pergunta:** Qual pergunta uma trust policy de role responde?

**Resposta:** Quem pode assumir a role e sob quais condições.

**Saiba mais:** Ela não define, sozinha, tudo que a sessão poderá fazer após assumir a role.

**Fonte:** [IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html)


## SAA-02-006-C002

**Objetivo:** Trust policy e permissions policy: separar confiança de permissão

**Pergunta:** Qual pergunta a permissions policy da role responde?

**Resposta:** Quais ações a role pode executar nos recursos.

**Saiba mais:** A trust policy controla quem obtém essa identidade.

**Fonte:** [IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html)


## SAA-02-006-C003

**Objetivo:** Trust policy e permissions policy: separar confiança de permissão

**Pergunta:** Uma trust policy que permite assumir a role concede automaticamente leitura de S3?

**Resposta:** Não.

**Saiba mais:** A autorização das operações da sessão precisa ser definida pelas políticas aplicáveis.

**Fonte:** [IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html)


## SAA-02-007-C001

**Objetivo:** STS AssumeRole e acesso entre contas: decompor o fluxo

**Pergunta:** Em acesso entre contas por AssumeRole, em qual conta é criada a role de destino?

**Resposta:** Na conta que oferece o acesso delegado aos recursos.

**Saiba mais:** A identidade de origem precisa poder assumir a role e ser confiada pelo destino.

**Fonte:** [IAM tutorial: Delegate access across AWS accounts using IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html)


## SAA-02-007-C002

**Objetivo:** STS AssumeRole e acesso entre contas: decompor o fluxo

**Pergunta:** Após AssumeRole, a aplicação usa suas chaves originais para agir como a role?

**Resposta:** Não. Usa as credenciais temporárias retornadas para a sessão da role.

**Saiba mais:** A sessão possui permissões associadas à role, sujeitas aos controles aplicáveis.

**Fonte:** [IAM tutorial: Delegate access across AWS accounts using IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html)


## SAA-02-007-C003

**Objetivo:** STS AssumeRole e acesso entre contas: decompor o fluxo

**Pergunta:** Por que conceder sts:AssumeRole na origem não basta quando a trust policy do destino rejeita o principal?

**Resposta:** Porque a relação de confiança do destino também precisa autorizar a assunção.

**Saiba mais:** Acesso entre contas exige analisar os dois lados.

**Fonte:** [IAM tutorial: Delegate access across AWS accounts using IAM roles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html)


## SAA-02-008-C001

**Objetivo:** External ID e confused deputy: identificar cenário de terceiro

**Pergunta:** Qual problema o External ID ajuda a mitigar em roles assumidas por um prestador multicliente?

**Resposta:** Confused deputy.

**Saiba mais:** Ele vincula a assunção ao contexto do cliente esperado pelo prestador.

**Fonte:** [Access to AWS accounts owned by third parties - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html)


## SAA-02-008-C002

**Objetivo:** External ID e confused deputy: identificar cenário de terceiro

**Pergunta:** External ID deve ser tratado como substituto de uma senha secreta?

**Resposta:** Não.

**Saiba mais:** Ele é uma condição de contexto e pode ser visível a quem consulta a role.

**Fonte:** [Access to AWS accounts owned by third parties - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html)


## SAA-02-008-C003

**Objetivo:** External ID e confused deputy: identificar cenário de terceiro

**Pergunta:** Onde exigir External ID para um terceiro assumir uma role?

**Resposta:** Em uma condição da trust policy.

**Saiba mais:** O terceiro deve enviar o valor correspondente ao chamar AssumeRole.

**Fonte:** [Access to AWS accounts owned by third parties - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html)


## SAA-02-009-C001

**Objetivo:** Permissions boundary e session policy: interpretar limites de permissão

**Pergunta:** Uma permissions boundary concede permissões por conta própria?

**Resposta:** Não. Ela limita permissões concedidas por políticas de identidade.

**Saiba mais:** Uma role sem concessões não passa a ter acesso só por receber uma boundary permissiva.

**Fonte:** [Permissions boundaries for IAM entities - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)


## SAA-02-009-C002

**Objetivo:** Permissions boundary e session policy: interpretar limites de permissão

**Pergunta:** Para que serve uma permissions boundary ao permitir que desenvolvedores criem roles?

**Resposta:** Estabelecer o teto das permissões delegadas.

**Saiba mais:** A política que permite criar roles também deve exigir o uso da boundary adequada.

**Fonte:** [Permissions boundaries for IAM entities - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)


## SAA-02-009-C003

**Objetivo:** Permissions boundary e session policy: interpretar limites de permissão

**Pergunta:** Uma session policy pode aumentar as permissões da role assumida?

**Resposta:** Não. Ela pode restringir as permissões da sessão.

**Saiba mais:** A sessão não ganha operações que a role não possui.

**Fonte:** [Permissions boundaries for IAM entities - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)


## SAA-02-010-C001

**Objetivo:** Menor privilégio e IAM Access Analyzer: revisar acesso concedido

**Pergunta:** Qual recurso ajuda a encontrar acesso público ou entre contas em recursos suportados?

**Resposta:** IAM Access Analyzer.

**Saiba mais:** O resultado precisa ser interpretado em relação à zona de confiança configurada.

**Fonte:** [Using AWS Identity and Access Management Access Analyzer - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)


## SAA-02-010-C002

**Objetivo:** Menor privilégio e IAM Access Analyzer: revisar acesso concedido

**Pergunta:** Como usar atividade observada para reduzir permissões de uma aplicação?

**Resposta:** Gerar e revisar políticas com IAM Access Analyzer a partir de atividade suportada.

**Saiba mais:** Ausência de uso recente não prova que uma permissão nunca será necessária.

**Fonte:** [Using AWS Identity and Access Management Access Analyzer - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)


## SAA-02-011-C001

**Objetivo:** MFA, usuário root e recuperação de acesso: selecionar controles

**Pergunta:** O usuário root deve ser usado nas tarefas administrativas diárias?

**Resposta:** Não.

**Saiba mais:** Usar acesso administrativo por identidades apropriadas e reservar root para necessidades específicas.

**Fonte:** [Root user best practices for your AWS account - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/root-user-best-practices.html)


## SAA-02-011-C002

**Objetivo:** MFA, usuário root e recuperação de acesso: selecionar controles

**Pergunta:** Por que habilitar MFA além de uma senha forte?

**Resposta:** Para exigir um fator adicional de autenticação.

**Saiba mais:** MFA não substitui políticas de menor privilégio.

**Fonte:** [Root user best practices for your AWS account - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/root-user-best-practices.html)


## SAA-02-011-C003

**Objetivo:** MFA, usuário root e recuperação de acesso: selecionar controles

**Pergunta:** Deve-se criar access keys de root para uma aplicação automatizada?

**Resposta:** Não.

**Saiba mais:** A aplicação deve usar uma identidade específica com acesso limitado, preferencialmente temporário.

**Fonte:** [Root user best practices for your AWS account - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/root-user-best-practices.html)


## SAA-02-012-C001

**Objetivo:** IAM Identity Center e federação: acesso humano a múltiplas contas

**Pergunta:** Qual serviço centraliza acesso de funcionários a múltiplas contas AWS?

**Resposta:** IAM Identity Center.

**Saiba mais:** Ele permite gerenciar acesso integrado a uma fonte de identidades.

**Fonte:** [What is IAM Identity Center? - AWS IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html)


## SAA-02-012-C002

**Objetivo:** IAM Identity Center e federação: acesso humano a múltiplas contas

**Pergunta:** Uma empresa precisa criar um usuário IAM permanente em cada conta para cada funcionário?

**Resposta:** Não.

**Saiba mais:** Federação e IAM Identity Center podem fornecer acesso centralizado por credenciais temporárias.

**Fonte:** [What is IAM Identity Center? - AWS IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html)


## SAA-02-012-C003

**Objetivo:** IAM Identity Center e federação: acesso humano a múltiplas contas

**Pergunta:** O que descreve um permission set no IAM Identity Center?

**Resposta:** Um conjunto de permissões usado para conceder acesso a contas AWS.

**Saiba mais:** A atribuição conecta usuários ou grupos às contas e permissões desejadas.

**Fonte:** [What is IAM Identity Center? - AWS IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html)


## SAA-02-013-C001

**Objetivo:** SAML e OIDC: reconhecer fluxos de federação

**Pergunta:** Qual padrão costuma integrar login corporativo federado a roles AWS usando asserções?

**Resposta:** SAML 2.0.

**Saiba mais:** A identidade autentica no provedor e obtém acesso federado conforme a confiança configurada.

**Fonte:** [Identity providers and federation into AWS - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers.html)


## SAA-02-013-C002

**Objetivo:** SAML e OIDC: reconhecer fluxos de federação

**Pergunta:** Qual API STS troca um token de identidade web suportado por credenciais temporárias?

**Resposta:** AssumeRoleWithWebIdentity.

**Saiba mais:** A role deve confiar no provedor e restringir os atributos relevantes do token.

**Fonte:** [Identity providers and federation into AWS - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers.html)


## SAA-02-014-C001

**Objetivo:** Instance profiles e roles de execução: credenciais para workloads

**Pergunta:** Qual é a função do instance profile no EC2?

**Resposta:** Entregar uma IAM role à instância.

**Saiba mais:** O profile é o vínculo usado para disponibilizar credenciais da role ao workload.

**Fonte:** [Use instance profiles - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2_instance-profiles.html)


## SAA-02-014-C002

**Objetivo:** Instance profiles e roles de execução: credenciais para workloads

**Pergunta:** Quem deve receber permissão para o código de uma Lambda ler um bucket?

**Resposta:** A execution role da função.

**Saiba mais:** A permissão para invocar a função é um controle separado.

**Fonte:** [Defining Lambda function permissions with an execution role - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html)


## SAA-02-015-C001

**Objetivo:** ABAC e RBAC: decidir entre atributos e papéis

**Pergunta:** Qual é a ideia central de ABAC no IAM?

**Resposta:** Autorizar acesso por atributos, frequentemente tags de principal e recurso.

**Saiba mais:** Pode reduzir a quantidade de políticas específicas quando muitos recursos seguem o mesmo padrão.

**Fonte:** [Define permissions based on attributes with ABAC authorization - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_attribute-based-access-control.html)


## SAA-02-015-C002

**Objetivo:** ABAC e RBAC: decidir entre atributos e papéis

**Pergunta:** Qual risco existe se usuários podem alterar livremente tags usadas para autorização?

**Resposta:** Eles podem modificar atributos que influenciam o próprio acesso.

**Saiba mais:** O controle sobre criação e alteração de tags também deve ser protegido.

**Fonte:** [Define permissions based on attributes with ABAC authorization - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_attribute-based-access-control.html)


## SAA-02-016-C001

**Objetivo:** Cognito user pools e identity pools: distinguir autenticação de credenciais AWS

**Pergunta:** Qual é a função principal de um Cognito user pool?

**Resposta:** Gerenciar autenticação de usuários de aplicações e emitir tokens.

**Saiba mais:** É um diretório de usuários para a aplicação.

**Fonte:** [What is Amazon Cognito? - Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html)


## SAA-02-016-C002

**Objetivo:** Cognito user pools e identity pools: distinguir autenticação de credenciais AWS

**Pergunta:** Qual é a função principal de um Cognito identity pool?

**Resposta:** Fornecer credenciais AWS temporárias para identidades autorizadas.

**Saiba mais:** Pode usar tokens de user pools ou outros provedores.

**Fonte:** [What is Amazon Cognito? - Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html)


## SAA-02-016-C003

**Objetivo:** Cognito user pools e identity pools: distinguir autenticação de credenciais AWS

**Pergunta:** Um token de user pool é automaticamente uma access key para chamar S3?

**Resposta:** Não.

**Saiba mais:** A aplicação precisa do fluxo apropriado de autorização, como um identity pool para credenciais AWS.

**Fonte:** [What is Amazon Cognito? - Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html)


## SAA-02-017-C001

**Objetivo:** Directory Service: avaliar integração com diretórios corporativos

**Pergunta:** Qual opção fornece um Microsoft Active Directory gerenciado na AWS?

**Resposta:** AWS Managed Microsoft AD.

**Saiba mais:** É adequada quando o cenário exige recursos de AD com infraestrutura gerenciada.

**Fonte:** [What is AWS Directory Service? - AWS Directory Service](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html)


## SAA-02-017-C002

**Objetivo:** Directory Service: avaliar integração com diretórios corporativos

**Pergunta:** Qual opção encaminha solicitações de diretório para um Active Directory existente?

**Resposta:** AD Connector.

**Saiba mais:** Não é um novo diretório completo que substitui o AD de origem.

**Fonte:** [What is AWS Directory Service? - AWS Directory Service](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html)


## SAA-02-018-C001

**Objetivo:** WAF e Shield: distinguir proteção de aplicação e DDoS

**Pergunta:** Qual serviço filtra requisições web com regras contra padrões como SQL injection?

**Resposta:** AWS WAF.

**Saiba mais:** Atua na camada de aplicação dos recursos compatíveis.

**Fonte:** [What are AWS WAF, AWS Shield Advanced, AWS Shield network security director and AWS Firewall Manager? - AWS WAF, AWS Firewall Manager, AWS Shield Advanced, and AWS Shield network security director](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)


## SAA-02-018-C002

**Objetivo:** WAF e Shield: distinguir proteção de aplicação e DDoS

**Pergunta:** Qual família de serviço é voltada à proteção contra DDoS?

**Resposta:** AWS Shield.

**Saiba mais:** WAF e Shield podem ser usados de forma complementar.

**Fonte:** [What are AWS WAF, AWS Shield Advanced, AWS Shield network security director and AWS Firewall Manager? - AWS WAF, AWS Firewall Manager, AWS Shield Advanced, and AWS Shield network security director](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)


## SAA-02-018-C003

**Objetivo:** WAF e Shield: distinguir proteção de aplicação e DDoS

**Pergunta:** Um security group inspeciona parâmetros HTTP para detectar SQL injection?

**Resposta:** Não.

**Saiba mais:** Regras de portas e origens não substituem inspeção de aplicação.

**Fonte:** [What are AWS WAF, AWS Shield Advanced, AWS Shield network security director and AWS Firewall Manager? - AWS WAF, AWS Firewall Manager, AWS Shield Advanced, and AWS Shield network security director](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)


## SAA-02-019-C001

**Objetivo:** GuardDuty, Inspector e Macie: escolher detecção adequada

**Pergunta:** Qual serviço analisa sinais AWS para detectar atividade suspeita e ameaças?

**Resposta:** Amazon GuardDuty.

**Saiba mais:** Detecção produz achados; a resposta pode exigir integração e automação.

**Fonte:** [What is Amazon GuardDuty? - Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html)


## SAA-02-019-C002

**Objetivo:** GuardDuty, Inspector e Macie: escolher detecção adequada

**Pergunta:** Qual serviço avalia vulnerabilidades de workloads suportados, como instâncias e imagens de containers?

**Resposta:** Amazon Inspector.

**Saiba mais:** O foco é diferente de procurar dados pessoais em objetos S3.

**Fonte:** [What is Amazon Inspector? - Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html)


## SAA-02-019-C003

**Objetivo:** GuardDuty, Inspector e Macie: escolher detecção adequada

**Pergunta:** Qual serviço ajuda a descobrir dados sensíveis no S3?

**Resposta:** Amazon Macie.

**Saiba mais:** A classificação de dados complementa controles de acesso e criptografia.

**Fonte:** [What is Amazon Macie? - Amazon Macie](https://docs.aws.amazon.com/macie/latest/user/what-is-macie.html)


## SAA-02-020-C001

**Objetivo:** Security Hub, Detective e Artifact: distinguir consolidação, investigação e relatórios

**Pergunta:** Qual serviço consolida achados de segurança e avalia postura em integrações suportadas?

**Resposta:** AWS Security Hub.

**Saiba mais:** Consolidação não torna desnecessários os serviços que produzem os achados.

**Fonte:** [Introduction to AWS Security Hub CSPM - AWS Security Hub](https://docs.aws.amazon.com/securityhub/latest/userguide/what-is-securityhub.html)


## SAA-02-020-C002

**Objetivo:** Security Hub, Detective e Artifact: distinguir consolidação, investigação e relatórios

**Pergunta:** Qual serviço ajuda a investigar e relacionar eventos de segurança após um achado?

**Resposta:** Amazon Detective.

**Saiba mais:** Ele auxilia a análise; não é um substituto de firewall.

**Fonte:** [What is Amazon Detective? - Amazon Detective](https://docs.aws.amazon.com/detective/latest/userguide/what-is-detective.html)


## SAA-02-020-C003

**Objetivo:** Security Hub, Detective e Artifact: distinguir consolidação, investigação e relatórios

**Pergunta:** Onde obter relatórios de conformidade e determinados acordos da AWS?

**Resposta:** AWS Artifact.

**Saiba mais:** Relatórios da infraestrutura AWS não certificam automaticamente a configuração do cliente.

**Fonte:** [What is AWS Artifact? - AWS Artifact](https://docs.aws.amazon.com/artifact/latest/ug/what-is-aws-artifact.html)


## SAA-02-021-C001

**Objetivo:** Network Firewall e Firewall Manager: selecionar controle e governança de rede

**Pergunta:** Qual serviço oferece firewall gerenciado para inspeção de tráfego em arquiteturas VPC?

**Resposta:** AWS Network Firewall.

**Saiba mais:** O caminho de roteamento precisa passar pelos endpoints de inspeção.

**Fonte:** [What is AWS Network Firewall? - AWS Network Firewall](https://docs.aws.amazon.com/network-firewall/latest/developerguide/what-is-aws-network-firewall.html)


## SAA-02-021-C002

**Objetivo:** Network Firewall e Firewall Manager: selecionar controle e governança de rede

**Pergunta:** Qual serviço administra políticas de proteção de forma centralizada em múltiplas contas?

**Resposta:** AWS Firewall Manager.

**Saiba mais:** Ele coordena políticas de recursos suportados; não substitui cada mecanismo de proteção.

**Fonte:** [AWS Firewall Manager - AWS WAF, AWS Firewall Manager, AWS Shield Advanced, and AWS Shield network security director](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html)

