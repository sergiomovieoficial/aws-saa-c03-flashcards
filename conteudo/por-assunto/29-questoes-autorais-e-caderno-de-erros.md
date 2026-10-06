# 29 · Questões autorais e caderno de erros

24 cartões · primeira edição · 05/10/2026.


## SAA-29-001-C001

**Objetivo:** Escolha única: acesso e identidade com restrições explícitas

**Pergunta:** Escolha uma: EC2 precisa ler S3 sem credenciais permanentes. A) Chaves root na AMI. B) Role associada à instância. C) Bucket público.

**Resposta:** B) Role associada à instância.

**Saiba mais:** A expõe credenciais privilegiadas; C altera a exposição dos dados sem necessidade.

**Fonte:** [Temporary security credentials in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html)


## SAA-29-001-C002

**Objetivo:** Escolha única: acesso e identidade com restrições explícitas

**Pergunta:** Escolha uma: prestador multicliente assume role; deve-se mitigar confused deputy. A) External ID na trust policy. B) Abrir o bucket. C) Aumentar timeout.

**Resposta:** A) External ID na trust policy.

**Saiba mais:** O controle vincula a assunção ao contexto esperado; as outras opções não resolvem a delegação.

**Fonte:** [Access to AWS accounts owned by third parties - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html)


## SAA-29-002-C001

**Objetivo:** Escolha única: segurança de dados e aplicação

**Pergunta:** Escolha uma: credenciais de banco precisam de ciclo de rotação gerenciado. A) Texto na imagem. B) Secrets Manager com rotação adequada. C) Tag no recurso.

**Resposta:** B) Secrets Manager com rotação adequada.

**Saiba mais:** A rotação precisa atualizar o sistema de destino e o segredo de forma coordenada.

**Fonte:** [Rotate AWS Secrets Manager secrets - AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/rotating-secrets.html)


## SAA-29-002-C002

**Objetivo:** Escolha única: segurança de dados e aplicação

**Pergunta:** Escolha uma: retenção não pode ser encurtada nem por root durante o prazo. A) Só versioning. B) Object Lock compliance. C) Presigned URL.

**Resposta:** B) Object Lock compliance.

**Saiba mais:** Versioning sozinho não impede exclusão autorizada de versões; URL assinada trata acesso.

**Fonte:** [Locking objects with Object Lock - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html)


## SAA-29-003-C001

**Objetivo:** Escolha única: disponibilidade e continuidade

**Pergunta:** Escolha uma: RDS DB instance precisa de failover automático, sem objetivo de leitura adicional. A) Multi-AZ com standby. B) Só aumentar disco. C) Só cache local.

**Resposta:** A) Multi-AZ com standby.

**Saiba mais:** As demais opções não criam a proteção de disponibilidade pedida.

**Fonte:** [Multi-AZ DB instance deployments for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html)


## SAA-29-003-C002

**Objetivo:** Escolha única: disponibilidade e continuidade

**Pergunta:** Escolha uma: qual evidência sustenta melhor o RTO? A) Backup existe. B) Restauração funcional cronometrada. C) Volume está cifrado.

**Resposta:** B) Restauração funcional cronometrada.

**Saiba mais:** Preservação e criptografia são importantes, mas não medem o tempo de retorno do serviço.

**Fonte:** [Restore testing - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/restore-testing.html)


## SAA-29-004-C001

**Objetivo:** Escolha única: desacoplamento e escala independente

**Pergunta:** Escolha uma: dois serviços precisam receber cada evento e ter backlog independente. A) Ambos competem na mesma fila. B) SNS para duas filas. C) Um arquivo local.

**Resposta:** B) SNS para duas filas.

**Saiba mais:** A competição numa única fila não oferece uma cópia de cada mensagem a cada aplicação.

**Fonte:** [Fanout Amazon SNS notifications to Amazon SQS queues for asynchronous processing - Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/sns-sqs-as-subscriber.html)


## SAA-29-004-C002

**Objetivo:** Escolha única: desacoplamento e escala independente

**Pergunta:** Escolha uma: trabalho ainda executa quando a mensagem reaparece. A) Rever visibility timeout. B) Reduzir retenção. C) Tornar fila pública.

