# 10 · Bancos relacionais, cache e bancos especializados

44 cartões · primeira edição · 05/10/2026.


## SAA-10-001-C001

**Objetivo:** Relacional e NoSQL: escolher por acesso, relações e transações

**Pergunta:** Um sistema exige relações complexas e consultas SQL transacionais. Qual família de banco avaliar primeiro?

**Resposta:** Banco relacional.

**Saiba mais:** O requisito de consulta e integridade pesa mais que popularidade do serviço.

**Fonte:** [AWS Database category iconDatabases - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/database.html)


## SAA-10-001-C002

**Objetivo:** Relacional e NoSQL: escolher por acesso, relações e transações

**Pergunta:** Uma aplicação tem consultas previsíveis por chave e grande necessidade de escala. Qual opção AWS considerar?

**Resposta:** DynamoDB, se seu modelo atender aos padrões de acesso.

**Saiba mais:** NoSQL não significa ausência de modelagem; a chave é parte central do desenho.

**Fonte:** [AWS Database category iconDatabases - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/database.html)


## SAA-10-002-C001

**Objetivo:** RDS: responsabilidades gerenciadas e controles do cliente

**Pergunta:** Qual atividade RDS reduz em comparação a instalar um banco diretamente em EC2?

**Resposta:** Administração de infraestrutura e tarefas gerenciadas do banco, conforme os recursos utilizados.

**Saiba mais:** O cliente ainda projeta esquema, consultas, permissões e configuração.

**Fonte:** [What is Amazon Relational Database Service (Amazon RDS)? - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)


## SAA-10-002-C002

**Objetivo:** RDS: responsabilidades gerenciadas e controles do cliente

**Pergunta:** RDS permite administrar livremente o sistema operacional subjacente como em EC2?

**Resposta:** Não no modelo gerenciado padrão.

**Saiba mais:** Requisitos de acesso ao host podem mudar a escolha de serviço.

**Fonte:** [What is Amazon Relational Database Service (Amazon RDS)? - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)


## SAA-10-003-C001

**Objetivo:** RDS Multi-AZ DB instance: avaliar disponibilidade

**Pergunta:** A standby de um RDS Multi-AZ DB instance tradicional atende consultas de leitura?

**Resposta:** Não.

**Saiba mais:** Sua finalidade é disponibilidade e failover; não confundir com read replica.

**Fonte:** [Multi-AZ DB instance deployments for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html)


## SAA-10-003-C002

**Objetivo:** RDS Multi-AZ DB instance: avaliar disponibilidade

**Pergunta:** Qual é o objetivo principal de Multi-AZ DB instance com uma standby?

**Resposta:** Reduzir indisponibilidade por falha da instância ou AZ conforme o mecanismo de failover.

**Saiba mais:** Isso não significa executar mais consultas de leitura na standby.

**Fonte:** [Multi-AZ DB instance deployments for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html)


## SAA-10-004-C001

**Objetivo:** RDS Multi-AZ DB cluster: distinguir topologia e capacidade de leitura

**Pergunta:** Um RDS Multi-AZ DB cluster tem o mesmo comportamento de leitura da standby tradicional de DB instance?

**Resposta:** Não. O cluster possui instâncias leitoras utilizáveis.

**Saiba mais:** Sempre identificar a modalidade antes de responder sobre leitura em Multi-AZ.

**Fonte:** [Multi-AZ DB cluster deployments for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/multi-az-db-clusters-concepts.html)


## SAA-10-004-C002

**Objetivo:** RDS Multi-AZ DB cluster: distinguir topologia e capacidade de leitura

**Pergunta:** Por que a frase toda implantação RDS Multi-AZ não atende leituras nas secundárias é incorreta?

**Resposta:** Porque generaliza o modelo tradicional para modalidades diferentes.

**Saiba mais:** RDS Multi-AZ DB cluster e Aurora têm arquiteturas próprias.

**Fonte:** [Multi-AZ DB cluster deployments for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/multi-az-db-clusters-concepts.html)


## SAA-10-005-C001

