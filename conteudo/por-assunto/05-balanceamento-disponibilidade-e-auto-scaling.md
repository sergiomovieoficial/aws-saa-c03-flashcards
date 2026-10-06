# 05 · Balanceamento, disponibilidade e Auto Scaling

33 cartões · primeira edição · 05/10/2026.


## SAA-05-001-C001

**Objetivo:** ALB, NLB e GWLB: escolher pelo protocolo e finalidade

**Pergunta:** Qual balanceador escolher para roteamento HTTP por host e caminho?

**Resposta:** Application Load Balancer.

**Saiba mais:** Ele opera com informações da camada de aplicação.

**Fonte:** [What is Elastic Load Balancing? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html)


## SAA-05-001-C002

**Objetivo:** ALB, NLB e GWLB: escolher pelo protocolo e finalidade

**Pergunta:** Qual balanceador considerar para tráfego TCP ou UDP com alto desempenho?

**Resposta:** Network Load Balancer.

**Saiba mais:** A seleção depende dos protocolos e recursos exigidos.

**Fonte:** [What is Elastic Load Balancing? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html)


## SAA-05-001-C003

**Objetivo:** ALB, NLB e GWLB: escolher pelo protocolo e finalidade

**Pergunta:** Qual balanceador integra appliances virtuais de rede ao fluxo de tráfego?

**Resposta:** Gateway Load Balancer.

**Saiba mais:** É usado em arquiteturas de inspeção, não como substituto genérico de roteamento HTTP.

**Fonte:** [What is Elastic Load Balancing? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html)


## SAA-05-002-C001

**Objetivo:** ALB: roteamento por host e path

**Pergunta:** Um domínio atende /imagens e /pedidos em serviços diferentes. Que recurso do ALB ajuda?

**Resposta:** Regras de listener baseadas em path com target groups diferentes.

**Saiba mais:** O roteamento pode direcionar cada rota ao backend correspondente.

**Fonte:** [Listeners for your Application Load Balancers - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html)


## SAA-05-002-C002

**Objetivo:** ALB: roteamento por host e path

**Pergunta:** Vários domínios usam um ALB e cada um precisa de backend próprio. Qual condição usar?

**Resposta:** Roteamento baseado em host.

**Saiba mais:** A regra considera o nome apresentado na requisição.

**Fonte:** [Listeners for your Application Load Balancers - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html)


## SAA-05-003-C001

**Objetivo:** NLB: requisitos de transporte e endereço IP

**Pergunta:** Por que um requisito de endereços IP estáticos pode favorecer NLB?

**Resposta:** O NLB oferece endereços estáticos por AZ habilitada, com opções de Elastic IP compatíveis.

**Saiba mais:** Não usar o endereço resolvido momentaneamente de um ALB como IP fixo.

**Fonte:** [What is a Network Load Balancer? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)


## SAA-05-003-C002

**Objetivo:** NLB: requisitos de transporte e endereço IP

**Pergunta:** Um NLB escolhe backend por caminho de URL como um ALB?

**Resposta:** Não.

**Saiba mais:** Para decisões baseadas em conteúdo HTTP, avaliar ALB.

**Fonte:** [What is a Network Load Balancer? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)


## SAA-05-004-C001

**Objetivo:** Target groups e health checks: interpretar saúde de aplicação

**Pergunta:** O que um health check de aplicação deve representar?

**Resposta:** A capacidade do target de atender ao tráfego esperado.

**Saiba mais:** Uma porta aberta pode existir mesmo quando a aplicação está inutilizável.

**Fonte:** [Health checks for Application Load Balancer target groups - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html)


## SAA-05-004-C002

**Objetivo:** Target groups e health checks: interpretar saúde de aplicação

**Pergunta:** Por que um endpoint de health check excessivamente dependente de serviços externos pode causar problemas?

**Resposta:** Pode retirar muitos targets simultaneamente por uma dependência compartilhada.

**Saiba mais:** Definir saúde exige equilibrar utilidade do teste e comportamento durante falhas.

**Fonte:** [Health checks for Application Load Balancer target groups - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html)


## SAA-05-005-C001

**Objetivo:** Health check EC2 e ELB: distinguir detecção e reposição

**Pergunta:** Um EC2 status check saudável garante que o endpoint HTTP está funcionando?

**Resposta:** Não.

**Saiba mais:** Falhas da aplicação podem exigir health checks do balanceador.

**Fonte:** [Health checks for instances in an Auto Scaling group - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/healthcheck.html)


## SAA-05-005-C002

**Objetivo:** Health check EC2 e ELB: distinguir detecção e reposição

**Pergunta:** Como o Auto Scaling pode substituir instâncias consideradas não saudáveis pelo ELB?

**Resposta:** Habilitando o uso dos health checks do ELB no grupo conforme a configuração.

**Saiba mais:** Não presumir que qualquer falha HTTP provoca substituição sem essa integração.

**Fonte:** [Health checks for instances in an Auto Scaling group - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/healthcheck.html)


## SAA-05-006-C001

