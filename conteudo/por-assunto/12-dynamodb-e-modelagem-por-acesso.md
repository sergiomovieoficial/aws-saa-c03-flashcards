# 12 · DynamoDB e modelagem por acesso

32 cartões · primeira edição · 05/10/2026.


## SAA-12-001-C001

**Objetivo:** Partition key e sort key: selecionar distribuição e consultas

**Pergunta:** Qual é a função da partition key no DynamoDB?

**Resposta:** Participar da identificação e distribuição dos itens.

**Saiba mais:** Uma boa escolha distribui a carga conforme os padrões de acesso.

**Fonte:** [Core components of Amazon DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html)


## SAA-12-001-C002

**Objetivo:** Partition key e sort key: selecionar distribuição e consultas

**Pergunta:** Em uma chave composta, para que serve a sort key?

**Resposta:** Distinguir e ordenar itens com a mesma partition key.

**Saiba mais:** Ela permite consultas por intervalos e condições suportadas dentro da partição lógica.

**Fonte:** [Core components of Amazon DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html)


## SAA-12-002-C001

**Objetivo:** Padrões de acesso: projetar chave antes das consultas

**Pergunta:** Por que definir padrões de acesso antes de criar chaves DynamoDB?

**Resposta:** Porque o modelo de chave e índices determina consultas eficientes.

**Saiba mais:** Não presumir que qualquer filtro arbitrário será barato como uma busca indexada.

**Fonte:** [First steps for modeling relational data in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-modeling-nosql.html)


## SAA-12-002-C002

**Objetivo:** Padrões de acesso: projetar chave antes das consultas

**Pergunta:** Uma chave que concentra quase todas as requisições em um valor pode causar qual problema?

**Resposta:** Uma partição quente.

**Saiba mais:** Capacidade total alta não garante distribuição adequada de tráfego.

**Fonte:** [First steps for modeling relational data in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-modeling-nosql.html)


## SAA-12-003-C001

**Objetivo:** Query e Scan: comparar eficiência e custo

**Pergunta:** Qual operação usa uma partition key específica para recuperar itens relacionados?

**Resposta:** Query.

**Saiba mais:** A sort key pode restringir os resultados conforme as condições suportadas.

**Fonte:** [Querying tables in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html)


## SAA-12-003-C002

**Objetivo:** Query e Scan: comparar eficiência e custo

**Pergunta:** Por que Scan frequente costuma ser inadequado para buscar poucos itens em uma tabela grande?

**Resposta:** Ele examina dados amplamente, consumindo leitura e tempo.

**Saiba mais:** Filtros posteriores não eliminam a leitura já realizada.

**Fonte:** [Scanning tables in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Scan.html)


## SAA-12-004-C001

**Objetivo:** GSI e LSI: escolher índice e reconhecer diferenças

**Pergunta:** Qual índice pode usar uma partition key diferente da tabela base?

**Resposta:** Global secondary index.

**Saiba mais:** Ele oferece outro padrão de acesso, com custos e manutenção próprios.

**Fonte:** [Improving data access with secondary indexes in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html)


## SAA-12-004-C002

**Objetivo:** GSI e LSI: escolher índice e reconhecer diferenças

**Pergunta:** Qual índice mantém a partition key da tabela e altera a possibilidade de sort key?

**Resposta:** Local secondary index.

**Saiba mais:** Seus requisitos e limites diferem dos de GSI.

**Fonte:** [Improving data access with secondary indexes in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html)


## SAA-12-005-C001

**Objetivo:** Leitura forte e eventual: escolher garantia e verificar suporte

**Pergunta:** Um GSI DynamoDB oferece leitura fortemente consistente?

**Resposta:** Não. Leituras de GSI são eventualmente consistentes.

**Saiba mais:** Não generalizar o suporte da tabela e de LSI para GSI.

**Fonte:** [DynamoDB read consistency - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.ReadConsistency.html)


## SAA-12-005-C002

**Objetivo:** Leitura forte e eventual: escolher garantia e verificar suporte

**Pergunta:** Qual trade-off existe ao escolher leitura forte em recursos que a suportam?

**Resposta:** Garantia de leitura mais atual, com consumo de capacidade diferente da eventual.

**Saiba mais:** A escolha deve seguir a necessidade de consistência.

**Fonte:** [DynamoDB read consistency - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.ReadConsistency.html)


## SAA-12-006-C001

**Objetivo:** On-demand e provisioned: selecionar capacidade

**Pergunta:** Qual modo DynamoDB reduz necessidade de provisionar manualmente capacidade para tráfego variável?

**Resposta:** On-demand.

**Saiba mais:** Ainda existem limites e características de adaptação a observar.

