# 23 · Organizations, governança e custos

34 cartões · primeira edição · 05/10/2026.


## SAA-23-001-C001

**Objetivo:** Organizations, contas e OUs: projetar separação administrativa

**Pergunta:** Qual benefício de separar ambientes em contas AWS distintas?

**Resposta:** Criar fronteiras administrativas, de acesso e de cobrança.

**Saiba mais:** Contas ajudam isolamento, mas ainda precisam de governança.

**Fonte:** [What is AWS Organizations? - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html)


## SAA-23-001-C002

**Objetivo:** Organizations, contas e OUs: projetar separação administrativa

**Pergunta:** Qual função de uma OU em AWS Organizations?

**Resposta:** Agrupar contas para organização e aplicação de políticas.

**Saiba mais:** A estrutura deve refletir requisitos de controle, não apenas um organograma.

**Fonte:** [What is AWS Organizations? - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html)


## SAA-23-002-C001

**Objetivo:** SCPs: interpretar guardrails sem tratá-los como concessão de acesso

**Pergunta:** Uma SCP aplicada à organização restringe usuários e roles da management account?

**Resposta:** Não.

**Saiba mais:** Seu efeito sobre membros não deve ser generalizado à conta de gerenciamento.

**Fonte:** [Service control policies (SCPs) - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)


## SAA-23-002-C002

**Objetivo:** SCPs: interpretar guardrails sem tratá-los como concessão de acesso

**Pergunta:** O root de uma conta membro é sempre imune a SCPs?

**Resposta:** Não.

**Saiba mais:** SCPs podem restringir identidades da conta membro, respeitadas as exceções documentadas.

**Fonte:** [Service control policies (SCPs) - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)


## SAA-23-003-C001

**Objetivo:** Control Tower: reconhecer landing zone e controles

**Pergunta:** Qual serviço auxilia a configurar e governar uma landing zone de múltiplas contas?

**Resposta:** AWS Control Tower.

**Saiba mais:** Utiliza capacidades de outros serviços para estabelecer a estrutura e controles.

