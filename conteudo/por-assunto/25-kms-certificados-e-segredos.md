# 25 · KMS, certificados e segredos

33 cartões · primeira edição · 05/10/2026.


## SAA-25-001-C001

**Objetivo:** Criptografia em repouso e em trânsito: selecionar controles

**Pergunta:** TLS protege principalmente dados em repouso ou em trânsito?

**Resposta:** Em trânsito.

**Saiba mais:** A criptografia do disco não protege, por si só, a comunicação de rede.

**Fonte:** [Data protection - Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/data-protection.html)


## SAA-25-001-C002

**Objetivo:** Criptografia em repouso e em trânsito: selecionar controles

**Pergunta:** Criptografar um banco elimina a necessidade de controlar quem consulta seus dados?

**Resposta:** Não.

**Saiba mais:** Um principal autorizado pode receber dados descriptografados normalmente.

**Fonte:** [Data protection - Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/data-protection.html)


## SAA-25-002-C001

**Objetivo:** Criptografia simétrica e assimétrica: reconhecer finalidade

**Pergunta:** Qual a diferença básica entre criptografia simétrica e assimétrica?

**Resposta:** A simétrica usa uma chave compartilhada; a assimétrica usa um par pública/privada.

**Saiba mais:** A escolha depende do uso, como criptografia ou assinatura.

**Fonte:** [Asymmetric keys in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/symmetric-asymmetric.html)


## SAA-25-002-C002

**Objetivo:** Criptografia simétrica e assimétrica: reconhecer finalidade

**Pergunta:** Em uma assinatura assimétrica, qual chave deve permanecer protegida?

**Resposta:** A chave privada.

**Saiba mais:** A chave pública pode ser distribuída para verificação.

**Fonte:** [Asymmetric keys in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/symmetric-asymmetric.html)


## SAA-25-003-C001

**Objetivo:** Envelope encryption e data keys: decompor proteção de dados

**Pergunta:** Na envelope encryption, o que normalmente cifra o grande volume de dados?

**Resposta:** Uma data key.

**Saiba mais:** A chave KMS protege a data key, evitando enviar todo o dado ao KMS.