**Fonte:** [DynamoDB throughput capacity - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/capacity-mode.html)


## SAA-12-006-C002

**Objetivo:** On-demand e provisioned: selecionar capacidade

**Pergunta:** Quando considerar capacidade provisionada?

**Resposta:** Quando há padrão de uso e gestão de capacidade que justificam essa modalidade.

**Saiba mais:** Comparar custo, previsibilidade e Auto Scaling.

**Fonte:** [DynamoDB throughput capacity - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/capacity-mode.html)


## SAA-12-007-C001

**Objetivo:** Auto Scaling e hot partitions: separar escala global de distribuição

**Pergunta:** Auto Scaling da tabela corrige automaticamente qualquer escolha ruim de partition key?

**Resposta:** Não.

**Saiba mais:** Concentração de tráfego pode exigir remodelagem da distribuição.

**Fonte:** [Best practices for designing and using partition keys effectively in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-partition-key-design.html)


## SAA-12-007-C002

**Objetivo:** Auto Scaling e hot partitions: separar escala global de distribuição

**Pergunta:** Como distribuir gravações muito concentradas mantendo acesso planejado?

**Resposta:** Avaliar uma estratégia de particionamento ou sharding da chave.

**Saiba mais:** A distribuição adicional pode exigir agregação de consultas na aplicação.

**Fonte:** [Best practices for designing and using partition keys effectively in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-partition-key-design.html)


## SAA-12-008-C001

**Objetivo:** Capacidade de leitura e escrita: calcular com premissas explícitas

**Pergunta:** Em leitura forte não transacional, um item de até 4 KB consome quantas unidades de leitura por operação?

**Resposta:** Uma unidade de leitura no modelo de capacidade correspondente.

**Saiba mais:** Arredondamento por tamanho e modalidade da operação importam.

**Fonte:** [DynamoDB read and write operations - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/read-write-operations.html)


## SAA-12-008-C002

**Objetivo:** Capacidade de leitura e escrita: calcular com premissas explícitas

**Pergunta:** Em escrita padrão não transacional, um item de até 1 KB consome quantas unidades de escrita?

**Resposta:** Uma unidade de escrita no modelo correspondente.

**Saiba mais:** Transações têm consumo diferente; não aplicar a regra indistintamente.

**Fonte:** [DynamoDB read and write operations - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/read-write-operations.html)


## SAA-12-009-C001

**Objetivo:** DynamoDB Streams: selecionar processamento de alterações

**Pergunta:** Qual recurso registra alterações de itens DynamoDB para processamento posterior?

**Resposta:** DynamoDB Streams.

**Saiba mais:** O consumidor deve tratar checkpoints, falhas e comportamento de entrega.

**Fonte:** [Change data capture for DynamoDB Streams - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html)


## SAA-12-009-C002

**Objetivo:** DynamoDB Streams: selecionar processamento de alterações

**Pergunta:** Streams transforma automaticamente todo evento em uma ação de negócio concluída exatamente uma vez?

**Resposta:** Não.

**Saiba mais:** O processamento e seus efeitos precisam ser projetados, inclusive quanto à idempotência.

**Fonte:** [Change data capture for DynamoDB Streams - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html)


## SAA-12-010-C001

**Objetivo:** TTL: avaliar expiração e sua semântica

**Pergunta:** TTL no DynamoDB garante exclusão exatamente no segundo configurado?

**Resposta:** Não. A remoção é assíncrona.

**Saiba mais:** Aplicações sensíveis à validade devem interpretar o atributo de expiração.

**Fonte:** [Using time to live (TTL) in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html)


## SAA-12-010-C002

**Objetivo:** TTL: avaliar expiração e sua semântica

**Pergunta:** Qual tipo de dado combina com TTL?

**Resposta:** Itens temporários cuja expiração pode ser gerenciada pelo serviço.

**Saiba mais:** Considerar o comportamento enquanto o item expirado ainda não foi removido.

**Fonte:** [Using time to live (TTL) in DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html)


## SAA-12-011-C001

**Objetivo:** Transações e escritas condicionais: preservar invariantes

**Pergunta:** Para que usar transações DynamoDB?

**Resposta:** Coordenar um conjunto de operações com garantias transacionais suportadas.

**Saiba mais:** Elas têm limites e consumo próprios.

**Fonte:** [Amazon DynamoDB Transactions: How it works - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/transaction-apis.html)


## SAA-12-011-C002

**Objetivo:** Transações e escritas condicionais: preservar invariantes

**Pergunta:** Como evitar sobrescrever um item sem verificar sua versão ou estado esperado?

**Resposta:** Usar escrita condicional adequada.

**Saiba mais:** A condição é avaliada como parte da operação, evitando uma checagem separada sujeita à corrida.

