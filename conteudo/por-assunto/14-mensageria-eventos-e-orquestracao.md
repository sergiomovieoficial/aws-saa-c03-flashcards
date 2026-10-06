# 14 · Mensageria, eventos e orquestração

36 cartões · primeira edição · 05/10/2026.


## SAA-14-001-C001

**Objetivo:** SQS, SNS e EventBridge: escolher fila, distribuição ou barramento

**Pergunta:** Qual serviço usar para manter trabalho pendente até consumidores processarem?

**Resposta:** Amazon SQS.

**Saiba mais:** A fila desacopla a produção do ritmo de processamento.

**Fonte:** [Amazon SQS, Amazon SNS, or Amazon EventBridge? - AWS Decision Guides](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/sns-or-sqs-or-eventbridge.html)


## SAA-14-001-C002

**Objetivo:** SQS, SNS e EventBridge: escolher fila, distribuição ou barramento

**Pergunta:** Qual serviço atende distribuição pub/sub para múltiplos assinantes?

**Resposta:** Amazon SNS.

**Saiba mais:** Pode enviar para filas independentes quando cada consumidor precisa de durabilidade própria.

**Fonte:** [Amazon SQS, Amazon SNS, or Amazon EventBridge? - AWS Decision Guides](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/sns-or-sqs-or-eventbridge.html)


## SAA-14-001-C003

**Objetivo:** SQS, SNS e EventBridge: escolher fila, distribuição ou barramento

**Pergunta:** Qual serviço roteia eventos por regras e padrões em um barramento?

**Resposta:** Amazon EventBridge.

**Saiba mais:** Eventos expressam acontecimentos; regras selecionam destinos.

**Fonte:** [Amazon SQS, Amazon SNS, or Amazon EventBridge? - AWS Decision Guides](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/sns-or-sqs-or-eventbridge.html)


## SAA-14-002-C001

**Objetivo:** SQS Standard e FIFO: comparar ordem e duplicação

**Pergunta:** Qual semântica de entrega deve ser considerada em SQS Standard?

**Resposta:** Pelo menos uma vez, com possibilidade de duplicação e ordem não estrita.

**Saiba mais:** O consumidor deve tolerar reentregas.

**Fonte:** [Amazon SQS standard queues - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/standard-queues.html)


## SAA-14-002-C002

**Objetivo:** SQS Standard e FIFO: comparar ordem e duplicação

**Pergunta:** Em SQS FIFO, a ordenação relevante é global entre todos os grupos de mensagem?

**Resposta:** Não. A ordem é mantida dentro de cada message group.

**Saiba mais:** Grupos distintos permitem concorrência conforme o recurso.

**Fonte:** [FIFO queue delivery logic in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues-understanding-logic.html)


## SAA-14-002-C003

**Objetivo:** SQS Standard e FIFO: comparar ordem e duplicação

**Pergunta:** FIFO dispensa idempotência de efeitos de negócio em qualquer falha do consumidor?

**Resposta:** Não.

**Saiba mais:** Falhar depois do efeito e antes da confirmação ainda precisa ser tratado.

**Fonte:** [FIFO queue delivery logic in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues-understanding-logic.html)


## SAA-14-003-C001

**Objetivo:** Visibility timeout: interpretar reentrega e duração de processamento

**Pergunta:** O que o visibility timeout faz após uma mensagem ser recebida?

**Resposta:** Oculta temporariamente a mensagem de outros recebimentos.

**Saiba mais:** Não equivale a excluí-la da fila.

**Fonte:** [Amazon SQS visibility timeout - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)


## SAA-14-003-C002

**Objetivo:** Visibility timeout: interpretar reentrega e duração de processamento

**Pergunta:** O que pode ocorrer se o processamento demora mais que o visibility timeout?

**Resposta:** A mensagem pode ficar visível e ser recebida novamente.

**Saiba mais:** Ajustar ou estender o timeout conforme o processamento.

**Fonte:** [Amazon SQS visibility timeout - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)


## SAA-14-004-C001

**Objetivo:** Long polling e short polling: reduzir consultas vazias

