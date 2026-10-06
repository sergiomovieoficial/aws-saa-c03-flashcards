# 18 · Ingestão, análise e transformação de dados

38 cartões · primeira edição · 05/10/2026.


## SAA-18-001-C001

**Objetivo:** Batch e streaming: selecionar padrão por latência

**Pergunta:** Qual diferença de requisito distingue processamento batch de streaming?

**Resposta:** O prazo para processar dados e a forma como chegam.

**Saiba mais:** Streaming lida com fluxo contínuo; batch agrupa trabalho em conjuntos.

**Fonte:** [AWS Analytics category iconAnalytics - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/analytics.html)


## SAA-18-001-C002

**Objetivo:** Batch e streaming: selecionar padrão por latência

**Pergunta:** Relatório diário exige necessariamente uma plataforma de streaming de baixa latência?

**Resposta:** Não.

**Saiba mais:** Uma solução em lote pode atender com menor complexidade.

**Fonte:** [AWS Analytics category iconAnalytics - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/analytics.html)


## SAA-18-002-C001

**Objetivo:** Kinesis Data Streams: shards, partições e consumidores

**Pergunta:** Qual papel de um shard em Kinesis Data Streams provisionado?

**Resposta:** Fornecer uma unidade de capacidade e particionamento do stream.

**Saiba mais:** A distribuição das partition keys influencia o uso da capacidade.

**Fonte:** [Amazon Kinesis Data Streams Terminology and concepts - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)


## SAA-18-002-C002

**Objetivo:** Kinesis Data Streams: shards, partições e consumidores

**Pergunta:** Uma partition key única para todo o tráfego pode concentrar carga em Kinesis?

**Resposta:** Sim.

**Saiba mais:** Distribuir chaves de forma adequada ajuda a evitar pontos quentes.

**Fonte:** [Amazon Kinesis Data Streams Terminology and concepts - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)


## SAA-18-003-C001

**Objetivo:** Capacidade provisionada e on-demand em streams

**Pergunta:** Qual escolha de capacidade Kinesis reduz a necessidade de dimensionar shards manualmente?

**Resposta:** On-demand, conforme as características e limites do serviço.

**Saiba mais:** Ainda é preciso observar comportamento de picos e distribuição.

**Fonte:** [Choose the right mode to stream in - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/how-do-i-size-a-stream.html)


## SAA-18-003-C002

**Objetivo:** Capacidade provisionada e on-demand em streams

**Pergunta:** Quando capacidade provisionada pode ser interessante em streaming?

**Resposta:** Quando a demanda é conhecida e o dimensionamento controlado atende custo e desempenho.

**Saiba mais:** Comparar uso real e margem de crescimento.

**Fonte:** [Choose the right mode to stream in - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/how-do-i-size-a-stream.html)


## SAA-18-004-C001

**Objetivo:** Ordem por chave e distribuição de eventos

**Pergunta:** Por que escolher partition keys de streaming a partir da unidade que precisa de ordem?

**Resposta:** A distribuição e a ordenação dependem do particionamento.

**Saiba mais:** Preservar ordem para uma entidade não exige uma única partição para toda a empresa.

**Fonte:** [Amazon Kinesis Data Streams Terminology and concepts - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)


## SAA-18-004-C002

**Objetivo:** Ordem por chave e distribuição de eventos

**Pergunta:** Mais shards resolvem automaticamente um produtor que usa sempre a mesma chave quente?

**Resposta:** Não necessariamente.

**Saiba mais:** A distribuição lógica continua podendo concentrar eventos.

**Fonte:** [Amazon Kinesis Data Streams Terminology and concepts - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)


## SAA-18-005-C001

**Objetivo:** Retenção, replay e consumidores independentes

**Pergunta:** Por que retenção de um stream é útil a consumidores independentes?

**Resposta:** Permite ler ou reler eventos dentro da janela disponível.

**Saiba mais:** Cada consumidor gerencia seu progresso conforme a arquitetura.

**Fonte:** [What is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)


## SAA-18-005-C002

**Objetivo:** Retenção, replay e consumidores independentes

**Pergunta:** Qual diferença de uso existe entre stream retido e fila com exclusão após processamento?

**Resposta:** O stream permite múltiplas leituras independentes do histórico retido.

**Saiba mais:** Selecionar o mecanismo conforme o modelo de consumo.

**Fonte:** [What is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)


## SAA-18-006-C001