**Fonte:** [DynamoDB condition expression CLI example - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.ConditionExpressions.html)


## SAA-12-012-C001

**Objetivo:** DAX: decidir quando cache atende o padrão de leitura

**Pergunta:** Qual recurso fornece cache compatível com DynamoDB para leituras de baixa latência?

**Resposta:** DynamoDB Accelerator, o DAX.

**Saiba mais:** Avaliar o padrão de leitura e a necessidade de consistência.

**Fonte:** [In-memory acceleration with DynamoDB Accelerator (DAX) - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DAX.html)


## SAA-12-012-C002

**Objetivo:** DAX: decidir quando cache atende o padrão de leitura

**Pergunta:** DAX torna leituras fortes automaticamente leituras servidas do cache?

**Resposta:** Não.

**Saiba mais:** Leituras fortes seguem comportamento próprio e não obtêm o mesmo uso do cache de leituras eventuais.

**Fonte:** [In-memory acceleration with DynamoDB Accelerator (DAX) - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DAX.html)


## SAA-12-013-C001

**Objetivo:** Global Tables: escolher replicação e validar modos de consistência atuais

**Pergunta:** Qual recurso replica tabelas DynamoDB entre regiões?

**Resposta:** Global Tables.

**Saiba mais:** Selecionar o modo e as regiões compatíveis com os requisitos.

**Fonte:** [How DynamoDB global tables work - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/V2globaltables_HowItWorks.html)


## SAA-12-013-C002

**Objetivo:** Global Tables: escolher replicação e validar modos de consistência atuais

**Pergunta:** É correto afirmar que Global Tables só possui consistência eventual em qualquer configuração atual?

**Resposta:** Não.

**Saiba mais:** Há modos de consistência distintos; verificar a modalidade e suas restrições.

**Fonte:** [How DynamoDB global tables work - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/V2globaltables_HowItWorks.html)


## SAA-12-014-C001

**Objetivo:** PITR, backups e exportação: selecionar proteção e análise

**Pergunta:** Qual recurso permite recuperar uma tabela DynamoDB a um ponto dentro da janela disponível?

**Resposta:** Point-in-time recovery.

**Saiba mais:** A recuperação cria uma tabela restaurada; planejar sua integração à aplicação.

**Fonte:** [Point-in-time backups for DynamoDB - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Point-in-time-recovery.html)


## SAA-12-014-C002

**Objetivo:** PITR, backups e exportação: selecionar proteção e análise

**Pergunta:** Qual opção permite exportar dados DynamoDB para análise em S3 sem usar um Scan da aplicação?

**Resposta:** Exportação da tabela para S3 conforme os requisitos do recurso.

**Saiba mais:** O pipeline analítico passa a operar sobre o conjunto exportado.

**Fonte:** [DynamoDB data export to Amazon S3: how it works - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/S3DataExport.HowItWorks.html)


## SAA-12-015-C001

**Objetivo:** Controle de acesso e criptografia: proteger tabelas

**Pergunta:** Criptografia em repouso DynamoDB dispensa controle IAM por tabela?

**Resposta:** Não.

**Saiba mais:** Criptografia e autorização de acesso resolvem aspectos diferentes.

**Fonte:** [DynamoDB encryption at rest - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/EncryptionAtRest.html)


## SAA-12-015-C002

**Objetivo:** Controle de acesso e criptografia: proteger tabelas

**Pergunta:** Qual aspecto revisar ao escolher uma customer managed key para DynamoDB?

**Resposta:** Política, ciclo de vida e disponibilidade da chave.

**Saiba mais:** Desativar a dependência criptográfica pode afetar o acesso aos dados.

**Fonte:** [DynamoDB encryption at rest - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/EncryptionAtRest.html)


## SAA-12-016-C001

**Objetivo:** Idempotência e concorrência: projetar gravações seguras

**Pergunta:** Qual técnica evita atualizar silenciosamente um item que mudou desde sua leitura?

**Resposta:** Controle de concorrência otimista com versão e condição.

**Saiba mais:** Uma falha de condição deve ser tratada pela aplicação.

**Fonte:** [DynamoDB and optimistic locking with version number - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBMapper.OptimisticLocking.html)


## SAA-12-016-C002

**Objetivo:** Idempotência e concorrência: projetar gravações seguras

**Pergunta:** Por que um consumidor que grava no DynamoDB precisa pensar em idempotência?

**Resposta:** A mesma solicitação pode ser repetida após falha ou retry.

**Saiba mais:** Usar uma chave ou condição de deduplicação pode impedir efeitos duplicados.

**Fonte:** [DynamoDB and optimistic locking with version number - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBMapper.OptimisticLocking.html)

