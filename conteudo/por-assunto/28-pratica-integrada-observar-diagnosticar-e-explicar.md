# 28 · Prática integrada: observar, diagnosticar e explicar

13 cartões · primeira edição · 05/10/2026.


## SAA-28-001-C001

**Objetivo:** Interpretar diagrama de aplicação em três camadas

**Pergunta:** Num diagrama web, o banco aceita tráfego da internet inteira. Que melhoria de segurança priorizar?

**Resposta:** Restringir acesso ao caminho e aos clientes necessários, normalmente pela camada de aplicação.

**Saiba mais:** O protocolo de banco não precisa ser público só porque a aplicação web é pública.

**Fonte:** [Example: VPC with servers in private subnets and NAT - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-example-private-subnets-nat.html)


## SAA-28-002-C001

**Objetivo:** Seguir a requisição do DNS até o banco

**Pergunta:** Uma requisição falha antes de abrir conexão HTTP porque o nome não resolve. Qual etapa do caminho investigar?

**Resposta:** Resolução DNS.

**Saiba mais:** Balanceador e banco não corrigem um nome que não é resolvido pelo cliente.

**Fonte:** [What is Amazon Route 53? - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html)


## SAA-28-002-C002

**Objetivo:** Seguir a requisição do DNS até o banco

**Pergunta:** DNS resolve e TLS termina no ALB, mas o backend retorna erro. Qual evidência ajuda a separar rede e aplicação?

**Resposta:** Logs, health checks e resposta do target.

**Saiba mais:** Seguir o caminho por etapas evita mudar controles sem diagnóstico.

**Fonte:** [Troubleshoot your Application Load Balancers - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-troubleshooting.html)


## SAA-28-003-C001

**Objetivo:** Simular conceitualmente a perda de uma AZ

**Pergunta:** Ao simular a perda de uma AZ, quais componentes além das instâncias devem entrar na análise?

**Resposta:** Dados, saída de rede, balanceamento e dependências compartilhadas.

**Saiba mais:** A réplica da camada web não prova resiliência do restante.

**Fonte:** [Auto Scaling benefits for application architecture - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-benefits.html)


## SAA-28-004-C001

**Objetivo:** Interpretar alarmes após aumento abrupto de carga

**Pergunta:** Após um pico, CPU está normal, mas latência de banco e conexões aumentaram. Onde concentrar investigação?

**Resposta:** No banco e na forma de acesso a ele.

**Saiba mais:** A métrica da camada web não representa todo o sistema.

**Fonte:** [Metrics concepts - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html)


## SAA-28-004-C002

**Objetivo:** Interpretar alarmes após aumento abrupto de carga

**Pergunta:** O backlog sobe e a idade das mensagens cresce. Qual requisito de negócio pode estar sendo violado?

**Resposta:** O prazo aceitável para concluir o processamento.

**Saiba mais:** Fila evita perda imediata, mas não garante conclusão dentro do prazo.

**Fonte:** [Scaling policy based on Amazon SQS - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)


## SAA-28-005-C001

**Objetivo:** Identificar exposição pública em arquitetura de dados

**Pergunta:** Qual evidência de revisão ajuda a localizar dados expostos por uma política de recurso?

**Resposta:** Achados de acesso externo e inspeção das concessões efetivas.

**Saiba mais:** Validar a intenção do compartilhamento antes de classificar o risco.

**Fonte:** [Using AWS Identity and Access Management Access Analyzer - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)


## SAA-28-006-C001

**Objetivo:** Planejar evidências de restauração de backup

**Pergunta:** Qual resultado de laboratório demonstra melhor recuperação do que apenas backup verde?

**Resposta:** Restaurar, verificar dados e executar uma transação funcional.

**Saiba mais:** Medir os tempos relaciona o teste ao RTO.

**Fonte:** [Restore testing - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/restore-testing.html)


## SAA-28-006-C002

**Objetivo:** Planejar evidências de restauração de backup

**Pergunta:** O teste restaurou dados de ontem, mas o negócio aceita perder apenas minutos. Qual objetivo não foi comprovado?

**Resposta:** O RPO.

**Saiba mais:** Uma restauração tecnicamente bem-sucedida pode não atender ao negócio.

**Fonte:** [Restoring a DB instance to a specified time for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIT.html)


## SAA-28-007-C001

**Objetivo:** Investigar entrega duplicada em fluxo orientado a eventos

**Pergunta:** Um lote com um item inválido repete itens já processados. Qual comportamento de integração avaliar?

**Resposta:** Resposta parcial de lote e idempotência dos itens.

**Saiba mais:** A solução deve evitar tanto duplicação de efeitos quanto perda de trabalho.

**Fonte:** [Handling errors for an SQS event source in Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/services-sqs-errorhandling.html)


## SAA-28-007-C002

**Objetivo:** Investigar entrega duplicada em fluxo orientado a eventos

**Pergunta:** Qual evidência registrar ao mover uma mensagem problemática para DLQ?

**Resposta:** Identificador, erro e contexto suficiente para investigar e recuperar.

**Saiba mais:** Não expor segredos desnecessariamente nos logs.

**Fonte:** [Using dead-letter queues in Amazon SQS - Amazon Simple Queue Service](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html)


## SAA-28-008-C001

**Objetivo:** Comparar estimativa de custo antes e depois da arquitetura

**Pergunta:** Após adicionar mais NATs, quais dimensões comparar além da nova cobrança por recurso?

**Resposta:** Processamento, tráfego entre AZs e requisito de disponibilidade.

**Saiba mais:** Uma mudança pode aumentar uma parcela e reduzir outra.

**Fonte:** [Analyzing your costs and usage with AWS Cost Explorer - AWS Cost Management](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)


## SAA-28-008-C002

**Objetivo:** Comparar estimativa de custo antes e depois da arquitetura

**Pergunta:** Uma alteração reduz custo por pedido, mas a fatura total cresce porque o volume dobrou. Ela necessariamente piorou eficiência?

**Resposta:** Não.

**Saiba mais:** Comparar custo unitário e atendimento dos requisitos.

**Fonte:** [Cost Optimization Pillar - AWS Well-Architected Framework - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html)