**Objetivo:** Amazon Data Firehose: entrega gerenciada e transformação

**Pergunta:** Qual serviço entrega dados de streaming a destinos suportados com gerenciamento de entrega?

**Resposta:** Amazon Data Firehose.

**Saiba mais:** Pode oferecer buffering, transformação e conversão conforme configuração.

**Fonte:** [What is Amazon Data Firehose? - Amazon Data Firehose](https://docs.aws.amazon.com/firehose/latest/dev/what-is-this-service.html)


## SAA-18-006-C002

**Objetivo:** Amazon Data Firehose: entrega gerenciada e transformação

**Pergunta:** Firehose deve ser presumido como entrega instantânea sem buffering em todo cenário?

**Resposta:** Não.

**Saiba mais:** Latência e buffering dependem da configuração e do destino.

**Fonte:** [What is Amazon Data Firehose? - Amazon Data Firehose](https://docs.aws.amazon.com/firehose/latest/dev/what-is-this-service.html)


## SAA-18-007-C001

**Objetivo:** Streams e Firehose: comparar controle e destino

**Pergunta:** Uma aplicação precisa de consumidores próprios e replay de um stream. Qual opção considerar em vez de apenas entrega gerenciada?

**Resposta:** Kinesis Data Streams.

**Saiba mais:** Firehose e Streams podem inclusive participar da mesma arquitetura com papéis diferentes.

**Fonte:** [What is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)


## SAA-18-007-C002

**Objetivo:** Streams e Firehose: comparar controle e destino

**Pergunta:** Selecionar Firehose remove a necessidade de definir destino e tratamento de falhas?

**Resposta:** Não.

**Saiba mais:** O pipeline precisa de configuração de entrega, acesso e recuperação.

**Fonte:** [What is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)


## SAA-18-008-C001

**Objetivo:** MSK: escolher Kafka gerenciado por compatibilidade

**Pergunta:** Qual serviço atende workloads que precisam de Apache Kafka gerenciado?

**Resposta:** Amazon MSK.

**Saiba mais:** Compatibilidade com o ecossistema Kafka pode orientar a decisão.

**Fonte:** [Welcome to the Amazon MSK Developer Guide - Amazon Managed Streaming for Apache Kafka](https://docs.aws.amazon.com/msk/latest/developerguide/what-is-msk.html)


## SAA-18-008-C002

**Objetivo:** MSK: escolher Kafka gerenciado por compatibilidade

**Pergunta:** Kafka gerenciado torna dispensável planejar tópicos, partições e consumidores?

**Resposta:** Não.

**Saiba mais:** O modelo da aplicação continua influenciando escala e ordenação.

**Fonte:** [Welcome to the Amazon MSK Developer Guide - Amazon Managed Streaming for Apache Kafka](https://docs.aws.amazon.com/msk/latest/developerguide/what-is-msk.html)


## SAA-18-009-C001

**Objetivo:** Glue ETL, crawlers e Data Catalog: distinguir componentes

**Pergunta:** Qual serviço fornece ETL gerenciado e catálogo de metadados para dados analíticos?

**Resposta:** AWS Glue.

**Saiba mais:** Jobs de transformação e Data Catalog têm funções distintas.

**Fonte:** [What is AWS Glue? - AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html)


## SAA-18-009-C002

**Objetivo:** Glue ETL, crawlers e Data Catalog: distinguir componentes

**Pergunta:** Qual papel de um Glue crawler?

**Resposta:** Descobrir estrutura e atualizar metadados de fontes suportadas.

**Saiba mais:** Crawler não substitui automaticamente a transformação dos dados.

**Fonte:** [What is AWS Glue? - AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html)


## SAA-18-010-C001

**Objetivo:** Athena: analisar dados em S3 com SQL

**Pergunta:** Qual serviço permite consultar dados no S3 usando SQL sem administrar servidores de consulta?

**Resposta:** Amazon Athena.

**Saiba mais:** O formato, particionamento e quantidade lida influenciam custo e desempenho.

**Fonte:** [What is Amazon Athena? - Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/what-is.html)


## SAA-18-010-C002

**Objetivo:** Athena: analisar dados em S3 com SQL

**Pergunta:** Athena exige copiar todo dataset para um banco transacional RDS antes de consultar?

**Resposta:** Não.

**Saiba mais:** Ele pode consultar dados no storage suportado conforme o catálogo e os conectores utilizados.

**Fonte:** [What is Amazon Athena? - Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/what-is.html)


## SAA-18-011-C001

**Objetivo:** Particionamento, compressão e Parquet: reduzir varredura

**Pergunta:** Como particionamento pode reduzir custo de consultas analíticas?

**Resposta:** Permite ler apenas as partições relevantes quando o filtro aproveita a organização.

**Saiba mais:** Particionar mal também pode introduzir complexidade e sobrecarga.

**Fonte:** [Optimize data - Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/performance-tuning-data-optimization-techniques.html)


## SAA-18-011-C002

**Objetivo:** Particionamento, compressão e Parquet: reduzir varredura

**Pergunta:** Por que um formato colunar como Parquet favorece consultas que leem poucas colunas?

**Resposta:** Permite evitar leitura de colunas desnecessárias.

**Saiba mais:** Compressão e organização dos arquivos também influenciam.

**Fonte:** [Optimize data - Amazon Athena](https://docs.aws.amazon.com/athena/latest/ug/performance-tuning-data-optimization-techniques.html)


## SAA-18-012-C001

**Objetivo:** Lake Formation: selecionar governança de data lake

**Pergunta:** Qual serviço ajuda a governar acesso a dados de um data lake AWS?

**Resposta:** AWS Lake Formation.

**Saiba mais:** A integração com serviços consumidores e políticas precisa ser configurada.

**Fonte:** [What is AWS Lake Formation? - AWS Lake Formation](https://docs.aws.amazon.com/lake-formation/latest/dg/what-is-lake-formation.html)


## SAA-18-012-C002

**Objetivo:** Lake Formation: selecionar governança de data lake

**Pergunta:** Governança do catálogo dispensa qualquer controle sobre o armazenamento subjacente?

**Resposta:** Não.

**Saiba mais:** As camadas de autorização devem ser coerentes.

**Fonte:** [What is AWS Lake Formation? - AWS Lake Formation](https://docs.aws.amazon.com/lake-formation/latest/dg/what-is-lake-formation.html)


## SAA-18-013-C001

**Objetivo:** EMR: avaliar processamento distribuído

**Pergunta:** Qual serviço AWS atende processamento distribuído com frameworks como Spark?

**Resposta:** Amazon EMR.

**Saiba mais:** Escolher a modalidade de execução conforme operação e demanda.

**Fonte:** [What is Amazon EMR? - Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html)


## SAA-18-013-C002

**Objetivo:** EMR: avaliar processamento distribuído

**Pergunta:** Um pequeno relatório SQL simples exige necessariamente um cluster EMR?

**Resposta:** Não.

**Saiba mais:** Athena ou outra opção adequada pode reduzir esforço operacional.

**Fonte:** [What is Amazon EMR? - Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html)


## SAA-18-014-C001

**Objetivo:** Redshift e Redshift Spectrum: escolher análise de dados

**Pergunta:** Qual serviço é voltado a data warehouse analítico na AWS?

**Resposta:** Amazon Redshift.

**Saiba mais:** Seu papel é diferente de um banco operacional de transações curtas.

**Fonte:** [What is Amazon Redshift? - Amazon Redshift](https://docs.aws.amazon.com/redshift/latest/mgmt/welcome.html)


## SAA-18-014-C002

**Objetivo:** Redshift e Redshift Spectrum: escolher análise de dados

**Pergunta:** Qual recurso Redshift permite consultar dados externos no S3 sem carregar tudo em tabelas locais?

**Resposta:** Redshift Spectrum.

**Saiba mais:** O desenho pode combinar dados internos e externos conforme o caso.

**Fonte:** [Amazon Redshift Spectrum - Amazon Redshift](https://docs.aws.amazon.com/redshift/latest/dg/c-using-spectrum.html)


## SAA-18-015-C001

**Objetivo:** OpenSearch Service: avaliar busca e análise de logs

**Pergunta:** Qual serviço avaliar para busca textual e análise de logs baseada em índices de busca?

**Resposta:** Amazon OpenSearch Service.

**Saiba mais:** Não é automaticamente a escolha para qualquer transação relacional.

**Fonte:** [What is Amazon OpenSearch Service? - Amazon OpenSearch Service](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/what-is.html)


## SAA-18-015-C002

**Objetivo:** OpenSearch Service: avaliar busca e análise de logs

**Pergunta:** Por que retenção de índices e dimensionamento precisam entrar no desenho de logs?

**Resposta:** Dados e consultas acumulados consomem armazenamento e computação.

**Saiba mais:** O valor operacional do histórico deve orientar sua retenção.

**Fonte:** [What is Amazon OpenSearch Service? - Amazon OpenSearch Service](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/what-is.html)


## SAA-18-016-C001

**Objetivo:** Visualização com Amazon Quick: conferir nome e escopo vigentes

**Pergunta:** Qual recurso AWS de BI, conhecido como QuickSight em materiais de estudo, atende dashboards e visualização de dados?

**Resposta:** Amazon Quick Sight, o recurso de BI do Amazon Quick.

**Saiba mais:** O nome QuickSight aparece em materiais anteriores; a decisão arquitetural é selecionar a ferramenta de BI para análise visual e dashboards.

**Fonte:** [Getting started with Amazon Quick Sight - Amazon Quick](https://docs.aws.amazon.com/quick/latest/userguide/quick-sight-getting-started.html)


## SAA-18-016-C002

**Objetivo:** Visualização com Amazon Quick: conferir nome e escopo vigentes

**Pergunta:** Criar um dashboard resolve por si só ingestão e qualidade dos dados de origem?

**Resposta:** Não.

**Saiba mais:** Visualização depende de dados disponíveis e confiáveis no pipeline.

**Fonte:** [Getting started with Amazon Quick Sight - Amazon Quick](https://docs.aws.amazon.com/quick/latest/userguide/quick-sight-getting-started.html)


## SAA-18-017-C001

**Objetivo:** Data Exchange: reconhecer compartilhamento de conjuntos de dados

**Pergunta:** Qual serviço AWS atende descoberta e uso de produtos de dados de provedores?

**Resposta:** AWS Data Exchange.

**Saiba mais:** Verificar licença, acesso e forma de entrega do produto.

**Fonte:** [What is AWS Data Exchange? - AWS Data Exchange User Guide](https://docs.aws.amazon.com/data-exchange/latest/userguide/what-is.html)


## SAA-18-017-C002

**Objetivo:** Data Exchange: reconhecer compartilhamento de conjuntos de dados

**Pergunta:** Adquirir acesso a um dataset define automaticamente seu pipeline analítico?

**Resposta:** Não.

**Saiba mais:** Integração, atualização e governança continuam necessárias.

**Fonte:** [What is AWS Data Exchange? - AWS Data Exchange User Guide](https://docs.aws.amazon.com/data-exchange/latest/userguide/what-is.html)


## SAA-18-018-C001

**Objetivo:** Kinesis Video Streams: reconhecer ingestão de vídeo

**Pergunta:** Qual serviço Kinesis é específico para ingestão e processamento de streams de vídeo?

**Resposta:** Kinesis Video Streams.

**Saiba mais:** Não confundir com os registros genéricos de Data Streams.

**Fonte:** [What is Amazon Kinesis Video Streams? - Amazon Kinesis Video Streams](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/what-is-kinesis-video.html)


## SAA-18-018-C002

**Objetivo:** Kinesis Video Streams: reconhecer ingestão de vídeo

**Pergunta:** Um pipeline de vídeo precisa considerar apenas armazenamento bruto?

**Resposta:** Não.

**Saiba mais:** Latência, retenção, consumidores e acesso também orientam o desenho.

**Fonte:** [What is Amazon Kinesis Video Streams? - Amazon Kinesis Video Streams](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/what-is-kinesis-video.html)


## SAA-18-019-C001

**Objetivo:** Custos e segurança de pipeline: avaliar percurso completo

**Pergunta:** Onde aplicar menor privilégio em um pipeline de dados?

**Resposta:** Em cada produtor, etapa de transformação, armazenamento e consumidor.

**Saiba mais:** Proteger apenas o bucket final não cobre todo o fluxo.

**Fonte:** [Data Analytics Lens - Data Analytics Lens](https://docs.aws.amazon.com/wellarchitected/latest/analytics-lens/analytics-lens.html)


## SAA-18-019-C002

**Objetivo:** Custos e segurança de pipeline: avaliar percurso completo

**Pergunta:** Por que medir custo por etapa de um pipeline?

**Resposta:** Para identificar onde volume, processamento ou transferência geram desperdício.

**Saiba mais:** A maior conta pode estar fora do serviço inicialmente suspeito.

**Fonte:** [Data Analytics Lens - Data Analytics Lens](https://docs.aws.amazon.com/wellarchitected/latest/analytics-lens/analytics-lens.html)

