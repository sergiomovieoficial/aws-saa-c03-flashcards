# 16 · Containers e execução gerenciada

30 cartões · primeira edição · 05/10/2026.


## SAA-16-001-C001

**Objetivo:** ECS e EKS: escolher plataforma de orquestração

**Pergunta:** Qual diferença central de escolha existe entre ECS e EKS?

**Resposta:** ECS é a orquestração própria da AWS; EKS oferece Kubernetes gerenciado.

**Saiba mais:** Compatibilidade com Kubernetes pode ser um requisito decisivo.

**Fonte:** [AWS Containers category iconContainers - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/containers.html)


## SAA-16-001-C002

**Objetivo:** ECS e EKS: escolher plataforma de orquestração

**Pergunta:** Usar EKS significa que toda operação da aplicação e dos nós desaparece?

**Resposta:** Não.

**Saiba mais:** As responsabilidades variam conforme a modalidade de execução e a configuração.

**Fonte:** [AWS Containers category iconContainers - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/containers.html)


## SAA-16-002-C001

**Objetivo:** Fargate e instâncias EC2: comparar execução de containers

**Pergunta:** Qual opção executa tarefas ECS sem administrar diretamente uma frota EC2?

**Resposta:** AWS Fargate.

**Saiba mais:** A equipe continua definindo recursos, imagens, rede e permissões da tarefa.

**Fonte:** [Architect for AWS Fargate for Amazon ECS - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html)


## SAA-16-002-C002

**Objetivo:** Fargate e instâncias EC2: comparar execução de containers

**Pergunta:** Quando EC2 para containers pode ser preferível a Fargate?

**Resposta:** Quando controle do host, compatibilidade ou economia de utilização justificam a operação.

**Saiba mais:** A decisão precisa considerar requisitos suportados e custo total.

**Fonte:** [Architect for AWS Fargate for Amazon ECS - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html)


## SAA-16-003-C001

**Objetivo:** ECS tasks, services e clusters: distinguir unidades

**Pergunta:** Qual diferença entre task definition e task no ECS?

**Resposta:** A definição descreve a execução; a task é uma instância dessa definição em execução.

**Saiba mais:** Uma service administra a manutenção de tarefas conforme a configuração.

**Fonte:** [What is Amazon Elastic Container Service? - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)


## SAA-16-003-C002

**Objetivo:** ECS tasks, services e clusters: distinguir unidades

**Pergunta:** Qual componente ECS mantém o número desejado de tarefas de uma aplicação contínua?

**Resposta:** ECS service.

**Saiba mais:** Uma tarefa avulsa não tem necessariamente o mesmo gerenciamento de ciclo de vida.

**Fonte:** [What is Amazon Elastic Container Service? - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)


## SAA-16-004-C001

**Objetivo:** Task role e execution role: separar permissões

**Pergunta:** Qual role ECS é usada pelo agente para atividades como obter imagens e enviar logs, conforme o ambiente?

**Resposta:** Task execution role.

**Saiba mais:** Não é a role que deve conceder indiscriminadamente acesso de negócio ao código.

**Fonte:** [Amazon ECS task execution IAM role - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_execution_IAM_role.html)


## SAA-16-004-C002

**Objetivo:** Task role e execution role: separar permissões

**Pergunta:** Qual role deve autorizar o código do container a ler uma tabela DynamoDB?

**Resposta:** Task role.

**Saiba mais:** Separar permissões de execução da plataforma das permissões da aplicação.

**Fonte:** [Amazon ECS task IAM role - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-iam-roles.html)


## SAA-16-005-C001

**Objetivo:** ECS networking: avaliar isolamento e conectividade

**Pergunta:** Qual característica do modo awsvpc permite controle de rede no nível da tarefa?

**Resposta:** A tarefa utiliza uma interface de rede com configuração própria apropriada.

**Saiba mais:** Planejar endereços de subnet e security groups.

**Fonte:** [Allocate a network interface for an Amazon ECS task - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-networking-awsvpc.html)


## SAA-16-005-C002

**Objetivo:** ECS networking: avaliar isolamento e conectividade

**Pergunta:** Uma tarefa em subnet privada consegue buscar imagem sem qualquer caminho para ECR ou internet?

**Resposta:** Não.

**Saiba mais:** Ela precisa alcançar as dependências necessárias por endpoints ou saída adequada.