**Fonte:** [What Is AWS Control Tower? - AWS Control Tower](https://docs.aws.amazon.com/controltower/latest/userguide/what-is-control-tower.html)


## SAA-23-003-C002

**Objetivo:** Control Tower: reconhecer landing zone e controles

**Pergunta:** Control Tower elimina a necessidade de definir organização e responsabilidades das contas?

**Resposta:** Não.

**Saiba mais:** A ferramenta implementa governança, mas a estratégia continua sendo uma decisão da organização.

**Fonte:** [What Is AWS Control Tower? - AWS Control Tower](https://docs.aws.amazon.com/controltower/latest/userguide/what-is-control-tower.html)


## SAA-23-004-C001

**Objetivo:** RAM: avaliar compartilhamento de recursos

**Pergunta:** Qual serviço compartilha recursos AWS suportados entre contas?

**Resposta:** AWS Resource Access Manager.

**Saiba mais:** A possibilidade e os limites variam por tipo de recurso.

**Fonte:** [What is AWS Resource Access Manager? - AWS Resource Access Manager](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html)


## SAA-23-004-C002

**Objetivo:** RAM: avaliar compartilhamento de recursos

**Pergunta:** Compartilhar um recurso por RAM significa transferir automaticamente sua propriedade?

**Resposta:** Não.

**Saiba mais:** Compartilhamento e propriedade são conceitos diferentes.

**Fonte:** [What is AWS Resource Access Manager? - AWS Resource Access Manager](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html)


## SAA-23-005-C001

**Objetivo:** Service Catalog: selecionar catálogo governado

**Pergunta:** Qual serviço permite oferecer um catálogo governado de produtos de infraestrutura aprovados?

**Resposta:** AWS Service Catalog.

**Saiba mais:** Ajuda a padronizar o provisionamento permitido aos usuários.

**Fonte:** [What Is Service Catalog? - AWS Service Catalog](https://docs.aws.amazon.com/servicecatalog/latest/adminguide/introduction.html)


## SAA-23-005-C002

**Objetivo:** Service Catalog: selecionar catálogo governado

**Pergunta:** Um catálogo aprovado substitui a necessidade de controlar permissões de lançamento?

**Resposta:** Não.

**Saiba mais:** O acesso aos produtos e sua execução precisam de autorização adequada.

**Fonte:** [What Is Service Catalog? - AWS Service Catalog](https://docs.aws.amazon.com/servicecatalog/latest/adminguide/introduction.html)


## SAA-23-006-C001

**Objetivo:** Cobrança consolidada e tags: organizar alocação de custos

**Pergunta:** Qual benefício da cobrança consolidada no Organizations?

**Resposta:** Reunir cobrança de contas e permitir benefícios agregados conforme as regras.

**Saiba mais:** A consolidação não elimina a separação administrativa entre contas.

**Fonte:** [Consolidating billing for AWS Organizations - AWS Billing](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html)


## SAA-23-006-C002

**Objetivo:** Cobrança consolidada e tags: organizar alocação de custos

**Pergunta:** Para que servem cost allocation tags?

**Resposta:** Classificar custos por dimensões como projeto ou centro de custo.

**Saiba mais:** As tags relevantes precisam ser ativadas e usadas consistentemente.

**Fonte:** [Organizing and tracking costs using AWS cost allocation tags - AWS Billing](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html)


## SAA-23-007-C001

**Objetivo:** Budgets e Cost Explorer: distinguir acompanhamento e análise

**Pergunta:** Qual serviço permite acompanhar orçamento e emitir alertas de custo ou uso?

**Resposta:** AWS Budgets.

**Saiba mais:** Um alerta não deve ser confundido com desligamento automático de todos os recursos.

**Fonte:** [Managing your costs with AWS Budgets - AWS Cost Management](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)


## SAA-23-007-C002

**Objetivo:** Budgets e Cost Explorer: distinguir acompanhamento e análise

**Pergunta:** Qual ferramenta permite explorar custos históricos e tendências de uso?

**Resposta:** AWS Cost Explorer.

**Saiba mais:** Ela ajuda a investigar e comparar dimensões do gasto.

**Fonte:** [Analyzing your costs and usage with AWS Cost Explorer - AWS Cost Management](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)


## SAA-23-008-C001

**Objetivo:** Cost and Usage Report: selecionar granularidade de informação

**Pergunta:** Qual recurso disponibiliza dados detalhados de custo e uso para análise própria?

**Resposta:** AWS Cost and Usage Report, conforme a modalidade de exportação utilizada.

**Saiba mais:** A granularidade facilita análises além de um painel resumido.

**Fonte:** [What are AWS Cost and Usage Reports? - AWS Data Exports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)


## SAA-23-008-C002

**Objetivo:** Cost and Usage Report: selecionar granularidade de informação

**Pergunta:** Um relatório detalhado reduz custos automaticamente ao ser criado?

**Resposta:** Não.

**Saiba mais:** Ele fornece evidência para decisões e ações de otimização.

**Fonte:** [What are AWS Cost and Usage Reports? - AWS Data Exports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)


## SAA-23-009-C001

**Objetivo:** Savings Plans e reservas: revisar compromisso a partir do uso

**Pergunta:** Qual risco de contratar compromisso muito acima do uso estável?

**Resposta:** Pagar compromisso sem aproveitá-lo completamente.

**Saiba mais:** Dimensionar com base em utilização e previsões confiáveis.

**Fonte:** [What are Savings Plans? - Savings Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html)


## SAA-23-009-C002

**Objetivo:** Savings Plans e reservas: revisar compromisso a partir do uso

**Pergunta:** Por que corrigir desperdício antes de assumir compromissos de longo prazo?

**Resposta:** Para não comprometer gasto em capacidade desnecessária.

**Saiba mais:** Rightsizing e eliminação de ociosidade ajudam a definir a base útil.

**Fonte:** [What are Savings Plans? - Savings Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html)


## SAA-23-010-C001

**Objetivo:** Compute Optimizer e Trusted Advisor: avaliar recomendações

**Pergunta:** Qual serviço oferece recomendações de boas práticas em categorias de infraestrutura, incluindo custos?

**Resposta:** AWS Trusted Advisor.

**Saiba mais:** O acesso às verificações depende das condições e recursos disponíveis.

**Fonte:** [AWS Trusted Advisor - AWS Support](https://docs.aws.amazon.com/awssupport/latest/user/trusted-advisor.html)


## SAA-23-010-C002

**Objetivo:** Compute Optimizer e Trusted Advisor: avaliar recomendações

**Pergunta:** Uma recomendação automática deve ser aplicada sem avaliar o workload?

**Resposta:** Não.

**Saiba mais:** Requisitos de negócio e contexto podem justificar a configuração existente.

**Fonte:** [AWS Trusted Advisor - AWS Support](https://docs.aws.amazon.com/awssupport/latest/user/trusted-advisor.html)


## SAA-23-011-C001

**Objetivo:** Custos de storage: retenção, requisições e recuperação

**Pergunta:** Como remover versões antigas sem valor pode reduzir custo S3?

**Resposta:** Reduzindo armazenamento retido desnecessariamente por políticas adequadas.

**Saiba mais:** Conferir obrigações de retenção antes de expirar dados.

**Fonte:** [Managing the lifecycle of objects - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html)


## SAA-23-011-C002

**Objetivo:** Custos de storage: retenção, requisições e recuperação

**Pergunta:** Trocar para armazenamento mais barato sempre reduz custo se as recuperações forem frequentes?

**Resposta:** Não.

**Saiba mais:** Taxas de acesso e recuperação podem inverter a economia.

**Fonte:** [Managing the lifecycle of objects - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html)


## SAA-23-012-C001

**Objetivo:** Custos de banco: capacidade, réplicas, backup e licenças

**Pergunta:** Qual desperdício pode existir em banco não produtivo executando continuamente sem necessidade?

**Resposta:** Capacidade provisionada ociosa.

**Saiba mais:** Avaliar horários, operação e regras do serviço antes de automatizar parada.

**Fonte:** [Managed Relational Database - Amazon RDS Pricing - Amazon Web Services](https://aws.amazon.com/rds/pricing/)


## SAA-23-012-C002

**Objetivo:** Custos de banco: capacidade, réplicas, backup e licenças

**Pergunta:** Por que custo de licença pode mudar a escolha de engine de banco?

**Resposta:** Ele compõe o custo total além da infraestrutura.

**Saiba mais:** Migração ainda precisa preservar compatibilidade e função.

**Fonte:** [Managed Relational Database - Amazon RDS Pricing - Amazon Web Services](https://aws.amazon.com/rds/pricing/)


## SAA-23-013-C001

**Objetivo:** Custos de rede: NAT, endpoints e transferência

**Pergunta:** Qual decisão de rede pode evitar processamento de tráfego S3 por NAT em cenários compatíveis?

**Resposta:** Usar gateway endpoint S3 e rotas adequadas.

**Saiba mais:** Comparar toda a topologia, não só a existência do endpoint.

**Fonte:** [Amazon VPC Pricing](https://aws.amazon.com/vpc/pricing/)


## SAA-23-013-C002

**Objetivo:** Custos de rede: NAT, endpoints e transferência

**Pergunta:** Por que mover tráfego entre AZs sem necessidade merece revisão?

**Resposta:** Pode aumentar custo e dependências entre zonas.

**Saiba mais:** A economia precisa ser equilibrada com resiliência.

**Fonte:** [Amazon VPC Pricing](https://aws.amazon.com/vpc/pricing/)


## SAA-23-014-C001

**Objetivo:** Ambientes não produtivos: planejar horários e capacidade

**Pergunta:** Qual estratégia reduz custo de ambientes de desenvolvimento usados apenas em horários definidos?

**Resposta:** Agendar início e parada de recursos compatíveis.

**Saiba mais:** Verificar dependências e custos que persistem quando a computação para.

**Fonte:** [Automate starting and stopping AWS instances - Instance Scheduler on AWS](https://docs.aws.amazon.com/solutions/latest/instance-scheduler-on-aws/solution-overview.html)


## SAA-23-014-C002

**Objetivo:** Ambientes não produtivos: planejar horários e capacidade

**Pergunta:** Desligar a produção fora do expediente é automaticamente a mesma otimização?

**Resposta:** Não.

**Saiba mais:** A janela de serviço deve ser definida pelos requisitos do negócio.

**Fonte:** [Automate starting and stopping AWS instances - Instance Scheduler on AWS](https://docs.aws.amazon.com/solutions/latest/instance-scheduler-on-aws/solution-overview.html)


## SAA-23-015-C001

**Objetivo:** Rightsizing antes de compromisso: ordenar otimizações

**Pergunta:** O que significa rightsizing?

**Resposta:** Adequar tipo, tamanho e quantidade de recursos ao uso necessário.

**Saiba mais:** Não é reduzir tudo indiscriminadamente.

**Fonte:** [Select the correct resource type, size, and number - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/select-the-correct-resource-type-size-and-number.html)


## SAA-23-015-C002

**Objetivo:** Rightsizing antes de compromisso: ordenar otimizações

**Pergunta:** Qual risco de dimensionar apenas pela média e ignorar picos críticos?

**Resposta:** Degradar o serviço nos períodos importantes.

**Saiba mais:** Usar métricas e requisitos de desempenho para definir margem.

**Fonte:** [Select the correct resource type, size, and number - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/select-the-correct-resource-type-size-and-number.html)


## SAA-23-016-C001

**Objetivo:** Controle de custos multi-account: selecionar alertas e responsáveis

**Pergunta:** Por que atribuir responsáveis a alertas de custo?

**Resposta:** Para que a informação provoque investigação e ação.

**Saiba mais:** Um alerta sem dono pode não produzir resposta.

**Fonte:** [Managing your costs with AWS Budgets - AWS Cost Management](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)


## SAA-23-016-C002

**Objetivo:** Controle de custos multi-account: selecionar alertas e responsáveis

**Pergunta:** Um orçamento é prova de que nenhum gasto acima dele ocorrerá?

**Resposta:** Não.

**Saiba mais:** O comportamento dos alertas e ações precisa ser entendido e configurado.

**Fonte:** [Managing your costs with AWS Budgets - AWS Cost Management](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)


## SAA-23-017-C001

**Objetivo:** License Manager: reconhecer gestão de licenciamento

**Pergunta:** Qual serviço ajuda a administrar uso de licenças de software em ambientes suportados?

**Resposta:** AWS License Manager.

**Saiba mais:** Ele ajuda governança; não altera automaticamente os termos do fornecedor.

**Fonte:** [What is AWS License Manager? - AWS License Manager](https://docs.aws.amazon.com/license-manager/latest/userguide/license-manager.html)


## SAA-23-017-C002

**Objetivo:** License Manager: reconhecer gestão de licenciamento

**Pergunta:** Mover um software para cloud garante que sua licença possa ser reutilizada sem restrições?

**Resposta:** Não.

**Saiba mais:** Conferir direitos de uso e requisitos de hardware ou tenancy.

**Fonte:** [What is AWS License Manager? - AWS License Manager](https://docs.aws.amazon.com/license-manager/latest/userguide/license-manager.html)