**Objetivo:** Auto Scaling: capacidade mínima, desejada e máxima

**Pergunta:** Qual parâmetro indica quantas instâncias o Auto Scaling group busca manter?

**Resposta:** Desired capacity.

**Saiba mais:** Min e max estabelecem os limites configurados.

**Fonte:** [Set scaling limits for your Auto Scaling group - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-capacity-limits.html)


## SAA-05-006-C002

**Objetivo:** Auto Scaling: capacidade mínima, desejada e máxima

**Pergunta:** O que acontece se a aplicação precisa de mais capacidade, mas o grupo já atingiu o máximo configurado?

**Resposta:** A configuração máxima impede a expansão normal além desse limite.

**Saiba mais:** Quotas e disponibilidade de capacidade também precisam ser avaliadas.

**Fonte:** [Set scaling limits for your Auto Scaling group - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-capacity-limits.html)


## SAA-05-007-C001

**Objetivo:** Target tracking e step scaling: selecionar política reativa

**Pergunta:** Qual política busca manter uma métrica próxima de um valor desejado?

**Resposta:** Target tracking.

**Saiba mais:** É útil para métricas que variam de forma adequada com a capacidade.

**Fonte:** [Target tracking scaling policies for Amazon EC2 Auto Scaling - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html)


## SAA-05-007-C002

**Objetivo:** Target tracking e step scaling: selecionar política reativa

**Pergunta:** Qual política permite ajustes diferentes conforme o tamanho do desvio de uma métrica?

**Resposta:** Step scaling.

**Saiba mais:** Os intervalos do alarme determinam o ajuste aplicável.

**Fonte:** [Step and simple scaling policies for Amazon EC2 Auto Scaling - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html)


## SAA-05-008-C001

**Objetivo:** Scheduled e predictive scaling: selecionar antecipação de demanda

**Pergunta:** Uma carga aumenta todo dia em horário conhecido. Qual mecanismo permite ampliar antes do evento?

**Resposta:** Scheduled scaling.

**Saiba mais:** Quando o horário é previsível, não é necessário esperar o alarme do pico.

**Fonte:** [Scheduled scaling for Amazon EC2 Auto Scaling - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-scheduled-scaling.html)


## SAA-05-008-C002

**Objetivo:** Scheduled e predictive scaling: selecionar antecipação de demanda

**Pergunta:** Qual mecanismo usa histórico de carga para antecipar necessidades recorrentes?

**Resposta:** Predictive scaling.

**Saiba mais:** Previsão deve ser avaliada junto a estratégias reativas e ao padrão real de demanda.

**Fonte:** [Predictive scaling for Amazon EC2 Auto Scaling - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-predictive-scaling.html)


## SAA-05-009-C001

**Objetivo:** Cooldown e instance warmup: interpretar estabilização

**Pergunta:** Para que serve instance warmup no Auto Scaling?

**Resposta:** Representar o tempo necessário para novas instâncias atingirem funcionamento normal.

**Saiba mais:** Evita tratar imediatamente toda capacidade recém-iniciada como estabilizada.

**Fonte:** [Set the default instance warmup for an Auto Scaling group - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-default-instance-warmup.html)


## SAA-05-009-C002

**Objetivo:** Cooldown e instance warmup: interpretar estabilização

**Pergunta:** Por que tempo de boot não deve ser ignorado ao dimensionar uma aplicação elástica?

**Resposta:** A capacidade recém-lançada pode demorar a atender requisições.

**Saiba mais:** Picos mais rápidos que o provisionamento exigem planejamento adicional.

**Fonte:** [Set the default instance warmup for an Auto Scaling group - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-default-instance-warmup.html)


## SAA-05-010-C001

**Objetivo:** Lifecycle hooks e connection draining: desligar instância com segurança

**Pergunta:** Qual recurso permite executar tarefas antes de concluir lançamento ou término de uma instância do grupo?

**Resposta:** Lifecycle hooks.

**Saiba mais:** A automação precisa concluir ou administrar o timeout da ação.

**Fonte:** [Amazon EC2 Auto Scaling lifecycle hooks - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/lifecycle-hooks.html)


## SAA-05-010-C002

**Objetivo:** Lifecycle hooks e connection draining: desligar instância com segurança

**Pergunta:** Por que usar deregistration delay ao retirar um target?

**Resposta:** Para dar oportunidade de concluir requisições em andamento.

**Saiba mais:** Isso não preserva trabalho indefinidamente nem substitui tratamento de falhas.

**Fonte:** [Edit target group attributes for your Application Load Balancer - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/edit-target-group-attributes.html)


## SAA-05-011-C001

**Objetivo:** Auto Scaling entre AZs: reduzir dependência de uma zona

**Pergunta:** Por que distribuir um Auto Scaling group entre AZs?

**Resposta:** Para reduzir impacto de falhas localizadas e distribuir capacidade.

**Saiba mais:** As demais dependências da aplicação também precisam de redundância.

**Fonte:** [Auto Scaling benefits for application architecture - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-benefits.html)