**Pergunta:** Como long polling ajuda consumidores SQS?

**Resposta:** Reduz respostas vazias esperando mensagens por um período configurado.

**Saiba mais:** Pode diminuir requisições desnecessárias e melhorar eficiência.

**Fonte:** [Amazon SQS short and long polling - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html)


## SAA-14-004-C002

**Objetivo:** Long polling e short polling: reduzir consultas vazias

**Pergunta:** Long polling faz uma mensagem permanecer invisível por mais tempo após recebimento?

**Resposta:** Não.

**Saiba mais:** Essa função é do visibility timeout.

**Fonte:** [Amazon SQS short and long polling - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html)


## SAA-14-005-C001

**Objetivo:** DLQ e redrive: tratar falhas persistentes

**Pergunta:** Qual é a finalidade de uma dead-letter queue?

**Resposta:** Separar mensagens que falham repetidamente conforme a política.

**Saiba mais:** Isso permite investigar sem impedir continuamente o fluxo normal.

**Fonte:** [Using dead-letter queues in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html)


## SAA-14-005-C002

**Objetivo:** DLQ e redrive: tratar falhas persistentes

**Pergunta:** Enviar mensagens da DLQ novamente à origem corrige automaticamente o defeito que causou a falha?

**Resposta:** Não.

**Saiba mais:** A causa deve ser tratada para evitar repetir o ciclo.

**Fonte:** [Using dead-letter queues in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html)


## SAA-14-006-C001

**Objetivo:** Retenção, atraso e mensagens em trânsito: distinguir controles

**Pergunta:** Qual a diferença entre delay e visibility timeout no SQS?

**Resposta:** Delay posterga disponibilidade inicial; visibility timeout oculta após recebimento.

**Saiba mais:** São controles de etapas diferentes do ciclo da mensagem.

**Fonte:** [Amazon SQS delay queues - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-delay-queues.html)


## SAA-14-006-C002

**Objetivo:** Retenção, atraso e mensagens em trânsito: distinguir controles

**Pergunta:** O que encerra normalmente o ciclo de uma mensagem processada com sucesso?

**Resposta:** Sua exclusão pelo consumidor ou integração responsável.

**Saiba mais:** Recebê-la não comprova conclusão do trabalho.

**Fonte:** [Amazon SQS visibility timeout - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)


## SAA-14-007-C001

**Objetivo:** Idempotência do consumidor: lidar com entrega repetida

**Pergunta:** O que significa um consumidor idempotente?

**Resposta:** Repetir a mesma solicitação não produz efeitos adicionais indesejados.

**Saiba mais:** É especialmente importante em processamento com retries e reentregas.

**Fonte:** [REL04-BP04 Make mutating operations idempotent - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_prevent_interaction_failure_idempotent.html)


## SAA-14-007-C002

**Objetivo:** Idempotência do consumidor: lidar com entrega repetida

**Pergunta:** Como uma chave de idempotência pode proteger uma cobrança?

**Resposta:** Identificando uma operação de negócio já aplicada.

**Saiba mais:** A verificação e o registro do efeito precisam resistir a concorrência.

**Fonte:** [REL04-BP04 Make mutating operations idempotent - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_prevent_interaction_failure_idempotent.html)


## SAA-14-008-C001

**Objetivo:** FIFO message groups e deduplication IDs: organizar processamento

**Pergunta:** Para que serve MessageGroupId em uma fila FIFO?

**Resposta:** Agrupar mensagens que precisam preservar ordem de processamento.

**Saiba mais:** Escolher apenas um grupo pode limitar paralelismo.

**Fonte:** [Amazon SQS FIFO queue key terms - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-key-terms.html)


## SAA-14-008-C002

**Objetivo:** FIFO message groups e deduplication IDs: organizar processamento

**Pergunta:** Para que serve MessageDeduplicationId?

**Resposta:** Identificar duplicatas no mecanismo de deduplicação FIFO dentro de suas condições.

**Saiba mais:** Não é uma substituição universal para deduplicação de negócio.

**Fonte:** [Amazon SQS FIFO queue key terms - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-key-terms.html)


## SAA-14-009-C001

