# 04 · Computação EC2 e modelos de compra

41 cartões · primeira edição · 05/10/2026.


## SAA-04-001-C001

**Objetivo:** Famílias de instâncias: selecionar perfil de CPU, memória e armazenamento

**Pergunta:** Uma aplicação mantém um grande conjunto de dados em memória. Qual perfil EC2 avaliar primeiro?

**Resposta:** Instâncias otimizadas para memória.

**Saiba mais:** A escolha final depende das métricas reais, não apenas do nome da aplicação.

**Fonte:** [Amazon EC2 instance types - Amazon EC2](https://docs.aws.amazon.com/ec2/latest/instancetypes/instance-types.html)


## SAA-04-001-C002

**Objetivo:** Famílias de instâncias: selecionar perfil de CPU, memória e armazenamento

**Pergunta:** Um processamento é limitado por cálculos de CPU. Qual perfil EC2 avaliar?

**Resposta:** Instâncias otimizadas para computação.

**Saiba mais:** Adicionar memória sem resolver o gargalo de CPU pode não melhorar o resultado.

**Fonte:** [Amazon EC2 instance types - Amazon EC2](https://docs.aws.amazon.com/ec2/latest/instancetypes/instance-types.html)


## SAA-04-002-C001

**Objetivo:** AMIs, user data e launch templates: distinguir funções

**Pergunta:** Qual é a função de uma AMI?

**Resposta:** Fornecer a imagem necessária para iniciar uma instância EC2.

**Saiba mais:** A imagem inclui o software base; permissões e rede ainda precisam ser configuradas.

**Fonte:** [Amazon Machine Images in Amazon EC2 - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html)


## SAA-04-002-C002

**Objetivo:** AMIs, user data e launch templates: distinguir funções

**Pergunta:** Para que serve user data em uma instância EC2?

**Resposta:** Executar configuração de inicialização conforme o sistema e o mecanismo utilizados.

**Saiba mais:** Não é um cofre de segredos e não substitui uma estratégia de configuração segura.

**Fonte:** [Run commands when you launch an EC2 instance with user data input - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html)


## SAA-04-002-C003

**Objetivo:** AMIs, user data e launch templates: distinguir funções

**Pergunta:** Por que usar um launch template em um Auto Scaling group?

**Resposta:** Para definir de forma reutilizável como novas instâncias serão lançadas.

**Saiba mais:** Inclui opções como AMI, tipo de instância e configuração de rede.

**Fonte:** [Store instance launch parameters in Amazon EC2 launch templates - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html)


## SAA-04-003-C001

**Objetivo:** Ciclo de vida EC2: stop, start, reboot, terminate e hibernate

**Pergunta:** Parar uma instância EC2 elimina todos os custos associados a ela?

**Resposta:** Não.

**Saiba mais:** Volumes EBS e outros recursos mantidos podem continuar gerando cobrança.

**Fonte:** [Amazon EC2 instance state changes - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html)


## SAA-04-003-C002

**Objetivo:** Ciclo de vida EC2: stop, start, reboot, terminate e hibernate

**Pergunta:** Reboot normalmente apaga os dados do instance store?

**Resposta:** Não.

**Saiba mais:** A perda está associada a eventos como stop, hibernate, terminate ou falha do host, não ao reboot normal.

**Fonte:** [Amazon EC2 instance state changes - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html)


## SAA-04-003-C003

**Objetivo:** Ciclo de vida EC2: stop, start, reboot, terminate e hibernate

**Pergunta:** Qual é a finalidade de hibernar uma instância compatível?

**Resposta:** Preservar o estado da memória para retomar a execução.

**Saiba mais:** É necessário atender aos requisitos de suporte e armazenamento.

**Fonte:** [Amazon EC2 instance state changes - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html)


## SAA-04-004-C001

**Objetivo:** EC2 instance store: decidir sobre persistência e dados reconstruíveis

**Pergunta:** Que tipo de dado combina com instance store?

**Resposta:** Dados temporários ou reconstruíveis.

**Saiba mais:** Não depender dele como única cópia de informação durável.

**Fonte:** [Instance store temporary block storage for EC2 instances - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)


## SAA-04-004-C002

**Objetivo:** EC2 instance store: decidir sobre persistência e dados reconstruíveis

**Pergunta:** Por que um banco com dados únicos não deve depender exclusivamente de instance store?

**Resposta:** A perda da instância ou do armazenamento subjacente pode perder os dados.

**Saiba mais:** É necessário projetar replicação e recuperação conforme a aplicação.

**Fonte:** [Instance store temporary block storage for EC2 instances - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)


## SAA-04-005-C001

**Objetivo:** EBS como disco de instância: distinguir ciclo de vida e capacidade

**Pergunta:** Qual é o modelo de armazenamento fornecido por EBS?

**Resposta:** Bloco.

**Saiba mais:** Ele se comporta como volume para sistemas operacionais e aplicações compatíveis.

**Fonte:** [What is Amazon Elastic Block Store? - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/what-is-ebs.html)


## SAA-04-005-C002

**Objetivo:** EBS como disco de instância: distinguir ciclo de vida e capacidade

**Pergunta:** Terminar uma instância necessariamente exclui todos os seus volumes EBS?

**Resposta:** Não. Depende da configuração DeleteOnTermination.

**Saiba mais:** Verificar o atributo dos volumes evita tanto perda inesperada quanto custos de volumes órfãos.

**Fonte:** [What is Amazon Elastic Block Store? - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/what-is-ebs.html)


## SAA-04-006-C001

**Objetivo:** ENI, endereços privados, públicos e Elastic IP: interpretar conectividade

**Pergunta:** O que representa uma ENI?

**Resposta:** Uma interface de rede virtual na VPC.

**Saiba mais:** Pode conter endereços e associações de segurança conforme seu uso.

**Fonte:** [Elastic network interfaces - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)


## SAA-04-006-C002

**Objetivo:** ENI, endereços privados, públicos e Elastic IP: interpretar conectividade

**Pergunta:** Qual recurso oferece um endereço IPv4 público estático alocável à conta?

**Resposta:** Elastic IP.

**Saiba mais:** É diferente de presumir permanência do IPv4 público atribuído automaticamente.

**Fonte:** [Elastic IP addresses - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html)


## SAA-04-007-C001

**Objetivo:** Placement groups cluster, spread e partition: selecionar distribuição

**Pergunta:** Qual placement group favorece proximidade de rede entre instâncias para baixa latência?

**Resposta:** Cluster.

**Saiba mais:** Concentração de recursos exige considerar o domínio de falha.

**Fonte:** [Placement groups for your Amazon EC2 instances - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html)


## SAA-04-007-C002

**Objetivo:** Placement groups cluster, spread e partition: selecionar distribuição

**Pergunta:** Qual placement group separa instâncias em hardware distinto para reduzir falhas correlacionadas?

**Resposta:** Spread.

**Saiba mais:** É voltado a um conjunto de instâncias críticas, sujeito aos limites aplicáveis.

**Fonte:** [Placement groups for your Amazon EC2 instances - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html)


## SAA-04-007-C003

**Objetivo:** Placement groups cluster, spread e partition: selecionar distribuição

**Pergunta:** Qual placement group divide instâncias em conjuntos com infraestrutura separada para aplicações distribuídas?

**Resposta:** Partition.

**Saiba mais:** A aplicação pode usar a separação para posicionar réplicas de forma consciente.

**Fonte:** [Placement groups for your Amazon EC2 instances - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html)


## SAA-04-008-C001

**Objetivo:** Rede aprimorada e requisitos HPC: identificar opções de desempenho

**Pergunta:** Qual recurso EC2 é relevante para comunicação de alto desempenho em workloads HPC compatíveis?

**Resposta:** Elastic Fabric Adapter.

**Saiba mais:** Verificar suporte da instância e da aplicação antes de escolher.

**Fonte:** [Elastic Fabric Adapter for AI/ML and HPC workloads on Amazon EC2 - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/efa.html)


## SAA-04-008-C002

**Objetivo:** Rede aprimorada e requisitos HPC: identificar opções de desempenho

**Pergunta:** Por que aumentar CPU pode não resolver um job HPC limitado pela troca de mensagens?

**Resposta:** O gargalo pode estar na comunicação entre nós.

**Saiba mais:** Analisar rede, latência e posicionamento em conjunto.

**Fonte:** [Elastic Fabric Adapter for AI/ML and HPC workloads on Amazon EC2 - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/efa.html)


## SAA-04-009-C001

**Objetivo:** On-Demand e Spot: selecionar conforme interrupção tolerada

**Pergunta:** Quando On-Demand é adequado em comparação a compromissos de longo prazo?

**Resposta:** Quando se deseja capacidade sem compromisso de uso de longo prazo.

**Saiba mais:** Flexibilidade pode ser mais importante quando a demanda ainda é incerta.

**Fonte:** [Amazon EC2 billing and purchasing options - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html)


## SAA-04-009-C002

**Objetivo:** On-Demand e Spot: selecionar conforme interrupção tolerada

**Pergunta:** Que característica de um workload favorece Spot?

**Resposta:** Tolerar interrupções e reiniciar ou redistribuir trabalho.

**Saiba mais:** O desconto não compensa perder trabalho que não pode ser recuperado.

**Fonte:** [Amazon EC2 billing and purchasing options - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html)


## SAA-04-010-C001

**Objetivo:** Reserved Instances e Savings Plans: diferenciar compromisso e flexibilidade

**Pergunta:** Qual é a base de compromisso de um Savings Plan?

**Resposta:** Um valor de uso por hora durante o prazo contratado.

**Saiba mais:** Não é simplesmente uma reserva de uma quantidade fixa de servidores.

**Fonte:** [What are Savings Plans? - Savings Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html)


## SAA-04-010-C002

**Objetivo:** Reserved Instances e Savings Plans: diferenciar compromisso e flexibilidade

**Pergunta:** Qual opção costuma oferecer maior flexibilidade entre EC2, Fargate e Lambda: Compute Savings Plans ou uma RI EC2 específica?

**Resposta:** Compute Savings Plans.

**Saiba mais:** O benefício depende da modalidade e do uso elegível.

**Fonte:** [What are Savings Plans? - Savings Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html)


## SAA-04-011-C001

**Objetivo:** Reserva de capacidade e desconto: separar disponibilidade de benefício financeiro

**Pergunta:** Reservar capacidade e obter desconto são o mesmo objetivo?

**Resposta:** Não.

**Saiba mais:** Capacity Reservations tratam de disponibilidade de capacidade; descontos dependem do modelo de compra aplicável.

**Fonte:** [Reserve compute capacity with EC2 On-Demand Capacity Reservations - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-capacity-reservations.html)


## SAA-04-011-C002

**Objetivo:** Reserva de capacidade e desconto: separar disponibilidade de benefício financeiro

**Pergunta:** Qual necessidade uma reserva de capacidade atende em um cenário crítico?

**Resposta:** Ter capacidade reservada compatível na localização e configuração definidas.

**Saiba mais:** Não confundir capacidade disponível com alta disponibilidade da aplicação.

**Fonte:** [Reserve compute capacity with EC2 On-Demand Capacity Reservations - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-capacity-reservations.html)


## SAA-04-012-C001

**Objetivo:** Dedicated Hosts e Dedicated Instances: avaliar isolamento e licenciamento

**Pergunta:** Qual opção oferece visibilidade e controle de um servidor físico para determinados requisitos de licenciamento?

**Resposta:** Dedicated Host.

**Saiba mais:** Pode ser relevante para licenças vinculadas a sockets ou núcleos físicos.

**Fonte:** [Amazon EC2 Dedicated Hosts - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-hosts-overview.html)


## SAA-04-012-C002

**Objetivo:** Dedicated Hosts e Dedicated Instances: avaliar isolamento e licenciamento

**Pergunta:** Dedicated Instances oferecem exatamente o mesmo controle de posicionamento e licenciamento de Dedicated Hosts?

**Resposta:** Não.

**Saiba mais:** Ambas tratam de dedicação de hardware, mas seus controles e modelos diferem.

**Fonte:** [Amazon EC2 Dedicated Hosts - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-hosts-overview.html)


## SAA-04-013-C001

**Objetivo:** Spot interruption e checkpoints: projetar retomada de processamento

**Pergunta:** Como checkpoints ajudam um job executado em Spot?

**Resposta:** Permitem retomar de um estado salvo após interrupção.

**Saiba mais:** O checkpoint deve estar em armazenamento que sobreviva à perda da instância.

**Fonte:** [Spot Instance interruptions - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-interruptions.html)


## SAA-04-013-C002

**Objetivo:** Spot interruption e checkpoints: projetar retomada de processamento

**Pergunta:** Por que diversificar tipos de instância e AZs pode ajudar uma frota Spot?

**Resposta:** Reduz dependência de um único pool de capacidade.

**Saiba mais:** Ainda é necessário tratar interrupções na aplicação.

**Fonte:** [Spot Instance interruptions - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-interruptions.html)


## SAA-04-014-C001

**Objetivo:** Rightsizing e Compute Optimizer: analisar dimensionamento

**Pergunta:** Qual serviço produz recomendações de dimensionamento para recursos suportados com base em utilização?

**Resposta:** AWS Compute Optimizer.

**Saiba mais:** A recomendação deve ser confrontada com picos, sazonalidade e requisitos.

**Fonte:** [What is AWS Compute Optimizer? - AWS Compute Optimizer](https://docs.aws.amazon.com/compute-optimizer/latest/ug/what-is-compute-optimizer.html)


## SAA-04-014-C002

**Objetivo:** Rightsizing e Compute Optimizer: analisar dimensionamento

**Pergunta:** É suficiente reduzir uma instância porque sua CPU média está baixa?

**Resposta:** Não.

**Saiba mais:** Memória, rede, armazenamento e picos podem ser os limites reais.

**Fonte:** [What is AWS Compute Optimizer? - AWS Compute Optimizer](https://docs.aws.amazon.com/compute-optimizer/latest/ug/what-is-compute-optimizer.html)


## SAA-04-015-C001

**Objetivo:** Graviton e arquitetura de processador: verificar compatibilidade

**Pergunta:** Qual compatibilidade deve ser verificada antes de migrar uma aplicação para Graviton?

**Resposta:** Compatibilidade com arquitetura Arm, incluindo binários e dependências.

**Saiba mais:** Código e bibliotecas compilados apenas para x86 podem exigir mudanças.

**Fonte:** [ARM Processor - Performance Processor - AWS EC2 Graviton - AWS](https://aws.amazon.com/ec2/graviton/)


## SAA-04-015-C002

**Objetivo:** Graviton e arquitetura de processador: verificar compatibilidade

**Pergunta:** Migrar para uma família de processador diferente garante automaticamente melhoria para toda aplicação?

**Resposta:** Não.

**Saiba mais:** É necessário medir desempenho, compatibilidade e custo do workload.

**Fonte:** [ARM Processor - Performance Processor - AWS EC2 Graviton - AWS](https://aws.amazon.com/ec2/graviton/)


## SAA-04-016-C001

**Objetivo:** Elastic Beanstalk e EC2: comparar operação de aplicações

**Pergunta:** Qual serviço gerencia implantação e ambiente de aplicações enquanto utiliza recursos como EC2?

**Resposta:** AWS Elastic Beanstalk.

**Saiba mais:** Ele reduz tarefas de provisionamento e gerenciamento do ambiente.

**Fonte:** [What is AWS Elastic Beanstalk? - AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)


## SAA-04-016-C002

**Objetivo:** Elastic Beanstalk e EC2: comparar operação de aplicações

**Pergunta:** Usar Elastic Beanstalk significa não ter responsabilidade pelo código da aplicação?

**Resposta:** Não.

**Saiba mais:** A aplicação, seus dados e configurações continuam exigindo gestão.

**Fonte:** [What is AWS Elastic Beanstalk? - AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)


## SAA-04-017-C001

**Objetivo:** AWS Batch: selecionar execução de trabalhos em lote

**Pergunta:** Qual serviço organiza execução de jobs em lote com filas e ambientes de computação?

**Resposta:** AWS Batch.

**Saiba mais:** É adequado quando o trabalho pode ser descrito como jobs com requisitos de recursos.

**Fonte:** [What is AWS Batch? - AWS Batch](https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html)


## SAA-04-017-C002

**Objetivo:** AWS Batch: selecionar execução de trabalhos em lote

**Pergunta:** Por que um job longo e pesado pode combinar mais com Batch que com uma função de curta duração?

**Resposta:** Porque requer um modelo de execução e capacidade compatível com trabalho em lote.

**Saiba mais:** Comparar duração, dependências e limites antes de decidir.

**Fonte:** [What is AWS Batch? - AWS Batch](https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html)


## SAA-04-018-C001

**Objetivo:** Outposts e computação híbrida: reconhecer necessidade de execução local

**Pergunta:** Qual serviço leva infraestrutura e serviços AWS suportados ao ambiente local do cliente?

**Resposta:** AWS Outposts.

**Saiba mais:** Pode atender requisitos de baixa latência local ou residência de processamento.

**Fonte:** [What is AWS Outposts? - AWS Outposts](https://docs.aws.amazon.com/outposts/latest/userguide/what-is-outposts.html)


## SAA-04-018-C002

**Objetivo:** Outposts e computação híbrida: reconhecer necessidade de execução local

**Pergunta:** Outposts elimina a necessidade de avaliar conectividade com a região AWS?

**Resposta:** Não.

**Saiba mais:** As dependências de conectividade e de operação precisam ser consideradas.

**Fonte:** [What is AWS Outposts? - AWS Outposts](https://docs.aws.amazon.com/outposts/latest/userguide/what-is-outposts.html)


## SAA-04-019-C001

**Objetivo:** Systems Manager Session Manager: planejar administração de instâncias

**Pergunta:** Como administrar uma instância sem expor diretamente uma porta SSH à internet?

**Resposta:** Usar Systems Manager Session Manager em uma configuração compatível.

**Saiba mais:** A instância precisa de agente, permissões e conectividade com os serviços necessários.

**Fonte:** [AWS Systems Manager Session Manager - AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)


## SAA-04-019-C002

**Objetivo:** Systems Manager Session Manager: planejar administração de instâncias

**Pergunta:** Session Manager funciona apenas por associar uma role à instância?

**Resposta:** Não.

**Saiba mais:** Também é preciso atender aos requisitos de agente, rede e configuração.

**Fonte:** [AWS Systems Manager Session Manager - AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)