**Resposta:** A) Rever visibility timeout.

**Saiba mais:** Retenção define vida máxima da mensagem; não a ocultação durante processamento.

**Fonte:** [Amazon SQS visibility timeout - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)


## SAA-29-005-C001

**Objetivo:** Escolha única: armazenamento e banco por acesso

**Pergunta:** Escolha uma: aplicação exige SMB integrado ao AD. A) EFS por ser compartilhado. B) FSx for Windows. C) EBS comum anexado indiscriminadamente.

**Resposta:** B) FSx for Windows.

**Saiba mais:** O protocolo e a integração de diretório determinam a escolha.

**Fonte:** [What is FSx for Windows File Server? - Amazon FSx for Windows File Server](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/what-is.html)


## SAA-29-005-C002

**Objetivo:** Escolha única: armazenamento e banco por acesso

**Pergunta:** Escolha uma: DynamoDB precisa consultar eficientemente por outra partition key. A) GSI. B) Aumentar TTL. C) Trocar o nome da tabela.

**Resposta:** A) GSI.

**Saiba mais:** O índice acrescenta um padrão de acesso; TTL e nome não fazem isso.

**Fonte:** [Improving data access with secondary indexes in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html)


## SAA-29-006-C001

**Objetivo:** Escolha única: rede, computação e ingestão por desempenho

**Pergunta:** Escolha uma: /api e /imagens devem ir a backends diferentes por regra HTTP. A) ALB. B) Só NACL. C) Só Internet Gateway.

**Resposta:** A) ALB.

**Saiba mais:** As outras opções não inspecionam path HTTP para escolher target group.

**Fonte:** [Listeners for your Application Load Balancers - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html)


## SAA-29-006-C002

**Objetivo:** Escolha única: rede, computação e ingestão por desempenho

**Pergunta:** Escolha uma: entregar dados contínuos a um destino suportado com mínimo gerenciamento do transporte. A) Data Firehose. B) IAM group. C) Snapshot manual diário.

**Resposta:** A) Data Firehose.

**Saiba mais:** O cenário pede entrega de streaming; as outras alternativas tratam problemas diferentes.

**Fonte:** [What is Amazon Data Firehose? - Amazon Data Firehose](https://docs.aws.amazon.com/firehose/latest/dev/what-is-this-service.html)


## SAA-29-007-C001

**Objetivo:** Escolha única: custo total de armazenamento e computação

**Pergunta:** Escolha uma: jobs reiniciáveis com checkpoints toleram interrupção e priorizam economia. A) Avaliar Spot. B) Exigir host dedicado sem requisito. C) Usar maior instância sempre.

**Resposta:** A) Avaliar Spot.

**Saiba mais:** A tolerância a interrupção é a condição decisiva para aproveitar essa modalidade.

**Fonte:** [Spot Instance interruptions - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-interruptions.html)


## SAA-29-007-C002

**Objetivo:** Escolha única: custo total de armazenamento e computação

**Pergunta:** Escolha uma: padrão de acesso de objetos muda e é difícil prever. A) Intelligent-Tiering. B) Excluir sem retenção. C) Duplicar tudo em Standard sem objetivo.

**Resposta:** A) Intelligent-Tiering.

**Saiba mais:** Avaliar custos e elegibilidade, mas a finalidade é adaptar tiers ao uso.

**Fonte:** [Managing storage costs with Amazon S3 Intelligent-Tiering - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/intelligent-tiering.html)


## SAA-29-008-C001

**Objetivo:** Escolha única: custo total de banco e rede

**Pergunta:** Escolha uma: EC2 privada acessa S3 na região e deseja evitar caminho por NAT. A) Gateway endpoint S3. B) Chave root. C) Aumentar memória da EC2.

**Resposta:** A) Gateway endpoint S3.

**Saiba mais:** Rotas e políticas precisam permitir seu uso; as demais opções não mudam o caminho de rede.

**Fonte:** [Gateway endpoints for Amazon S3 - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints-s3.html)


## SAA-29-008-C002

**Objetivo:** Escolha única: custo total de banco e rede

**Pergunta:** Escolha uma: o gargalo é I/O do banco, com CPU folgada. A) Analisar storage/IOPS. B) Duplicar CPU sem medir. C) Mudar logo do dashboard.

