# 27 · Cenários integrados de arquitetura

32 cartões · primeira edição · 05/10/2026.


## SAA-27-001-C001

**Objetivo:** E-commerce com pico sazonal e banco relacional

**Pergunta:** Um e-commerce tem picos sazonais e servidores web intercambiáveis. Como expandir a camada web mantendo tolerância à falha zonal?

**Resposta:** Usar balanceamento e Auto Scaling distribuído entre AZs.

**Saiba mais:** Sessões e arquivos precisam sobreviver à substituição dos servidores.

**Fonte:** [Auto Scaling benefits for application architecture - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-benefits.html)


## SAA-27-001-C002

**Objetivo:** E-commerce com pico sazonal e banco relacional

**Pergunta:** No e-commerce, catálogo gera muitas leituras tolerantes a atraso, mas compras exigem escrita. Qual melhoria direcionada considerar?

**Resposta:** Separar leituras adequadas para réplicas ou cache, mantendo escritas no destino correto.

**Saiba mais:** Não enviar transações críticas indiscriminadamente a réplicas assíncronas.

**Fonte:** [Working with DB instance read replicas - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)


## SAA-27-002-C001

**Objetivo:** Site estático privado na origem com público global

**Pergunta:** Um site estático deve ser público, mas o bucket não pode aceitar leitura direta anônima. Qual combinação atende?

**Resposta:** CloudFront com origem S3 privada, OAC e política restrita.

**Saiba mais:** A entrada pública fica na distribuição autorizada.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)


## SAA-27-002-C002

**Objetivo:** Site estático privado na origem com público global

**Pergunta:** Uma nova versão do site foi enviada, mas usuários recebem o JavaScript antigo. Qual camada investigar?

**Resposta:** O cache da distribuição e dos clientes.

**Saiba mais:** Nomes versionados ou invalidação podem fazer parte da publicação.

**Fonte:** [Invalidate files to remove content - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html)


## SAA-27-003-C001

**Objetivo:** Processamento assíncrono de imagens enviadas por usuários

**Pergunta:** Uploads de imagens chegam em rajadas e podem ser processados depois. Como desacoplar recepção e processamento?

**Resposta:** Armazenar no S3 e encaminhar eventos a um fluxo com fila e consumidores adequados.

**Saiba mais:** A fila absorve variações sem exigir que o upload espere o processamento inteiro.

**Fonte:** [Amazon S3 Event Notifications - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/EventNotifications.html)


## SAA-27-003-C002

**Objetivo:** Processamento assíncrono de imagens enviadas por usuários

**Pergunta:** Uma função gera thumbnails no mesmo bucket que dispara sua execução. Qual cuidado evita recursão?

**Resposta:** Separar prefixos ou buckets e aplicar filtros de evento.

**Saiba mais:** O resultado não deve reativar indefinidamente o mesmo processamento.

**Fonte:** [Process Amazon S3 event notifications with Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/with-s3.html)


## SAA-27-004-C001

**Objetivo:** API de alta demanda com controle de autenticação

**Pergunta:** Uma API de clientes precisa de login e autorização por usuário. Uma API key basta?

**Resposta:** Não. Usar mecanismo de autenticação e autorização apropriado.

**Saiba mais:** API key identifica uso em certos recursos, mas não substitui identidade segura.

**Fonte:** [Control and manage access to REST APIs in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-control-access-to-api.html)


## SAA-27-004-C002

**Objetivo:** API de alta demanda com controle de autenticação

**Pergunta:** Uma API pode sobrecarregar um backend limitado. Qual controle de entrada ajuda?

**Resposta:** Throttling, junto de dimensionamento e tratamento de limite no cliente.

**Saiba mais:** A elasticidade da camada de entrada não aumenta sozinha a capacidade do backend.

**Fonte:** [Throttle requests to your REST APIs for better throughput in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-request-throttling.html)


## SAA-27-005-C001

**Objetivo:** Aplicação legada com filesystem compartilhado

**Pergunta:** Uma aplicação Linux em várias EC2 exige arquivos NFS compartilhados. Qual opção gerenciada atende ao padrão?

**Resposta:** Amazon EFS.

**Saiba mais:** S3 exigiria adaptar a interface se a aplicação espera filesystem NFS.

**Fonte:** [What is Amazon Elastic File System? - Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html)


## SAA-27-005-C002

**Objetivo:** Aplicação legada com filesystem compartilhado

**Pergunta:** Por que não anexar qualquer volume EBS a todos os servidores para substituir NFS?

**Resposta:** Multi-Attach tem restrições e exige coordenação do filesystem/aplicação.

**Saiba mais:** Bloco compartilhado não é automaticamente um serviço de arquivos compartilhado.

**Fonte:** [Attach an EBS volume to multiple EC2 instances using Multi-Attach - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volumes-multi.html)


## SAA-27-006-C001

**Objetivo:** Aplicação corporativa Windows integrada ao diretório

**Pergunta:** Uma aplicação Windows depende de SMB e permissões integradas ao AD. Qual serviço de arquivos considerar?