**Objetivo:** RDS read replicas: avaliar escala de leitura e promoção

**Pergunta:** Qual recurso RDS pode reduzir carga de leitura no banco de origem?

**Resposta:** Read replicas.

**Saiba mais:** A aplicação precisa direcionar leituras aos endpoints apropriados.

**Fonte:** [Working with DB instance read replicas - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)


## SAA-10-005-C002

**Objetivo:** RDS read replicas: avaliar escala de leitura e promoção

**Pergunta:** Qual risco de consistência avaliar ao ler de uma read replica com replicação assíncrona?

**Resposta:** Replication lag.

**Saiba mais:** Uma gravação recente pode ainda não estar visível na réplica.

**Fonte:** [Working with DB instance read replicas - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)


## SAA-10-005-C003

**Objetivo:** RDS read replicas: avaliar escala de leitura e promoção

**Pergunta:** Promover uma read replica é equivalente a continuar mantendo-a como réplica do mesmo primário?

**Resposta:** Não.

**Saiba mais:** A promoção muda seu papel; planejar a aplicação e a continuidade da replicação.

**Fonte:** [Working with DB instance read replicas - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)


## SAA-10-006-C001

**Objetivo:** RDS backups automáticos, snapshots e PITR: selecionar recuperação

**Pergunta:** O que permite recuperar um banco a um instante dentro da janela suportada de backups automáticos?

**Resposta:** Point-in-time recovery.

**Saiba mais:** A recuperação cria uma instância conforme o fluxo de restauração, não desfaz consultas no banco atual.

**Fonte:** [Introduction to backups - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html)


## SAA-10-006-C002

**Objetivo:** RDS backups automáticos, snapshots e PITR: selecionar recuperação

**Pergunta:** Um snapshot manual substitui automaticamente uma janela contínua de recuperação ponto a ponto?

**Resposta:** Não.

**Saiba mais:** Ele representa um ponto específico de proteção.

**Fonte:** [Introduction to backups - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html)


## SAA-10-007-C001

**Objetivo:** RDS storage e IOPS: dimensionar por gargalo

**Pergunta:** CPU baixa com alta espera de disco sugere investigar qual dimensão do RDS?

**Resposta:** IOPS, throughput e latência de armazenamento.

**Saiba mais:** Aumentar CPU pode não resolver um gargalo de I/O.

**Fonte:** [Amazon RDS DB instance storage - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html)


## SAA-10-007-C002

**Objetivo:** RDS storage e IOPS: dimensionar por gargalo

**Pergunta:** Auto scaling de storage RDS deve ser confundido com redução automática de tamanho quando o uso cai?

**Resposta:** Não.

**Saiba mais:** Capacidade de expansão não implica redução automática.

**Fonte:** [Amazon RDS DB instance storage - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html)


## SAA-10-008-C001

**Objetivo:** RDS Proxy: gerenciar conexões de aplicações

**Pergunta:** Qual recurso pode reduzir pressão de muitas conexões curtas de funções serverless ao banco?

**Resposta:** RDS Proxy.

**Saiba mais:** O pooling ajuda a gerenciar conexões sem transformar o banco em capacidade infinita.

**Fonte:** [Amazon RDS Proxy - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-proxy.html)


## SAA-10-008-C002

**Objetivo:** RDS Proxy: gerenciar conexões de aplicações

**Pergunta:** RDS Proxy elimina a necessidade de otimizar consultas lentas?

**Resposta:** Não.

**Saiba mais:** Pooling de conexões e desempenho das consultas são problemas distintos.

**Fonte:** [Amazon RDS Proxy - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-proxy.html)


## SAA-10-009-C001

**Objetivo:** Aurora: storage distribuído e arquitetura de cluster

**Pergunta:** No Aurora, computação e armazenamento formam necessariamente um disco local único de uma instância?

**Resposta:** Não. A arquitetura separa instâncias e armazenamento de cluster distribuído.

**Saiba mais:** Essa separação é importante para compreender réplicas e recuperação.

**Fonte:** [Amazon Aurora DB clusters - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.html)