**Resposta:** A) Analisar storage/IOPS.

**Saiba mais:** Dimensionamento deve atacar a limitação observada.

**Fonte:** [Amazon RDS DB instance storage - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html)


## SAA-29-009-C001

**Objetivo:** Múltipla seleção: conjunto mínimo de componentes necessários

**Pergunta:** Selecione duas para acesso IPv4 direto de EC2 à internet: A) Rota para IGW. B) IPv4 público apropriado. C) Apenas nome da subnet contendo pública. Considere SG/NACL já corretos.

**Resposta:** A e B.

**Saiba mais:** O nome da subnet não cria conectividade.

**Fonte:** [Enable internet access for a VPC using an internet gateway - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)


## SAA-29-009-C002

**Objetivo:** Múltipla seleção: conjunto mínimo de componentes necessários

**Pergunta:** Selecione duas para origem S3 privada com CloudFront: A) OAC compatível. B) Política do bucket permitindo a distribuição. C) Tornar todos os objetos públicos.

**Resposta:** A e B.

**Saiba mais:** A publicação anônima direta contraria o requisito de origem privada.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)


## SAA-29-010-C001

**Objetivo:** Múltipla seleção: controles complementares de segurança

**Pergunta:** Selecione duas boas práticas para acesso humano: A) Federação com credenciais temporárias quando possível. B) MFA conforme o modelo de acesso. C) Compartilhar uma senha root.

**Resposta:** A e B.

**Saiba mais:** Identidade individual e fatores adicionais reduzem risco e melhoram controle.

**Fonte:** [Security best practices in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)


## SAA-29-010-C002

**Objetivo:** Múltipla seleção: controles complementares de segurança

**Pergunta:** Selecione duas camadas a verificar para leitura de objeto SSE-KMS: A) Permissão S3. B) Autorização KMS. C) Cor do bucket no console.

**Resposta:** A e B.

**Saiba mais:** Autorização do dado e da chave são verificações complementares.

**Fonte:** [Using server-side encryption with AWS KMS keys (SSE-KMS) - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingKMSEncryption.html)


## SAA-29-011-C001

**Objetivo:** Análise de alternativa plausível que falha em um requisito

**Pergunta:** Uma alternativa usa Deep Archive para dados que devem estar disponíveis imediatamente. Por que o menor preço não a torna correta?

**Resposta:** Ela não atende ao tempo de recuperação exigido.

**Saiba mais:** Primeiro eliminar opções que violam requisitos obrigatórios.

**Fonte:** [Understanding S3 Glacier storage classes for long-term data storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/glacier-storage-classes.html)


## SAA-29-011-C002

**Objetivo:** Análise de alternativa plausível que falha em um requisito

**Pergunta:** Uma alternativa usa standby tradicional Multi-AZ para descarregar SELECTs. Qual requisito ela não atende?

**Resposta:** Escala de leitura pela standby.

**Saiba mais:** Identificar precisamente a modalidade evita confundir disponibilidade com réplica de leitura.

**Fonte:** [Multi-AZ DB instance deployments for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html)


## SAA-29-012-C001

**Objetivo:** Caderno de erros: transformar equívoco recorrente em objetivo específico

**Pergunta:** Ao errar uma questão de arquitetura, qual informação é mais útil registrar que apenas a letra correta?

**Resposta:** A restrição decisiva e a razão técnica de descartar a alternativa escolhida.

**Saiba mais:** Isso permite criar um cartão que corrija o raciocínio, não memorize posição de resposta.

**Fonte:** [AWS Certified Solutions Architect - Associate (SAA-C03) - AWS Certified Solutions Architect - Associate](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03/solutions-architect-associate-03.html)


## SAA-29-012-C002

**Objetivo:** Caderno de erros: transformar equívoco recorrente em objetivo específico

**Pergunta:** Dois serviços parecem possíveis. Qual pergunta ajuda a evitar escolha por preferência?

**Resposta:** Qual opção satisfaz melhor todas as condições e o critério pedido?

**Saiba mais:** Comparar evidências do cenário torna a decisão reproduzível.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