**Resposta:** FSx for Windows File Server.

**Saiba mais:** A compatibilidade de protocolo é a restrição decisiva.

**Fonte:** [What is FSx for Windows File Server? - Amazon FSx for Windows File Server](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/what-is.html)


## SAA-27-006-C002

**Objetivo:** Aplicação corporativa Windows integrada ao diretório

**Pergunta:** Uma empresa quer integrar aplicações ao diretório corporativo existente. O que deve orientar a escolha de Directory Service?

**Resposta:** Necessidade de diretório gerenciado ou de conexão ao diretório existente.

**Saiba mais:** Managed Microsoft AD e AD Connector não têm o mesmo papel.

**Fonte:** [What is AWS Directory Service? - AWS Directory Service](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html)


## SAA-27-007-C001

**Objetivo:** Pipeline de eventos em tempo quase real

**Pergunta:** Telemetria precisa de múltiplos consumidores e replay recente. Qual modelo de ingestão avaliar?

**Resposta:** Um stream retido, como Kinesis Data Streams.

**Saiba mais:** Uma única fila competitiva não entrega automaticamente todo histórico a cada consumidor.

**Fonte:** [Amazon Kinesis Data Streams Terminology and concepts - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)


## SAA-27-007-C002

**Objetivo:** Pipeline de eventos em tempo quase real

**Pergunta:** O requisito é entregar eventos a S3 com mínimo gerenciamento de consumidores. Qual serviço considerar?

**Resposta:** Amazon Data Firehose.

**Saiba mais:** Avaliar buffering e transformação exigidos.