**Objetivo:** SNS fan-out para SQS: desacoplar consumidores

**Pergunta:** Como entregar cada evento a dois consumidores que processam em velocidades diferentes?

**Resposta:** SNS publicando em uma fila SQS independente para cada consumidor.

**Saiba mais:** Cada fila preserva o backlog de sua aplicação.

**Fonte:** [Fanout Amazon SNS notifications to Amazon SQS queues for asynchronous processing - Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/sns-sqs-as-subscriber.html)


## SAA-14-009-C002

**Objetivo:** SNS fan-out para SQS: desacoplar consumidores

**Pergunta:** Dois consumidores da mesma fila SQS recebem obrigatoriamente uma cópia de cada mensagem cada um?

**Resposta:** Não.

**Saiba mais:** Eles normalmente competem pelo trabalho; fan-out exige desenho diferente.

**Fonte:** [Fanout Amazon SNS notifications to Amazon SQS queues for asynchronous processing - Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/sns-sqs-as-subscriber.html)


## SAA-14-010-C001

**Objetivo:** SNS filter policies: filtrar assinaturas

**Pergunta:** Qual recurso SNS permite entregar apenas eventos que atendem critérios de uma assinatura?

**Resposta:** Subscription filter policy.

**Saiba mais:** O filtro evita que todos os consumidores recebam todo o conteúdo indiscriminadamente.

**Fonte:** [Amazon SNS message filtering - Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/sns-message-filtering.html)


## SAA-14-010-C002

**Objetivo:** SNS filter policies: filtrar assinaturas

**Pergunta:** Filtrar mensagens depois que chegam à aplicação tem o mesmo efeito operacional de filtrar na assinatura?

**Resposta:** Não.

**Saiba mais:** A filtragem na origem da entrega pode reduzir tráfego e processamento desnecessários.

**Fonte:** [Amazon SNS message filtering - Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/sns-message-filtering.html)


## SAA-14-011-C001

**Objetivo:** EventBridge rules e event patterns: rotear eventos

**Pergunta:** Como uma regra EventBridge seleciona eventos relevantes?

**Resposta:** Por event pattern com campos e condições suportadas.

**Saiba mais:** O formato do evento precisa corresponder ao padrão.

**Fonte:** [Amazon EventBridge event patterns - Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-event-patterns.html)


## SAA-14-011-C002

**Objetivo:** EventBridge rules e event patterns: rotear eventos

**Pergunta:** Um evento roteado pelo barramento executa necessariamente a lógica do consumidor com sucesso?

**Resposta:** Não.

**Saiba mais:** Entrega, processamento e tratamento de falha são etapas diferentes.

**Fonte:** [Amazon EventBridge event patterns - Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-event-patterns.html)


## SAA-14-012-C001

**Objetivo:** EventBridge archive e replay: avaliar reprocessamento

**Pergunta:** Para que serve archive e replay no EventBridge?

**Resposta:** Armazenar eventos selecionados e reenviá-los conforme o recurso.

**Saiba mais:** Consumidores devem considerar os efeitos de reprocessar eventos.

**Fonte:** [Archiving and replaying events in Amazon EventBridge - Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-archive.html)


## SAA-14-012-C002

**Objetivo:** EventBridge archive e replay: avaliar reprocessamento

**Pergunta:** Replay é apropriado sem analisar idempotência de consumidores que cobram clientes?

**Resposta:** Não.

**Saiba mais:** Repetir o evento pode repetir efeitos de negócio se não houver proteção.

**Fonte:** [Archiving and replaying events in Amazon EventBridge - Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-archive.html)


## SAA-14-013-C001

**Objetivo:** Step Functions Standard e Express: escolher workflow

**Pergunta:** Quais duas modalidades principais de workflow o Step Functions oferece?

**Resposta:** Standard e Express.

**Saiba mais:** Escolher conforme duração, volume, semântica e recursos necessários.