**Fonte:** [Allocate a network interface for an Amazon ECS task - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-networking-awsvpc.html)


## SAA-16-006-C001

**Objetivo:** ECS service auto scaling: dimensionar tarefas

**Pergunta:** O que ECS Service Auto Scaling ajusta?

**Resposta:** A quantidade desejada de tarefas de uma service.

**Saiba mais:** Capacidade para executar essas tarefas também precisa estar disponível.

**Fonte:** [Automatically scale your Amazon ECS service - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html)


## SAA-16-006-C002

**Objetivo:** ECS service auto scaling: dimensionar tarefas

**Pergunta:** Escalar a quantidade de tarefas corrige automaticamente um banco que já atingiu seu limite?

**Resposta:** Não.

**Saiba mais:** Pode aumentar ainda mais a pressão sobre a dependência.

**Fonte:** [Automatically scale your Amazon ECS service - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html)


## SAA-16-007-C001

**Objetivo:** Capacity providers: relacionar tarefas à capacidade

**Pergunta:** Qual função dos capacity providers no ECS?

**Resposta:** Relacionar execução das tarefas à capacidade disponível e às estratégias de alocação.

**Saiba mais:** Eles ajudam a administrar modalidades como EC2 e Fargate conforme suporte.

**Fonte:** [Amazon ECS cluster capacity - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/capacity-cluster-best-practice.html)


## SAA-16-007-C002

**Objetivo:** Capacity providers: relacionar tarefas à capacidade

**Pergunta:** Uma tarefa pendente pode resultar de falta de capacidade mesmo com service configurada corretamente?

**Resposta:** Sim.

**Saiba mais:** Verificar recursos, restrições de posicionamento e capacidade compatível.

**Fonte:** [Amazon ECS cluster capacity - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/capacity-cluster-best-practice.html)


## SAA-16-008-C001

**Objetivo:** ECR: armazenamento de imagens e acesso

**Pergunta:** Qual serviço armazena e distribui imagens de container na AWS?

**Resposta:** Amazon ECR.

**Saiba mais:** É um registro de imagens, não o orquestrador que as executa.

**Fonte:** [What is Amazon Elastic Container Registry? - Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html)


## SAA-16-008-C002

**Objetivo:** ECR: armazenamento de imagens e acesso

**Pergunta:** Ter a URI de uma imagem ECR privada garante permissão para baixá-la?

**Resposta:** Não.

**Saiba mais:** O principal e a rede precisam permitir acesso ao registro e suas dependências.

**Fonte:** [What is Amazon Elastic Container Registry? - Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html)


## SAA-16-009-C001

**Objetivo:** Containers com persistência: selecionar EFS e outras opções suportadas

**Pergunta:** Como fornecer filesystem compartilhado persistente a tarefas ECS compatíveis?

**Resposta:** Usar integração com Amazon EFS.

**Saiba mais:** Verificar modo de execução, rede e autorização de montagem.

**Fonte:** [Use Amazon EFS volumes with Amazon ECS - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/efs-volumes.html)


## SAA-16-009-C002

**Objetivo:** Containers com persistência: selecionar EFS e outras opções suportadas

**Pergunta:** Guardar arquivos únicos apenas no filesystem efêmero do container é suficiente para persistência após substituição?

**Resposta:** Não.

**Saiba mais:** Persistência precisa ser externa ou usar um volume apropriado ao ciclo de vida.

**Fonte:** [Use Amazon EFS volumes with Amazon ECS - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/efs-volumes.html)


## SAA-16-010-C001

**Objetivo:** EKS nodes, pods e serviços: reconhecer componentes arquiteturais

**Pergunta:** Qual unidade Kubernetes reúne um ou mais containers com contexto compartilhado de execução?

**Resposta:** Pod.

**Saiba mais:** EKS gerencia a plataforma Kubernetes, enquanto workloads usam suas abstrações.

**Fonte:** [What is Amazon EKS? - Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)


## SAA-16-010-C002

**Objetivo:** EKS nodes, pods e serviços: reconhecer componentes arquiteturais

**Pergunta:** Control plane gerenciado elimina a necessidade de planejar disponibilidade dos workloads?

**Resposta:** Não.

**Saiba mais:** Réplicas, distribuição e dependências continuam sendo decisões arquiteturais.

**Fonte:** [What is Amazon EKS? - Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)


## SAA-16-011-C001

**Objetivo:** Workload identity no EKS: escolher acesso a serviços AWS