## SAA-05-011-C002

**Objetivo:** Auto Scaling entre AZs: reduzir dependência de uma zona

**Pergunta:** Ter instâncias em duas AZs basta se todas dependem de um banco sem proteção contra falha zonal?

**Resposta:** Não.

**Saiba mais:** A disponibilidade da arquitetura é limitada pelas dependências críticas.

**Fonte:** [Auto Scaling benefits for application architecture - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-benefits.html)


## SAA-05-012-C001

**Objetivo:** Sessões: comparar sticky sessions e armazenamento externo

**Pergunta:** Qual é o objetivo de sticky sessions?

**Resposta:** Encaminhar requisições de uma sessão ao mesmo target durante a afinidade aplicável.

**Saiba mais:** Isso pode ajudar aplicações com estado, mas não torna o estado local durável.

**Fonte:** [Edit target group attributes for your Application Load Balancer - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/edit-target-group-attributes.html#sticky-sessions)


## SAA-05-012-C002

**Objetivo:** Sessões: comparar sticky sessions e armazenamento externo

**Pergunta:** Por que externalizar sessões costuma facilitar substituição de instâncias?

**Resposta:** A sessão deixa de depender da memória de um target específico.

**Saiba mais:** O armazenamento externo precisa atender latência e disponibilidade exigidas.

**Fonte:** [Edit target group attributes for your Application Load Balancer - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/edit-target-group-attributes.html#sticky-sessions)


## SAA-05-013-C001

**Objetivo:** Cross-zone load balancing: avaliar distribuição e custo

**Pergunta:** O que cross-zone load balancing altera?

**Resposta:** A distribuição de tráfego entre targets de AZs habilitadas.

**Saiba mais:** O comportamento e a cobrança dependem do tipo de balanceador e da configuração.

**Fonte:** [How Elastic Load Balancing works - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/how-elastic-load-balancing-works.html)


## SAA-05-013-C002

**Objetivo:** Cross-zone load balancing: avaliar distribuição e custo

**Pergunta:** É correto aplicar as mesmas regras de custo cross-zone a ALB, NLB e GWLB sem conferir?

**Resposta:** Não.

**Saiba mais:** Os produtos e caminhos de transferência possuem condições próprias.

**Fonte:** [How Elastic Load Balancing works - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/how-elastic-load-balancing-works.html)


## SAA-05-014-C001

**Objetivo:** TLS no balanceador: selecionar terminação ou passagem de tráfego

**Pergunta:** Qual listener do NLB termina TLS no balanceador?

**Resposta:** Um listener TLS.

**Saiba mais:** Usar TCP para passagem de tráfego criptografado é uma decisão diferente.

**Fonte:** [Create a listener for your Network Load Balancer - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/create-listener.html)


## SAA-05-014-C002

**Objetivo:** TLS no balanceador: selecionar terminação ou passagem de tráfego

**Pergunta:** Terminar TLS no balanceador elimina a necessidade de certificado?

**Resposta:** Não.

**Saiba mais:** O ponto que termina TLS precisa do certificado e da configuração correspondente.

**Fonte:** [Create a listener for your Network Load Balancer - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/create-listener.html)


## SAA-05-015-C001

**Objetivo:** Scaling por backlog de fila: conectar capacidade ao trabalho pendente

**Pergunta:** Qual métrica pode ser mais útil que CPU para escalar consumidores de uma fila?

**Resposta:** Backlog por instância ou por consumidor.

**Saiba mais:** Relaciona trabalho pendente à capacidade efetiva de processamento.

**Fonte:** [Scaling policy based on Amazon SQS - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)


## SAA-05-015-C002

**Objetivo:** Scaling por backlog de fila: conectar capacidade ao trabalho pendente

**Pergunta:** Por que o total de mensagens sozinho pode ser um sinal incompleto para scaling?

**Resposta:** Ele não considera quantidade e velocidade dos consumidores.

**Saiba mais:** O tempo aceitável na fila também importa.

**Fonte:** [Scaling policy based on Amazon SQS - Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)


## SAA-05-016-C001

**Objetivo:** Aplicação com estado: remover barreiras à expansão horizontal

**Pergunta:** Uma aplicação grava uploads no disco local de cada servidor. Qual barreira isso cria para scaling?

**Resposta:** Outros servidores podem não acessar os mesmos arquivos.

**Saiba mais:** Usar armazenamento apropriado compartilhado ou de objetos conforme o padrão de acesso.

**Fonte:** [Design your workload service architecture - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/design-your-workload-service-architecture.html)


## SAA-05-016-C002

**Objetivo:** Aplicação com estado: remover barreiras à expansão horizontal

**Pergunta:** Por que duplicar servidores sem revisar estado não garante escalabilidade correta?

**Resposta:** Requisições podem depender de dados que existem apenas em um servidor.

**Saiba mais:** Escala exige desenho de comunicação, estado e concorrência.

**Fonte:** [Design your workload service architecture - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/design-your-workload-service-architecture.html)

