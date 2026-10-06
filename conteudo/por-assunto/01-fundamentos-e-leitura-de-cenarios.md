# 01 · Fundamentos e leitura de cenários

36 cartões · primeira edição · 05/10/2026.


## SAA-01-001-C001

**Objetivo:** Região, zona de disponibilidade e localização de borda: escolher o nível de implantação

**Pergunta:** O que diferencia uma região AWS de uma zona de disponibilidade?

**Resposta:** Uma região contém várias zonas de disponibilidade; cada AZ reúne um ou mais datacenters isolados.

**Saiba mais:** Distribuir recursos entre AZs reduz a dependência de um único local físico.

**Fonte:** [Global infrastructure - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/global-infrastructure.html)


## SAA-01-001-C002

**Objetivo:** Região, zona de disponibilidade e localização de borda: escolher o nível de implantação

**Pergunta:** Uma aplicação deve sobreviver à falha de um datacenter. Qual distribuição considerar primeiro?

**Resposta:** Implantar componentes redundantes em múltiplas AZs.

**Saiba mais:** Criar duas instâncias na mesma AZ não garante isolamento contra uma falha zonal.

**Fonte:** [Global infrastructure - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/global-infrastructure.html)


## SAA-01-001-C003

**Objetivo:** Região, zona de disponibilidade e localização de borda: escolher o nível de implantação

**Pergunta:** Qual é a finalidade de uma localização de borda em uma CDN?

**Resposta:** Aproximar a entrega de conteúdo dos usuários.

**Saiba mais:** A borda complementa a região de origem; não substitui todos os serviços regionais.

**Fonte:** [What is Amazon CloudFront? - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)


## SAA-01-002-C001

**Objetivo:** Responsabilidade compartilhada: atribuir controles ao cliente e à AWS

**Pergunta:** Quem atualiza o sistema operacional convidado de uma instância EC2?

**Resposta:** O cliente.

**Saiba mais:** EC2 oferece infraestrutura; o cliente continua responsável pelo software instalado na instância.