## SAA-10-009-C002

**Objetivo:** Aurora: storage distribuído e arquitetura de cluster

**Pergunta:** Por que não descrever Aurora simplesmente como um RDS comum com uma standby tradicional?

**Resposta:** Seu armazenamento, endpoints e réplicas seguem arquitetura específica.

**Saiba mais:** A modalidade do serviço muda a resposta correta em cenários.

**Fonte:** [Amazon Aurora DB clusters - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.html)


## SAA-10-010-C001

**Objetivo:** Aurora writer, reader e instance endpoints: rotear clientes

**Pergunta:** Qual endpoint Aurora aponta para a instância primária para operações de escrita?

**Resposta:** O cluster endpoint, também chamado writer endpoint.

**Saiba mais:** A aplicação evita fixar o endereço de uma instância que pode mudar de papel.

**Fonte:** [Amazon Aurora endpoint connections - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Endpoints.html)


## SAA-10-010-C002

**Objetivo:** Aurora writer, reader e instance endpoints: rotear clientes

**Pergunta:** Qual finalidade do reader endpoint do Aurora?

**Resposta:** Distribuir conexões de leitura entre réplicas apropriadas.

**Saiba mais:** Distribuição de conexões não significa balanceamento de cada consulta dentro de uma conexão.

**Fonte:** [Amazon Aurora endpoint connections - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Endpoints.html)


## SAA-10-011-C001

**Objetivo:** Aurora Replicas e failover: escolher continuidade e leitura

**Pergunta:** Qual papel uma Aurora Replica pode desempenhar além de atender leituras?

**Resposta:** Ser candidata à promoção em um failover.

**Saiba mais:** Planejar prioridade e capacidade para suportar a função de writer.

**Fonte:** [Replication with Amazon Aurora - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Replication.html)


## SAA-10-011-C002

**Objetivo:** Aurora Replicas e failover: escolher continuidade e leitura

**Pergunta:** Uma aplicação que usa endereço fixo da instância evita todos os problemas de failover?

**Resposta:** Não.

**Saiba mais:** É necessário usar endpoints apropriados e tratar reconexão.

**Fonte:** [Replication with Amazon Aurora - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Replication.html)


## SAA-10-012-C001

**Objetivo:** Aurora Global Database: analisar cenários entre regiões

**Pergunta:** Qual recurso Aurora foi desenhado para bancos distribuídos em múltiplas regiões com recuperação regional?

**Resposta:** Aurora Global Database.

**Saiba mais:** É necessário entender o fluxo de replicação e os papéis regionais.

**Fonte:** [Using Amazon Aurora Global Database - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database.html)


## SAA-10-012-C002

**Objetivo:** Aurora Global Database: analisar cenários entre regiões

**Pergunta:** Aurora Global Database significa aceitar escrita independente em qualquer região sem considerar configuração e modo?

**Resposta:** Não.

**Saiba mais:** O caminho de escrita e recursos como encaminhamento devem ser avaliados explicitamente.

**Fonte:** [Using Amazon Aurora Global Database - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database.html)


## SAA-10-013-C001

**Objetivo:** Aurora Serverless v2: avaliar carga variável

**Pergunta:** Qual característica central do Aurora Serverless v2 atende demanda variável?

**Resposta:** Ajuste de capacidade de computação dentro da configuração suportada.

**Saiba mais:** Não confundir escalabilidade com eliminação de todos os custos ou limites.

**Fonte:** [Using Aurora serverless - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.html)


## SAA-10-013-C002

**Objetivo:** Aurora Serverless v2: avaliar carga variável

**Pergunta:** Aurora Serverless v2 dispensa planejamento de conexões e consultas?

**Resposta:** Não.

**Saiba mais:** A aplicação ainda pode atingir limites ou usar o banco de forma ineficiente.

**Fonte:** [Using Aurora serverless - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.html)


## SAA-10-014-C001

**Objetivo:** Aurora provisionado e serverless: comparar requisitos e custos

**Pergunta:** Ao comparar Aurora provisionado e Serverless v2, quais aspectos de demanda importam?