**Fonte:** [AWS KMS keys - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#enveloping)


## SAA-25-003-C002

**Objetivo:** Envelope encryption e data keys: decompor proteção de dados

**Pergunta:** O que deve ser armazenado junto dos dados para permitir recuperação em envelope encryption?

**Resposta:** A data key cifrada e os metadados necessários.

**Saiba mais:** A data key em texto claro deve ser protegida e descartada após o uso apropriado.

**Fonte:** [AWS KMS keys - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#enveloping)


## SAA-25-004-C001

**Objetivo:** AWS owned, AWS managed e customer managed keys: distinguir controle

**Pergunta:** Qual tipo de chave KMS oferece ao cliente controle sobre política e ciclo de vida?

**Resposta:** Customer managed key.

**Saiba mais:** AWS managed e AWS owned keys têm modelos diferentes de controle.

**Fonte:** [AWS KMS keys - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html)


## SAA-25-004-C002

**Objetivo:** AWS owned, AWS managed e customer managed keys: distinguir controle

**Pergunta:** AWS owned key é uma chave que o cliente gerencia na própria conta?

**Resposta:** Não.

**Saiba mais:** Ela é controlada pela AWS para proteger dados em serviços que a utilizam.

**Fonte:** [AWS KMS keys - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html)


## SAA-25-005-C001

**Objetivo:** KMS key policy e IAM policy: avaliar autorização

**Pergunta:** Uma política IAM isolada sempre basta para usar uma chave KMS?

**Resposta:** Não. A key policy e os demais controles aplicáveis precisam permitir o acesso.

**Saiba mais:** KMS possui um modelo de autorização centrado também na política da chave.

**Fonte:** [Key policies in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html)


## SAA-25-005-C002

**Objetivo:** KMS key policy e IAM policy: avaliar autorização

**Pergunta:** Qual política controla diretamente o acesso a uma chave KMS?

**Resposta:** A key policy.

**Saiba mais:** Ela pode permitir delegação a políticas IAM conforme a configuração.

**Fonte:** [Key policies in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html)


## SAA-25-006-C001

**Objetivo:** KMS grants: reconhecer delegação a serviços

**Pergunta:** O que é um grant no KMS?

**Resposta:** Um mecanismo de concessão de operações específicas sobre uma chave.

**Saiba mais:** Serviços integrados podem usá-lo para acessar a chave em nome de workloads autorizados.

**Fonte:** [Grants in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/grants.html)


## SAA-25-006-C002

**Objetivo:** KMS grants: reconhecer delegação a serviços

**Pergunta:** Um grant é uma cópia do material criptográfico da chave?

**Resposta:** Não.

**Saiba mais:** É um instrumento de autorização, não uma exportação de chave.

**Fonte:** [Grants in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/grants.html)


## SAA-25-007-C001

**Objetivo:** KMS entre contas: avaliar política e serviço consumidor

**Pergunta:** Para acesso KMS entre contas, basta a política IAM da conta consumidora?

**Resposta:** Não. A política da chave na conta proprietária também precisa permitir o acesso.

**Saiba mais:** As operações suportadas entre contas devem ser verificadas.

**Fonte:** [Allowing users in other accounts to use a KMS key - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-modifying-external-accounts.html)


## SAA-25-007-C002

**Objetivo:** KMS entre contas: avaliar política e serviço consumidor

**Pergunta:** Por que compartilhar um snapshot criptografado pode exigir compartilhar autorização da chave?

**Resposta:** Porque acessar o snapshot não elimina a necessidade de descriptografar seus dados.

**Saiba mais:** Permissões de recurso e criptografia são camadas distintas.

**Fonte:** [Allowing users in other accounts to use a KMS key - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-modifying-external-accounts.html)


## SAA-25-008-C001

**Objetivo:** Rotação, desativação e exclusão: distinguir impactos

**Pergunta:** Rotacionar uma chave KMS recriptografa automaticamente todos os dados existentes?

**Resposta:** Não.

**Saiba mais:** O serviço preserva material anterior para operações compatíveis; recriptografar dados é uma ação distinta.

**Fonte:** [Rotate AWS KMS keys - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/rotate-keys.html)


## SAA-25-008-C002

**Objetivo:** Rotação, desativação e exclusão: distinguir impactos

**Pergunta:** Por que excluir uma chave KMS exige cuidado especial?

**Resposta:** Dados que dependem dela podem ficar irrecuperáveis.

**Saiba mais:** A existência de backups cifrados pela mesma chave não elimina essa dependência.

**Fonte:** [Delete an AWS KMS key - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html)


## SAA-25-008-C003

**Objetivo:** Rotação, desativação e exclusão: distinguir impactos

**Pergunta:** Desativar uma chave KMS tem o mesmo caráter irreversível de sua exclusão concluída?

**Resposta:** Não. A desativação pode ser revertida.

**Saiba mais:** Mesmo reversível, pode interromper serviços que precisam da chave.

**Fonte:** [Delete an AWS KMS key - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html)


## SAA-25-009-C001

**Objetivo:** Chaves Multi-Region: avaliar replicação e independência

**Pergunta:** Qual é a vantagem de chaves KMS Multi-Region relacionadas?

**Resposta:** Permitir uso de material criptográfico relacionado em regiões diferentes.

**Saiba mais:** Isso pode apoiar aplicações que movem dados cifrados entre regiões.

**Fonte:** [Multi-Region keys in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/multi-region-keys-overview.html)


## SAA-25-009-C002

**Objetivo:** Chaves Multi-Region: avaliar replicação e independência

**Pergunta:** As políticas de chaves Multi-Region são sincronizadas automaticamente entre todas as réplicas?

**Resposta:** Não.

**Saiba mais:** Vários atributos e controles são administrados independentemente em cada região.

**Fonte:** [Multi-Region keys in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/multi-region-keys-overview.html)


## SAA-25-010-C001

**Objetivo:** Encryption context: interpretar contexto de autorização

**Pergunta:** O que é encryption context no KMS?

**Resposta:** Um conjunto de pares chave-valor usado como dado autenticado adicional em operações compatíveis.

**Saiba mais:** Pode ajudar a vincular a operação a um contexto esperado.

**Fonte:** [Encryption context - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/encrypt_context.html)


## SAA-25-010-C002

**Objetivo:** Encryption context: interpretar contexto de autorização

**Pergunta:** É adequado colocar um segredo no encryption context?

**Resposta:** Não.

**Saiba mais:** O contexto não é tratado como informação secreta e pode aparecer em logs.

**Fonte:** [Encryption context - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/encrypt_context.html)


## SAA-25-011-C001

**Objetivo:** CloudHSM e KMS: comparar controle e operação

**Pergunta:** Qual serviço oferece HSMs dedicados com controle criptográfico mais direto pelo cliente?

**Resposta:** AWS CloudHSM.

**Saiba mais:** Esse controle vem com responsabilidades operacionais maiores que integrações comuns com KMS.

**Fonte:** [What is AWS CloudHSM? - AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html)


## SAA-25-011-C002

**Objetivo:** CloudHSM e KMS: comparar controle e operação

**Pergunta:** Exigir uso de um HSM significa necessariamente administrar um cluster CloudHSM?

**Resposta:** Não.

**Saiba mais:** É preciso distinguir exigência técnica do módulo de segurança da exigência de controle dedicado pelo cliente.

**Fonte:** [What is AWS CloudHSM? - AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html)


## SAA-25-012-C001

**Objetivo:** Secrets Manager e Parameter Store: escolher gerenciamento

**Pergunta:** Qual serviço é voltado ao ciclo de vida de segredos como credenciais de banco, incluindo rotação?

**Resposta:** AWS Secrets Manager.

**Saiba mais:** Escolher o mecanismo de rotação apropriado ao tipo de segredo.

**Fonte:** [What is AWS Secrets Manager? - AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html)


## SAA-25-012-C002

**Objetivo:** Secrets Manager e Parameter Store: escolher gerenciamento

**Pergunta:** Qual recurso pode armazenar parâmetros de configuração e valores SecureString?

**Resposta:** Systems Manager Parameter Store.

**Saiba mais:** Armazenar valor cifrado não equivale automaticamente a rotacionar a credencial no sistema de destino.

**Fonte:** [AWS Systems Manager Parameter Store - AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html)


## SAA-25-013-C001

**Objetivo:** Rotação de segredo: separar atualização do segredo e da aplicação

**Pergunta:** Por que mudar apenas o valor guardado no Secrets Manager pode quebrar a aplicação?

**Resposta:** A credencial no banco ou serviço de destino pode continuar diferente.

**Saiba mais:** Uma rotação precisa coordenar o segredo e o sistema que o valida.

**Fonte:** [Rotate AWS Secrets Manager secrets - AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/rotating-secrets.html)


## SAA-25-013-C002

**Objetivo:** Rotação de segredo: separar atualização do segredo e da aplicação

**Pergunta:** Qual cuidado uma aplicação com cache de segredos precisa ter após rotação?

**Resposta:** Atualizar ou invalidar o valor armazenado conforme o fluxo de rotação.

**Saiba mais:** Usar indefinidamente a credencial antiga pode causar falhas de autenticação.

**Fonte:** [Rotate AWS Secrets Manager secrets - AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/rotating-secrets.html)


## SAA-25-014-C001

**Objetivo:** ACM: selecionar certificado e planejar renovação

**Pergunta:** Certificados importados no ACM recebem renovação automática do ACM?

**Resposta:** Não.

**Saiba mais:** O cliente precisa providenciar renovação e reimportação apropriadas.

**Fonte:** [Managed certificate renewal in AWS Certificate Manager - AWS Certificate Manager](https://docs.aws.amazon.com/acm/latest/userguide/managed-renewal.html)


## SAA-25-014-C002

**Objetivo:** ACM: selecionar certificado e planejar renovação

**Pergunta:** Todos os certificados emitidos pelo ACM são renovados sem condições adicionais?

**Resposta:** Não. É preciso cumprir os requisitos de elegibilidade e validação.

**Saiba mais:** Não presumir que remover registros necessários à validação seja inofensivo.

**Fonte:** [Managed certificate renewal in AWS Certificate Manager - AWS Certificate Manager](https://docs.aws.amazon.com/acm/latest/userguide/managed-renewal.html)


## SAA-25-015-C001

**Objetivo:** Terminação TLS e criptografia ponta a ponta: avaliar caminhos

**Pergunta:** HTTPS no ALB garante que o trecho ALB até os targets também usa TLS?

**Resposta:** Não.

**Saiba mais:** O protocolo do target group determina a comunicação com os targets.

**Fonte:** [Create an HTTPS listener for your Application Load Balancer - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html)


## SAA-25-015-C002

**Objetivo:** Terminação TLS e criptografia ponta a ponta: avaliar caminhos

**Pergunta:** O que configurar quando o requisito exige cifrar também o tráfego do balanceador ao backend?

**Resposta:** Uma conexão TLS compatível no trecho até os targets.

**Saiba mais:** Criptografia em um segmento não se estende automaticamente aos demais.

**Fonte:** [Create an HTTPS listener for your Application Load Balancer - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html)


## SAA-25-016-C001

**Objetivo:** Falha KMS em S3, EBS ou RDS: localizar permissão e chave

**Pergunta:** Uma aplicação tem GetObject, mas falha ao ler um objeto SSE-KMS. Qual autorização adicional investigar?

**Resposta:** A autorização para usar a chave KMS, incluindo kms:Decrypt quando exigido.

**Saiba mais:** Conferir IAM, key policy e estado da chave.

**Fonte:** [Using server-side encryption with AWS KMS keys (SSE-KMS) - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingKMSEncryption.html)


## SAA-25-016-C002

**Objetivo:** Falha KMS em S3, EBS ou RDS: localizar permissão e chave

**Pergunta:** O que acontece com acessos que precisam de uma chave KMS desativada?

**Resposta:** Eles podem falhar mesmo que a policy do recurso permita a operação.

**Saiba mais:** Disponibilidade da chave faz parte da disponibilidade do dado.

**Fonte:** [Using server-side encryption with AWS KMS keys (SSE-KMS) - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingKMSEncryption.html)

