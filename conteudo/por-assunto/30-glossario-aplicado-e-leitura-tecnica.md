# 30 · Glossário aplicado e leitura técnica

13 cartões · primeira edição · 05/10/2026.


## SAA-30-001-C001

**Objetivo:** Mapear siglas de identidade a papéis arquiteturais

**Pergunta:** O que significa ARN e para que é usado?

**Resposta:** Amazon Resource Name; identifica recursos AWS.

**Saiba mais:** Não é uma credencial secreta nem prova autorização de acesso.

**Fonte:** [IAM identifiers - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html)


## SAA-30-001-C002

**Objetivo:** Mapear siglas de identidade a papéis arquiteturais

**Pergunta:** O que significa STS no contexto AWS?

**Resposta:** Security Token Service.

**Saiba mais:** É associado à emissão de credenciais temporárias, não a armazenamento de segredos de aplicação.

**Fonte:** [Temporary security credentials in IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html)


## SAA-30-002-C001

**Objetivo:** Mapear siglas de rede a caminhos de tráfego

**Pergunta:** O que significa VPC?

**Resposta:** Virtual Private Cloud.

**Saiba mais:** É a rede virtual onde se configuram subnets, rotas e outros recursos compatíveis.

**Fonte:** [What is Amazon VPC? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)


## SAA-30-002-C002

**Objetivo:** Mapear siglas de rede a caminhos de tráfego

**Pergunta:** O que o prefixo /24 representa na notação CIDR IPv4?

**Resposta:** Que 24 bits compõem o prefixo de rede.

**Saiba mais:** O tamanho do prefixo determina a faixa de endereços; disponibilidade para recursos inclui reservas do provedor.

**Fonte:** [VPC CIDR blocks - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-cidr-blocks.html)


## SAA-30-003-C001

**Objetivo:** Mapear siglas de recuperação a objetivos de negócio

**Pergunta:** Na expressão RPO, point se refere ao tempo para ligar servidores?

**Resposta:** Não. Refere-se ao ponto recuperável dos dados.

**Saiba mais:** Associar RPO à perda de dados e RTO ao tempo de retorno do serviço.

**Fonte:** [What is Recovery Time Objective (RTO)? - RTO Explained - AWS](https://aws.amazon.com/what-is/recovery-time-objective/)


## SAA-30-004-C001

**Objetivo:** Ler termos de consistência, replicação e transação

**Pergunta:** Leitura eventualmente consistente significa que cada leitura sempre verá o dado mais recente?

**Resposta:** Não.

**Saiba mais:** O sistema pode convergir para o estado mais recente sem garantir sua visibilidade imediata em toda leitura.

**Fonte:** [DynamoDB read consistency - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.ReadConsistency.html)


## SAA-30-004-C002

**Objetivo:** Ler termos de consistência, replicação e transação

**Pergunta:** O que significa replication lag?

**Resposta:** O atraso entre alterações da origem e sua aplicação ou visibilidade na réplica.

**Saiba mais:** A interpretação exata da métrica depende do produto.

**Fonte:** [Working with DB instance read replicas - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)


## SAA-30-005-C001

**Objetivo:** Ler unidades de capacidade, armazenamento e transferência

**Pergunta:** O que significa IOPS?

**Resposta:** Input/output operations per second, operações de entrada e saída por segundo.

**Saiba mais:** Não expressa sozinho quantos bytes cada operação transfere.

**Fonte:** [Amazon EBS volume types - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html)


## SAA-30-005-C002

**Objetivo:** Ler unidades de capacidade, armazenamento e transferência

**Pergunta:** Partition key e shard são sinônimos em um stream?

**Resposta:** Não.

**Saiba mais:** A chave participa da distribuição lógica; shard é uma unidade de particionamento/capacidade.

**Fonte:** [Amazon Kinesis Data Streams Terminology and concepts - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)


## SAA-30-006-C001

**Objetivo:** Interpretar least operational overhead e most cost-effective

**Pergunta:** O que significa least operational overhead em um enunciado?

**Resposta:** Menor esforço operacional entre soluções que atendem aos requisitos.

**Saiba mais:** Não significa obrigatoriamente menor preço de infraestrutura.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)


## SAA-30-006-C002

**Objetivo:** Interpretar least operational overhead e most cost-effective

**Pergunta:** O que significa most cost-effective em um enunciado?

**Resposta:** A alternativa com melhor custo para atender às condições exigidas.

**Saiba mais:** Não escolher a opção mais barata que descumpre segurança ou disponibilidade.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)


## SAA-30-007-C001

**Objetivo:** Distinguir highly available, fault tolerant e durable

**Pergunta:** Durable e highly available descrevem a mesma propriedade?

**Resposta:** Não.

**Saiba mais:** Durabilidade preserva os dados; disponibilidade trata de acesso e funcionamento quando necessário.

**Fonte:** [Availability - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/availability.html)


## SAA-30-008-C001

**Objetivo:** Identificar conceito já coberto para não duplicar cartão

**Pergunta:** Qual é o código da certificação Solutions Architect Associate usada neste baralho?

**Resposta:** SAA-C03.

**Saiba mais:** O código ajuda a conferir se um material corresponde à versão pretendida do exame.

**Fonte:** [AWS Certified Solutions Architect - Associate (SAA-C03) - AWS Certified Solutions Architect - Associate](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03/solutions-architect-associate-03.html)