**Resposta:** Estabilidade, amplitude dos picos e capacidade mínima necessária.

**Saiba mais:** A opção mais barata depende do uso real e da configuração.

**Fonte:** [How Aurora serverless works - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.how-it-works.html)


## SAA-10-014-C002

**Objetivo:** Aurora provisionado e serverless: comparar requisitos e custos

**Pergunta:** É correto afirmar que qualquer Aurora Serverless sempre escala a zero?

**Resposta:** Não.

**Saiba mais:** Suporte, versão e configuração precisam ser conferidos; não generalizar entre modalidades.

**Fonte:** [How Aurora serverless works - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.how-it-works.html)


## SAA-10-015-C001

**Objetivo:** ElastiCache: selecionar cache para reduzir latência

**Pergunta:** Quando um cache pode reduzir latência de consultas ao banco?

**Resposta:** Quando resultados reutilizáveis podem ser atendidos em memória.

**Saiba mais:** Definir validade e atualização para não servir dados além da tolerância.

**Fonte:** [What is Amazon ElastiCache? - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/WhatIs.html)


## SAA-10-015-C002

**Objetivo:** ElastiCache: selecionar cache para reduzir latência

**Pergunta:** Cache elimina a necessidade de um banco persistente em todo cenário?

**Resposta:** Não.

**Saiba mais:** O papel de armazenamento durável depende da arquitetura e do produto escolhido.

**Fonte:** [What is Amazon ElastiCache? - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/WhatIs.html)


## SAA-10-016-C001

**Objetivo:** Cache-aside e write-through: comparar atualização e falha

**Pergunta:** No padrão cache-aside, o que ocorre após um cache miss?

**Resposta:** A aplicação consulta a origem e pode preencher o cache.

**Saiba mais:** A estratégia demanda controle de expiração e invalidação.

**Fonte:** [Caching strategies for Memcached - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/Strategies.html)


## SAA-10-016-C002

**Objetivo:** Cache-aside e write-through: comparar atualização e falha

**Pergunta:** Qual diferença de write-through em relação a preencher cache apenas após leitura?

**Resposta:** A atualização do cache acompanha a escrita no fluxo projetado.

**Saiba mais:** O objetivo é reduzir misses futuros, com custo adicional no caminho de atualização.

**Fonte:** [Caching strategies for Memcached - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/Strategies.html)


## SAA-10-017-C001

**Objetivo:** TTL, invalidação e cache stampede: avaliar consistência do cache

**Pergunta:** Qual trade-off existe ao aumentar TTL de dados em cache?

**Resposta:** Mais reutilização, com maior risco de servir dados desatualizados.

**Saiba mais:** A tolerância de negócio define a validade aceitável.