**Fonte:** [What is Amazon Data Firehose? - Amazon Data Firehose](https://docs.aws.amazon.com/firehose/latest/dev/what-is-this-service.html)


## SAA-27-008-C001

**Objetivo:** Data lake com múltiplas equipes e políticas de acesso

**Pergunta:** Várias equipes compartilham dados analíticos, mas devem ter acessos distintos. Qual capacidade precisa existir no data lake?

**Resposta:** Governança granular e coerente de acesso aos dados.

**Saiba mais:** Lake Formation pode participar desse controle nas integrações suportadas.

**Fonte:** [What is AWS Lake Formation? - AWS Lake Formation](https://docs.aws.amazon.com/lake-formation/latest/dg/what-is-lake-formation.html)


## SAA-27-008-C002

**Objetivo:** Data lake com múltiplas equipes e políticas de acesso

**Pergunta:** Consultas diárias leem apenas o mês atual, mas varrem todo o histórico. Qual mudança de organização avaliar?

**Resposta:** Particionar dados de modo que o filtro limite a leitura necessária.

**Saiba mais:** Formato colunar e compressão podem complementar a otimização.

**Fonte:** [Optimize data - Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/performance-tuning-data-optimization-techniques.html)


## SAA-27-009-C001

**Objetivo:** Migração de banco com janela curta de indisponibilidade

**Pergunta:** Uma base segue recebendo escritas durante a migração e só aceita curta parada final. Qual estratégia de dados avaliar?

**Resposta:** Carga inicial seguida de CDC e cutover coordenado.

**Saiba mais:** Validar sincronização e compatibilidade antes da troca.

**Fonte:** [Creating tasks for ongoing replication using AWS DMS - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Task.CDC.html)


## SAA-27-009-C002

**Objetivo:** Migração de banco com janela curta de indisponibilidade

**Pergunta:** O destino usa outro engine. Por que replicar linhas não é o plano completo?

**Resposta:** Esquema, tipos e lógica podem exigir conversão.

**Saiba mais:** Testar consultas e aplicações além dos dados transferidos.

**Fonte:** [Converting database schemas using DMS Schema Conversion - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_SchemaConversion.html)


## SAA-27-010-C001

**Objetivo:** Recuperação regional para sistema transacional

**Pergunta:** Uma aplicação transacional exige recuperação regional. Qual aspecto dos dados precisa ser definido antes do failover?

**Resposta:** O RPO e o comportamento da replicação no momento da mudança.

**Saiba mais:** Uma região secundária existente não garante ausência de perda.

**Fonte:** [Using switchover or failover in Amazon Aurora Global Database - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database-disaster-recovery.html)


## SAA-27-010-C002

**Objetivo:** Recuperação regional para sistema transacional

**Pergunta:** O ambiente secundário tem dados replicados, mas quota insuficiente para escalar. Qual requisito de DR foi negligenciado?

**Resposta:** Capacidade operacional de recuperação.

**Saiba mais:** Preparar dados e preparar capacidade são etapas complementares.

**Fonte:** [Manage service quotas and constraints - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/manage-service-quotas-and-constraints.html)


## SAA-27-011-C001

**Objetivo:** Plataforma SaaS com isolamento entre clientes

**Pergunta:** Em SaaS multitenant, autenticar o usuário basta para isolá-lo dos dados de outros clientes?

**Resposta:** Não.

**Saiba mais:** Toda operação precisa manter o contexto e a autorização do tenant.

**Fonte:** [Tenant Isolation - SaaS Lens](https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/tenant-isolation.html)


## SAA-27-011-C002

**Objetivo:** Plataforma SaaS com isolamento entre clientes

**Pergunta:** Como atributos podem ajudar a controlar acesso por tenant em um desenho compatível?

**Resposta:** Relacionando atributos do principal aos recursos autorizados.

**Saiba mais:** Também proteger quem pode atribuir ou alterar esses atributos.

**Fonte:** [Define permissions based on attributes with ABAC authorization - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_attribute-based-access-control.html)


## SAA-27-012-C001

**Objetivo:** Processamento em lote tolerante a interrupções

**Pergunta:** Um lote pode reiniciar e possui checkpoints duráveis. Qual modelo de compra pode reduzir custo?

**Resposta:** Spot, com tratamento de interrupções.

**Saiba mais:** A economia depende de a aplicação suportar a recuperação.

**Fonte:** [Spot Instance interruptions - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-interruptions.html)


## SAA-27-012-C002

**Objetivo:** Processamento em lote tolerante a interrupções

**Pergunta:** Milhares de jobs independentes precisam de fila e capacidade gerenciada. Qual serviço de computação considerar?

**Resposta:** AWS Batch.

**Saiba mais:** Ele organiza execução por requisitos de jobs e ambientes configurados.

**Fonte:** [What is AWS Batch? - AWS Batch](https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html)


## SAA-27-013-C001

**Objetivo:** Serviço global que exige endereços estáticos

**Pergunta:** Parceiros exigem IPs estáticos para uma aplicação global TCP. Qual camada de entrada considerar?

**Resposta:** Global Accelerator com endpoints compatíveis.

**Saiba mais:** CDN com cache HTTP não é a mesma solução para esse requisito.

**Fonte:** [What is AWS Global Accelerator? - AWS Global Accelerator](https://docs.aws.amazon.com/global-accelerator/latest/dg/what-is-global-accelerator.html)


## SAA-27-013-C002

**Objetivo:** Serviço global que exige endereços estáticos

**Pergunta:** Um serviço regional TCP exige balanceamento por transporte e IP estático por AZ. Qual balanceador avaliar?

**Resposta:** Network Load Balancer.

**Saiba mais:** A abrangência regional distingue esse componente da aceleração global.

**Fonte:** [What is a Network Load Balancer? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)


## SAA-27-014-C001

**Objetivo:** Arquivamento regulado com restrição de exclusão

**Pergunta:** Documentos devem permanecer sem possibilidade de apagar antes de prazo legal, inclusive por administradores. Qual proteção S3 avaliar?

**Resposta:** Object Lock em compliance mode com retenção apropriada.

**Saiba mais:** Verificar versão, prazo e condições do requisito.

**Fonte:** [Locking objects with Object Lock - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html)


## SAA-27-014-C002

**Objetivo:** Arquivamento regulado com restrição de exclusão

**Pergunta:** Documentos retidos raramente são lidos, mas precisam estar disponíveis imediatamente quando solicitados. Deep Archive é automaticamente adequado?

**Resposta:** Não.

**Saiba mais:** A classe precisa atender ao tempo de acesso; considerar opções de recuperação imediata.

**Fonte:** [Understanding S3 Glacier storage classes for long-term data storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/glacier-storage-classes.html)


## SAA-27-015-C001

**Objetivo:** Rede corporativa com dezenas de VPCs

**Pergunta:** Dezenas de VPCs precisam de conectividade central com segmentação. Qual serviço avaliar?

**Resposta:** Transit Gateway com route tables planejadas.

**Saiba mais:** Conectar todas as redes sem segmentação não atende automaticamente ao requisito.

**Fonte:** [What is AWS Transit Gateway for Amazon VPC? - Amazon VPC](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html)


## SAA-27-015-C002

**Objetivo:** Rede corporativa com dezenas de VPCs

**Pergunta:** Um parceiro só precisa consumir uma API privada, sem acesso amplo à rede. Qual padrão considerar?

**Resposta:** Exposição de serviço via PrivateLink em arquitetura compatível.

**Saiba mais:** Acesso a serviço pode ser preferível a interligar toda a rede.

**Fonte:** [What is AWS PrivateLink? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html)


## SAA-27-016-C001

**Objetivo:** Redução de custos mantendo requisitos de disponibilidade

**Pergunta:** Uma proposta corta metade da capacidade sem testar o pico e viola a latência exigida. Ela é uma otimização válida?

**Resposta:** Não.

**Saiba mais:** A economia deve preservar o requisito do workload.

**Fonte:** [Select the correct resource type, size, and number - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/select-the-correct-resource-type-size-and-number.html)


## SAA-27-016-C002

**Objetivo:** Redução de custos mantendo requisitos de disponibilidade

**Pergunta:** Uma empresa tem uso estável após eliminar desperdício. Qual próxima alavanca financeira avaliar?

**Resposta:** Compromissos de uso compatíveis, como Savings Plans ou reservas apropriadas.

**Saiba mais:** Não contratar acima da base de uso justificada.

**Fonte:** [What are Savings Plans? - Savings Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html)