**Pergunta:** Como conceder acesso AWS específico a workloads EKS sem depender de uma role ampla do nó?

**Resposta:** Usar identidade de workload apropriada, como EKS Pod Identity em ambientes suportados.

**Saiba mais:** Aplicar menor privilégio por aplicação.

**Fonte:** [Learn how EKS Pod Identity grants pods access to AWS services - Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html)


## SAA-16-011-C002

**Objetivo:** Workload identity no EKS: escolher acesso a serviços AWS

**Pergunta:** Por que compartilhar uma role ampla do nó entre aplicações distintas pode ser inadequado?

**Resposta:** Amplia o conjunto de permissões potencialmente disponível aos workloads.

**Saiba mais:** Separação de identidade reduz alcance de acesso.

**Fonte:** [Learn how EKS Pod Identity grants pods access to AWS services - Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html)


## SAA-16-012-C001

**Objetivo:** Containers entre AZs: evitar concentração de falha

**Pergunta:** Por que distribuir réplicas de containers entre AZs?

**Resposta:** Para reduzir impacto de falha zonal.

**Saiba mais:** Também verificar armazenamento e dependências externas.

**Fonte:** [Balancing an Amazon ECS service across Availability Zones - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-rebalancing.html)


## SAA-16-012-C002

**Objetivo:** Containers entre AZs: evitar concentração de falha

**Pergunta:** Três tarefas na mesma AZ equivalem a três tarefas distribuídas para tolerância à falha de AZ?

**Resposta:** Não.

**Saiba mais:** A quantidade de réplicas não substitui separação física.

**Fonte:** [Balancing an Amazon ECS service across Availability Zones - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-rebalancing.html)


## SAA-16-013-C001

**Objetivo:** Deployment e health checks: avaliar continuidade

**Pergunta:** Qual objetivo dos limites de tarefas saudáveis durante um deployment ECS?

**Resposta:** Controlar disponibilidade e capacidade enquanto versões são substituídas.

**Saiba mais:** A configuração precisa ser compatível com recursos e health checks.

**Fonte:** [Deploy Amazon ECS services by replacing tasks - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/deployment-type-ecs.html)


## SAA-16-013-C002

**Objetivo:** Deployment e health checks: avaliar continuidade

**Pergunta:** Por que um deployment que inicia container sem verificar prontidão pode falhar?

**Resposta:** O tráfego pode chegar antes de a aplicação estar apta a responder.

**Saiba mais:** Processo iniciado e serviço pronto não são a mesma condição.

**Fonte:** [Deploy Amazon ECS services by replacing tasks - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/deployment-type-ecs.html)


## SAA-16-014-C001

**Objetivo:** ECS/EKS Anywhere: reconhecer necessidade híbrida

**Pergunta:** Qual recurso estende gerenciamento ECS a capacidade externa compatível?

**Resposta:** ECS Anywhere.

**Saiba mais:** O hardware externo continua tendo responsabilidades de operação próprias.

**Fonte:** [Amazon ECS clusters for external instances - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-anywhere.html)


## SAA-16-014-C002

**Objetivo:** ECS/EKS Anywhere: reconhecer necessidade híbrida

**Pergunta:** ECS Anywhere significa mover automaticamente toda computação local para a região AWS?

**Resposta:** Não.

**Saiba mais:** O propósito é gerenciar execução externa integrada ao ECS.

**Fonte:** [Amazon ECS clusters for external instances - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-anywhere.html)


## SAA-16-015-C001

**Objetivo:** Custos EC2 versus Fargate: comparar utilização e operação

**Pergunta:** Quais dimensões de recursos influenciam diretamente custo de tarefas Fargate?

**Resposta:** Recursos alocados e duração, conforme a modalidade e a tabela de preços.

**Saiba mais:** Não comparar só quantidade de containers.

**Fonte:** [AWS Fargate Pricing](https://aws.amazon.com/fargate/pricing/)


## SAA-16-015-C002

**Objetivo:** Custos EC2 versus Fargate: comparar utilização e operação

**Pergunta:** Por que uma frota EC2 bem utilizada pode ter comparação de custo diferente de tarefas esporádicas Fargate?

**Resposta:** Taxa de utilização e operação mudam o custo total.

**Saiba mais:** O mesmo serviço não é universalmente o mais barato.

**Fonte:** [AWS Fargate Pricing](https://aws.amazon.com/fargate/pricing/)