**Fonte:** [Cache Validity - Database Caching Strategies Using Redis](https://docs.aws.amazon.com/whitepapers/latest/database-caching-strategies-using-redis/cache-validity.html)


## SAA-10-017-C002

**Objetivo:** TTL, invalidação e cache stampede: avaliar consistência do cache

**Pergunta:** O que é cache stampede?

**Resposta:** Muitos clientes recomputarem ou consultarem a origem ao mesmo tempo após expiração ou miss.

**Saiba mais:** Jitter, coordenação e estratégias de atualização podem reduzir o pico.

**Fonte:** [Cache Validity - Database Caching Strategies Using Redis](https://docs.aws.amazon.com/whitepapers/latest/database-caching-strategies-using-redis/cache-validity.html)


## SAA-10-018-C001

**Objetivo:** Redis OSS/Valkey e Memcached: comparar necessidades do cenário

**Pergunta:** Por que a escolha entre motores de cache precisa considerar mais que velocidade?

**Resposta:** Estruturas de dados, replicação, persistência e operação diferem.

**Saiba mais:** Selecionar o motor a partir das capacidades exigidas.

**Fonte:** [Comparing node-based Valkey, Memcached, and Redis OSS clusters - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/SelectEngine.html)


## SAA-10-018-C002

**Objetivo:** Redis OSS/Valkey e Memcached: comparar necessidades do cenário

**Pergunta:** Uma aplicação precisa de estruturas como conjuntos ordenados. O tipo de dado influencia a escolha do cache?

**Resposta:** Sim.

**Saiba mais:** Um cache simples chave-valor pode não oferecer as operações necessárias.

**Fonte:** [Comparing node-based Valkey, Memcached, and Redis OSS clusters - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/SelectEngine.html)


## SAA-10-019-C001

**Objetivo:** DocumentDB, Neptune e Keyspaces: reconhecer modelos de dados

**Pergunta:** Qual banco AWS avaliar para relações e consultas em grafos?

**Resposta:** Amazon Neptune.

**Saiba mais:** O modelo é útil quando conexões entre entidades são centrais.

**Fonte:** [What Is Amazon Neptune? - Amazon Neptune](https://docs.aws.amazon.com/neptune/latest/userguide/intro.html)


## SAA-10-019-C002

**Objetivo:** DocumentDB, Neptune e Keyspaces: reconhecer modelos de dados

**Pergunta:** Qual serviço AWS é voltado a banco de documentos com compatibilidade de APIs MongoDB suportadas?

**Resposta:** Amazon DocumentDB.

**Saiba mais:** Compatibilidade deve ser verificada para recursos e versões da aplicação.

**Fonte:** [What is Amazon DocumentDB (with MongoDB compatibility) - Amazon DocumentDB](https://docs.aws.amazon.com/documentdb/latest/developerguide/what-is.html)


## SAA-10-019-C003

**Objetivo:** DocumentDB, Neptune e Keyspaces: reconhecer modelos de dados

**Pergunta:** Qual serviço gerenciado atende workloads compatíveis com Apache Cassandra?

**Resposta:** Amazon Keyspaces.

**Saiba mais:** O foco é o modelo e a interface Cassandra suportada.

**Fonte:** [What is Amazon Keyspaces (for Apache Cassandra)? - Amazon Keyspaces (for Apache Cassandra)](https://docs.aws.amazon.com/keyspaces/latest/devguide/what-is-keyspaces.html)


## SAA-10-020-C001

**Objetivo:** RDS em subnets privadas e acesso por IAM: planejar proteção

**Pergunta:** IAM database authentication concede automaticamente autorização para todas as tabelas do banco?

**Resposta:** Não.

**Saiba mais:** Autenticação no banco e privilégios internos de consulta são controles diferentes.

**Fonte:** [IAM database authentication for MariaDB, MySQL, and PostgreSQL - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.html)


## SAA-10-020-C002

**Objetivo:** RDS em subnets privadas e acesso por IAM: planejar proteção

**Pergunta:** Por que manter RDS privado quando só a aplicação precisa acessá-lo?

**Resposta:** Para limitar a superfície de exposição de rede.

**Saiba mais:** Ainda é necessário configurar SGs, autenticação e permissões no banco.

**Fonte:** [IAM database authentication for MariaDB, MySQL, and PostgreSQL - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.html)


## SAA-10-021-C001

**Objetivo:** Licenciamento, retenção e réplicas: identificar fatores de custo

**Pergunta:** Por que réplicas ociosas e backups retidos precisam entrar na análise de custo?

**Resposta:** Eles podem gerar cobrança mesmo sem aumentar o uso útil da aplicação.

**Saiba mais:** O custo total inclui mais que a instância primária.

**Fonte:** [Managed Relational Database - Amazon RDS Pricing - Amazon Web Services](https://aws.amazon.com/rds/pricing/)


## SAA-10-021-C002

**Objetivo:** Licenciamento, retenção e réplicas: identificar fatores de custo

**Pergunta:** Uma mudança de engine pode reduzir custo sem qualquer análise funcional?

**Resposta:** Não.

**Saiba mais:** Compatibilidade, licenciamento, migração e desempenho devem ser avaliados.

**Fonte:** [Managed Relational Database - Amazon RDS Pricing - Amazon Web Services](https://aws.amazon.com/rds/pricing/)