**Fonte:** [Shared Responsibility Model - Amazon Web Services (AWS)](https://aws.amazon.com/compliance/shared-responsibility-model/)


## SAA-01-002-C002

**Objetivo:** Responsabilidade compartilhada: atribuir controles ao cliente e à AWS

**Pergunta:** Quem protege fisicamente os datacenters da AWS?

**Resposta:** A AWS.

**Saiba mais:** Esse controle faz parte da segurança da infraestrutura da nuvem.

**Fonte:** [Shared Responsibility Model - Amazon Web Services (AWS)](https://aws.amazon.com/compliance/shared-responsibility-model/)


## SAA-01-002-C003

**Objetivo:** Responsabilidade compartilhada: atribuir controles ao cliente e à AWS

**Pergunta:** Ao usar S3, quem define quais pessoas podem acessar os objetos?

**Resposta:** O cliente, por meio dos controles de acesso.

**Saiba mais:** Um serviço gerenciado não elimina a responsabilidade sobre permissões e dados.

**Fonte:** [Shared Responsibility Model - Amazon Web Services (AWS)](https://aws.amazon.com/compliance/shared-responsibility-model/)


## SAA-01-002-C004

**Objetivo:** Responsabilidade compartilhada: atribuir controles ao cliente e à AWS

**Pergunta:** No RDS, usar um serviço gerenciado elimina a responsabilidade por usuários do banco?

**Resposta:** Não. O cliente ainda administra acessos e configurações sob seu controle.

**Saiba mais:** A fronteira de responsabilidade depende do serviço, não apenas do nome gerenciado.

**Fonte:** [Shared Responsibility Model - Amazon Web Services (AWS)](https://aws.amazon.com/compliance/shared-responsibility-model/)


## SAA-01-003-C001

**Objetivo:** Alta disponibilidade, tolerância a falhas e durabilidade: distinguir objetivos

**Pergunta:** O que mede a disponibilidade de um sistema?

**Resposta:** A proporção de tempo em que ele consegue prestar o serviço esperado.

**Saiba mais:** Durabilidade trata da preservação dos dados, não de conseguir acessá-los agora.

**Fonte:** [Availability - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/availability.html)


## SAA-01-003-C002

**Objetivo:** Alta disponibilidade, tolerância a falhas e durabilidade: distinguir objetivos

**Pergunta:** Um objeto está preservado, mas temporariamente inacessível. Qual propriedade foi afetada diretamente?

**Resposta:** Disponibilidade.

**Saiba mais:** A indisponibilidade não implica necessariamente perda permanente do dado.

**Fonte:** [Availability - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/availability.html)


## SAA-01-003-C003

**Objetivo:** Alta disponibilidade, tolerância a falhas e durabilidade: distinguir objetivos

**Pergunta:** Qual a diferença entre recuperação de falha e tolerância a falhas?

**Resposta:** Recuperação restabelece o serviço; tolerância busca mantê-lo funcionando durante a falha.

**Saiba mais:** O requisito de interrupção aceitável orienta a arquitetura.

**Fonte:** [Availability - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/availability.html)


## SAA-01-004-C001

**Objetivo:** Escalabilidade horizontal, vertical e elasticidade: reconhecer requisitos

**Pergunta:** O que é escalar horizontalmente uma aplicação?

**Resposta:** Adicionar mais unidades de execução, como instâncias ou tarefas.

**Saiba mais:** O processamento deve conseguir distribuir trabalho entre essas unidades.

**Fonte:** [Design your workload to withstand component failures - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/design-your-workload-to-withstand-component-failures.html)


## SAA-01-004-C002

**Objetivo:** Escalabilidade horizontal, vertical e elasticidade: reconhecer requisitos

**Pergunta:** O que é escalar verticalmente um banco de dados?

**Resposta:** Aumentar os recursos da unidade existente, como CPU e memória.

**Saiba mais:** Isso não cria automaticamente redundância nem escala de escrita distribuída.

**Fonte:** [Design your workload to withstand component failures - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/design-your-workload-to-withstand-component-failures.html)


## SAA-01-004-C003

**Objetivo:** Escalabilidade horizontal, vertical e elasticidade: reconhecer requisitos

**Pergunta:** Qual característica distingue elasticidade de simplesmente possuir grande capacidade?

**Resposta:** Ajustar capacidade conforme a demanda aumenta ou diminui.

**Saiba mais:** Manter servidores grandes ociosos oferece capacidade, mas não demonstra elasticidade.

**Fonte:** [Design your workload to withstand component failures - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/design-your-workload-to-withstand-component-failures.html)


## SAA-01-005-C001

**Objetivo:** Latência, throughput e IOPS: identificar o gargalo descrito

**Pergunta:** O que significa latência em uma requisição?

**Resposta:** O tempo decorrido para obter a resposta ou concluir a operação.

**Saiba mais:** Uma média baixa pode esconder usuários com respostas muito lentas.

**Fonte:** [Monitor workload resources - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/monitor-workload-resources.html)


## SAA-01-005-C002

**Objetivo:** Latência, throughput e IOPS: identificar o gargalo descrito

**Pergunta:** O que significa throughput em um sistema?

**Resposta:** A quantidade de trabalho ou dados processados por unidade de tempo.

**Saiba mais:** Throughput alto não garante baixa latência de cada requisição.

**Fonte:** [Monitor workload resources - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/monitor-workload-resources.html)


## SAA-01-005-C003

**Objetivo:** Latência, throughput e IOPS: identificar o gargalo descrito

**Pergunta:** Qual a diferença entre IOPS e throughput de armazenamento?

**Resposta:** IOPS conta operações por segundo; throughput mede volume de dados por segundo.

**Saiba mais:** O tamanho médio de cada operação liga as duas métricas.

**Fonte:** [Monitor workload resources - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/monitor-workload-resources.html)


## SAA-01-005-C004

**Objetivo:** Latência, throughput e IOPS: identificar o gargalo descrito

**Pergunta:** Um disco atende poucas operações grandes por segundo. Qual métrica pode ser o gargalo mesmo com IOPS baixo?

**Resposta:** Throughput em bytes por segundo.

**Saiba mais:** Não escolher volume apenas pelo número de operações.

**Fonte:** [Monitor workload resources - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/monitor-workload-resources.html)


## SAA-01-006-C001

**Objetivo:** Estado de sessão e aplicações stateless: identificar dependências

**Pergunta:** Por que guardar a sessão apenas na memória de uma instância dificulta o Auto Scaling?

**Resposta:** A próxima requisição pode chegar a outra instância sem o estado da sessão.

**Saiba mais:** A perda da instância também pode perder o estado local.

**Fonte:** [Common ElastiCache Use Cases and How ElastiCache Can Help - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/elasticache-use-cases.html)


## SAA-01-006-C002

**Objetivo:** Estado de sessão e aplicações stateless: identificar dependências

**Pergunta:** Como permitir que qualquer servidor de aplicação atenda a mesma sessão?

**Resposta:** Externalizar o estado para um armazenamento compartilhado adequado.

**Saiba mais:** O armazenamento da sessão também precisa de disponibilidade e controles de acesso.

**Fonte:** [Common ElastiCache Use Cases and How ElastiCache Can Help - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/elasticache-use-cases.html)


## SAA-01-006-C003

**Objetivo:** Estado de sessão e aplicações stateless: identificar dependências

**Pergunta:** Aplicação stateless significa que o sistema não possui dados persistentes?

**Resposta:** Não. Significa que a unidade de execução não depende de estado local entre requisições.

**Saiba mais:** O estado pode existir em bancos, caches ou outros serviços externos.

**Fonte:** [Common ElastiCache Use Cases and How ElastiCache Can Help - Amazon ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/elasticache-use-cases.html)


## SAA-01-007-C001

**Objetivo:** Serviços gerenciados e autogerenciados: avaliar esforço operacional

**Pergunta:** Por que um serviço gerenciado costuma atender a um requisito de menor esforço operacional?

**Resposta:** Transfere parte da administração da infraestrutura ou plataforma ao provedor.

**Saiba mais:** Ainda é necessário configurar segurança, observabilidade e capacidade conforme o serviço.

**Fonte:** [Adopt cloud-native, managed services wherever possible and practical - AWS Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/strategy-education-hybrid-multicloud/managed-services.html)


## SAA-01-007-C002

**Objetivo:** Serviços gerenciados e autogerenciados: avaliar esforço operacional

**Pergunta:** Quando uma solução autogerenciada pode ser necessária apesar da operação adicional?

**Resposta:** Quando requisitos de controle ou compatibilidade não são atendidos pela opção gerenciada.

**Saiba mais:** Menor operação só desempata alternativas que cumprem as restrições obrigatórias.

**Fonte:** [Adopt cloud-native, managed services wherever possible and practical - AWS Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/strategy-education-hybrid-multicloud/managed-services.html)


## SAA-01-008-C001

**Objetivo:** Recursos zonais, regionais e globais: planejar limites de falha

**Pergunta:** Uma instância EC2 pode estar simultaneamente em duas AZs?

**Resposta:** Não. Cada instância é criada em uma AZ.

**Saiba mais:** Para redundância zonal, criar instâncias distintas em AZs diferentes.

**Fonte:** [Manage your Amazon EC2 resources - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/resources.html)


## SAA-01-008-C002

**Objetivo:** Recursos zonais, regionais e globais: planejar limites de falha

**Pergunta:** Um volume EBS comum pode ser anexado diretamente a uma instância de outra AZ?

**Resposta:** Não. Volume e instância devem estar na mesma AZ.

**Saiba mais:** Para mover dados, pode-se usar snapshot e criar outro volume na AZ de destino.

**Fonte:** [Manage your Amazon EC2 resources - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/resources.html)


## SAA-01-008-C003

**Objetivo:** Recursos zonais, regionais e globais: planejar limites de falha

**Pergunta:** Por que identificar se um recurso é zonal ou regional antes de desenhar alta disponibilidade?

**Resposta:** Para localizar domínios de falha e dependências compartilhadas.

**Saiba mais:** Uma aplicação em duas AZs pode continuar dependendo de um recurso zonal único.

**Fonte:** [Manage your Amazon EC2 resources - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/resources.html)


## SAA-01-009-C001

**Objetivo:** Requisitos funcionais e não funcionais: separar restrições do cenário

**Pergunta:** Em um cenário, processar pagamentos é requisito funcional ou não funcional?

**Resposta:** Funcional.

**Saiba mais:** Ele descreve uma capacidade de negócio que o sistema deve oferecer.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)


## SAA-01-009-C002

**Objetivo:** Requisitos funcionais e não funcionais: separar restrições do cenário

**Pergunta:** Em um cenário, responder em até determinado tempo é requisito funcional ou não funcional?

**Resposta:** Não funcional.

**Saiba mais:** Ele restringe a qualidade de execução, como desempenho, segurança ou disponibilidade.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)


## SAA-01-009-C003

**Objetivo:** Requisitos funcionais e não funcionais: separar restrições do cenário

**Pergunta:** Qual deve ser a primeira análise ao comparar duas arquiteturas de uma questão?

**Resposta:** Verificar quais atendem a todas as restrições obrigatórias.

**Saiba mais:** Só depois comparar custo, desempenho ou esforço operacional solicitado.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)


## SAA-01-010-C001

**Objetivo:** RTO e RPO: interpretar objetivos sem confundir tempo e perda de dados

**Pergunta:** O que representa o RTO?

**Resposta:** O tempo máximo aceitável para recuperar o serviço após uma interrupção.

**Saiba mais:** É um objetivo de recuperação, não o intervalo de backup.

**Fonte:** [What is Recovery Time Objective (RTO)? - RTO Explained - AWS](https://aws.amazon.com/what-is/recovery-time-objective/)


## SAA-01-010-C002

**Objetivo:** RTO e RPO: interpretar objetivos sem confundir tempo e perda de dados

**Pergunta:** O que representa o RPO?

**Resposta:** A perda de dados aceitável, expressa como intervalo de tempo.

**Saiba mais:** Ele orienta frequência de cópia e estratégia de replicação.

**Fonte:** [What is Recovery Time Objective (RTO)? - RTO Explained - AWS](https://aws.amazon.com/what-is/recovery-time-objective/)


## SAA-01-010-C003

**Objetivo:** RTO e RPO: interpretar objetivos sem confundir tempo e perda de dados

**Pergunta:** Backups diários garantem RPO de cinco minutos?

**Resposta:** Não, isoladamente não.

**Saiba mais:** A frequência de proteção precisa ser compatível com a perda de dados tolerada.

**Fonte:** [What is Recovery Time Objective (RTO)? - RTO Explained - AWS](https://aws.amazon.com/what-is/recovery-time-objective/)


## SAA-01-010-C004

**Objetivo:** RTO e RPO: interpretar objetivos sem confundir tempo e perda de dados

**Pergunta:** Uma restauração preserva todos os dados, mas demora horas. Qual objetivo pode ser violado?

**Resposta:** O RTO.

**Saiba mais:** Preservar dados não significa recuperar o serviço no prazo exigido.

**Fonte:** [What is Recovery Time Objective (RTO)? - RTO Explained - AWS](https://aws.amazon.com/what-is/recovery-time-objective/)


## SAA-01-011-C001

**Objetivo:** Leitura de cenários: menor custo, menor operação e maior disponibilidade

**Pergunta:** A alternativa com menor preço por hora é sempre a de menor custo total?

**Resposta:** Não. É preciso considerar uso, transferência, armazenamento e operação.

**Saiba mais:** Um componente barato pode exigir outros recursos caros para cumprir os requisitos.

**Fonte:** [Cost Optimization Pillar - AWS Well-Architected Framework - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html)


## SAA-01-011-C002

**Objetivo:** Leitura de cenários: menor custo, menor operação e maior disponibilidade

**Pergunta:** Uma arquitetura mais barata que viola o RPO é uma solução válida para o cenário?

**Resposta:** Não.

**Saiba mais:** Otimização de custo deve preservar os requisitos obrigatórios.

**Fonte:** [Cost Optimization Pillar - AWS Well-Architected Framework - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html)


## SAA-01-012-C001

**Objetivo:** Arquitetura em camadas: localizar componentes e limites de confiança

**Pergunta:** Por que separar apresentação, aplicação e banco em camadas?

**Resposta:** Para controlar comunicação e escalar componentes conforme suas funções.

**Saiba mais:** A separação lógica precisa ser acompanhada de regras de acesso adequadas.

**Fonte:** [Building a Scalable and Secure Multi-VPC AWS Network Infrastructure - Building a Scalable and Secure Multi-VPC AWS Network Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/welcome.html)


## SAA-01-012-C002

**Objetivo:** Arquitetura em camadas: localizar componentes e limites de confiança

**Pergunta:** O banco de uma aplicação web precisa ser publicamente acessível porque o site é público?

**Resposta:** Não.

**Saiba mais:** A camada de aplicação pode acessar um banco privado, enquanto só a entrada web é pública.

**Fonte:** [Building a Scalable and Secure Multi-VPC AWS Network Infrastructure - Building a Scalable and Secure Multi-VPC AWS Network Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/welcome.html)