**Fonte:** [Choosing workflow type in Step Functions - AWS Step Functions](https://docs.aws.amazon.com/step-functions/latest/dg/choosing-workflow-type.html)


## SAA-14-013-C002

**Objetivo:** Step Functions Standard e Express: escolher workflow

**Pergunta:** Por que um fluxo de longa duração com auditoria detalhada pode favorecer Standard?

**Resposta:** Seu modelo é voltado a workflows duráveis com características próprias de execução.

**Saiba mais:** Verificar limites e integrações antes de escolher.

**Fonte:** [Choosing workflow type in Step Functions - AWS Step Functions](https://docs.aws.amazon.com/step-functions/latest/dg/choosing-workflow-type.html)


## SAA-14-014-C001

**Objetivo:** Retries, backoff e tratamento de erros: projetar recuperação

**Pergunta:** Qual é a utilidade de retry com backoff?

**Resposta:** Espaçar novas tentativas para reduzir pressão sobre uma dependência em falha.

**Saiba mais:** Repetir imediatamente em massa pode agravar a indisponibilidade.

**Fonte:** [Handling errors in Step Functions workflows - AWS Step Functions](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-error-handling.html)


## SAA-14-014-C002

**Objetivo:** Retries, backoff e tratamento de erros: projetar recuperação

**Pergunta:** Quando um Catch de workflow é útil?

**Resposta:** Quando uma falha precisa seguir um caminho alternativo de tratamento.

**Saiba mais:** Nem todo erro deve produzir repetição infinita.

**Fonte:** [Handling errors in Step Functions workflows - AWS Step Functions](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-error-handling.html)


## SAA-14-015-C001

**Objetivo:** Amazon MQ: avaliar migração com protocolo existente

**Pergunta:** Qual serviço considerar para migrar aplicação dependente de protocolos de brokers tradicionais com menos alterações?

**Resposta:** Amazon MQ.

**Saiba mais:** A compatibilidade do broker pode ser decisiva para uma aplicação legada.

**Fonte:** [What is Amazon MQ? - Amazon MQ](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/welcome.html)


## SAA-14-015-C002

**Objetivo:** Amazon MQ: avaliar migração com protocolo existente

**Pergunta:** Por que SQS não é sempre uma substituição sem alterações de um broker existente?

**Resposta:** APIs, protocolos e recursos podem diferir.

**Saiba mais:** A seleção precisa considerar a integração atual.

**Fonte:** [What is Amazon MQ? - Amazon MQ](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/welcome.html)


## SAA-14-016-C001

**Objetivo:** AppFlow: reconhecer integração com aplicações SaaS

**Pergunta:** Qual serviço realiza transferência gerenciada de dados entre aplicações SaaS e serviços AWS suportados?

**Resposta:** Amazon AppFlow.

**Saiba mais:** Verificar conectores, direção e frequência disponíveis.

**Fonte:** [What is Amazon AppFlow? - Amazon AppFlow](https://docs.aws.amazon.com/appflow/latest/userguide/what-is-appflow.html)


## SAA-14-016-C002

**Objetivo:** AppFlow: reconhecer integração com aplicações SaaS

**Pergunta:** AppFlow é o mesmo que um barramento genérico para qualquer evento da aplicação?

**Resposta:** Não.

**Saiba mais:** Sua finalidade central é integração e transferência por conectores suportados.

**Fonte:** [What is Amazon AppFlow? - Amazon AppFlow](https://docs.aws.amazon.com/appflow/latest/userguide/what-is-appflow.html)


## SAA-14-017-C001

**Objetivo:** Filas e backpressure: absorver picos sem perder trabalho

**Pergunta:** Como uma fila protege um processamento contra picos temporários de entrada?

**Resposta:** Armazena o backlog enquanto consumidores trabalham em seu ritmo.

**Saiba mais:** A capacidade e retenção devem atender ao volume acumulado.

**Fonte:** [Scaling policy based on Amazon SQS - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)


## SAA-14-017-C002

**Objetivo:** Filas e backpressure: absorver picos sem perder trabalho

**Pergunta:** Uma fila elimina a necessidade de escalar consumidores quando a entrada supera o processamento continuamente?

**Resposta:** Não.

**Saiba mais:** O backlog cresce até limites ou perda de prazo; é preciso capacidade sustentável.

**Fonte:** [Scaling policy based on Amazon SQS - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)

