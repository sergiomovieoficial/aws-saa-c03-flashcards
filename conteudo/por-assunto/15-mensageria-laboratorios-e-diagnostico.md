# 15 · Mensageria: laboratórios e diagnóstico

16 cartões · primeira edição · 05/10/2026.


## SAA-15-001-C001

**Objetivo:** Mensagem processada duas vezes: analisar exclusão e idempotência

**Pergunta:** O consumidor gravou no banco e caiu antes de excluir a mensagem. Qual risco existe na reentrega?

**Resposta:** Aplicar o mesmo efeito outra vez.

**Saiba mais:** A idempotência precisa abranger o efeito de negócio, não só o recebimento.

**Fonte:** [Amazon SQS at-least-once delivery - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/standard-queues-at-least-once-delivery.html)


## SAA-15-001-C002

**Objetivo:** Mensagem processada duas vezes: analisar exclusão e idempotência

**Pergunta:** Excluir a mensagem antes de concluir o trabalho elimina duplicatas sem nenhum risco?

**Resposta:** Não. Pode perder o trabalho se houver falha depois da exclusão.

**Saiba mais:** Confirmar conclusão na ordem e com a estratégia apropriadas.

**Fonte:** [Amazon SQS at-least-once delivery - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/standard-queues-at-least-once-delivery.html)


## SAA-15-002-C001

**Objetivo:** Mensagem reaparece cedo: avaliar visibility timeout

**Pergunta:** Uma tarefa leva minutos, mas a mensagem reaparece enquanto ainda é processada. Qual configuração revisar?

**Resposta:** Visibility timeout.

**Saiba mais:** O prazo precisa considerar duração e possíveis extensões.

**Fonte:** [Amazon SQS visibility timeout - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)


## SAA-15-002-C002

**Objetivo:** Mensagem reaparece cedo: avaliar visibility timeout

**Pergunta:** Estender visibility timeout resolve uma aplicação travada para sempre?

**Resposta:** Não.

**Saiba mais:** Também é necessário limitar tentativas e tratar mensagens problemáticas.

**Fonte:** [Amazon SQS visibility timeout - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)


## SAA-15-003-C001

**Objetivo:** Fila cresce continuamente: avaliar capacidade de consumidores

**Pergunta:** O backlog cresce embora não haja erros. Qual comparação fazer?

**Resposta:** Taxa de entrada versus taxa de processamento efetiva.

**Saiba mais:** O sistema pode estar correto funcionalmente, mas subdimensionado.

**Fonte:** [Scaling policy based on Amazon SQS - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)


## SAA-15-003-C002

**Objetivo:** Fila cresce continuamente: avaliar capacidade de consumidores

**Pergunta:** CPU baixa prova que não é necessário ampliar consumidores?

**Resposta:** Não.

**Saiba mais:** O trabalho pode estar limitado por I/O, dependências ou quantidade de consumidores.

**Fonte:** [Scaling policy based on Amazon SQS - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)


## SAA-15-004-C001

**Objetivo:** Mensagem vai para DLQ: localizar falha e política de reentrega

**Pergunta:** Uma mensagem foi para DLQ. Isso prova que a fila perdeu os dados?

**Resposta:** Não.

**Saiba mais:** A política isolou uma mensagem que não foi processada dentro das condições configuradas.

**Fonte:** [Using dead-letter queues in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html)


## SAA-15-004-C002

**Objetivo:** Mensagem vai para DLQ: localizar falha e política de reentrega

**Pergunta:** Antes de redrive, quais informações analisar?

**Resposta:** Erro do consumidor, conteúdo da mensagem e política de tentativas.

**Saiba mais:** Reenviar sem diagnóstico pode repetir a falha.

**Fonte:** [Using dead-letter queues in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html)


## SAA-15-005-C001

**Objetivo:** Assinante não recebe evento: inspecionar filtro e permissões

**Pergunta:** Uma assinatura SNS recebe alguns tipos de evento e não outros. Qual configuração verificar?

**Resposta:** Filter policy e atributos ou corpo usados no filtro.

**Saiba mais:** A ausência pode ser seleção intencional, não falha de transporte.

**Fonte:** [Amazon SNS message filtering - Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/sns-message-filtering.html)


## SAA-15-005-C002

**Objetivo:** Assinante não recebe evento: inspecionar filtro e permissões

**Pergunta:** SNS não consegue enviar para uma fila SQS. Qual autorização revisar?

**Resposta:** A policy da fila permitindo envio pelo tópico apropriado.

**Saiba mais:** Assinar o tópico não dispensa os controles do destino.

**Fonte:** [Fanout Amazon SNS notifications to Amazon SQS queues for asynchronous processing - Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/sns-sqs-as-subscriber.html)


## SAA-15-006-C001

**Objetivo:** Ordem inesperada: avaliar Standard e grupos FIFO

**Pergunta:** Mensagens de grupos diferentes em FIFO avançam em paralelo. Isso viola ordenação por grupo?

**Resposta:** Não.

**Saiba mais:** A ordenação é avaliada dentro do grupo correspondente.

**Fonte:** [FIFO queue delivery logic in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues-understanding-logic.html)


## SAA-15-006-C002

**Objetivo:** Ordem inesperada: avaliar Standard e grupos FIFO

**Pergunta:** Uma única chave de grupo é adequada quando eventos independentes precisam de alto paralelismo?

**Resposta:** Pode limitar a concorrência desnecessariamente.

**Saiba mais:** Separar grupos conforme a unidade que realmente exige ordem.

**Fonte:** [FIFO queue delivery logic in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues-understanding-logic.html)


## SAA-15-007-C001

**Objetivo:** Reprocessamento: evitar repetição de efeitos colaterais

**Pergunta:** Um replay usa novo ID de transporte para o mesmo pagamento. Qual ID deve orientar deduplicação de negócio?

**Resposta:** Um identificador estável da operação de pagamento.

**Saiba mais:** IDs de entrega e IDs de negócio não são necessariamente equivalentes.

**Fonte:** [REL04-BP04 Make mutating operations idempotent - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_prevent_interaction_failure_idempotent.html)


## SAA-15-007-C002

**Objetivo:** Reprocessamento: evitar repetição de efeitos colaterais

**Pergunta:** Guardar apenas uma marca em memória local garante deduplicação após substituir o consumidor?

**Resposta:** Não.

**Saiba mais:** O registro pode desaparecer com a instância; a proteção precisa sobreviver conforme o requisito.

**Fonte:** [REL04-BP04 Make mutating operations idempotent - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_prevent_interaction_failure_idempotent.html)


## SAA-15-008-C001

**Objetivo:** Falha parcial de lote: isolar itens malsucedidos

**Pergunta:** Como reduzir reprocessamento de itens bem-sucedidos quando parte de um lote SQS-Lambda falha?

**Resposta:** Configurar e implementar partial batch responses compatíveis.

**Saiba mais:** A função precisa reportar corretamente os itens malsucedidos.

**Fonte:** [Handling errors for an SQS event source in Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/services-sqs-errorhandling.html)


## SAA-15-008-C002

**Objetivo:** Falha parcial de lote: isolar itens malsucedidos

**Pergunta:** Retornar sucesso geral quando um item não foi processado é uma forma segura de tratar falha parcial?

**Resposta:** Não.

**Saiba mais:** Pode confirmar indevidamente trabalho que deveria ser repetido.

**Fonte:** [Handling errors for an SQS event source in Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/services-sqs-errorhandling.html)

