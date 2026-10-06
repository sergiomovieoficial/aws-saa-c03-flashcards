# 26 · Well-Architected e decisões transversais

20 cartões · primeira edição · 05/10/2026.


## SAA-26-001-C001

**Objetivo:** Pilar segurança: aplicar defesa em camadas ao cenário

**Pergunta:** Qual pilar orienta identidade forte, proteção de dados e preparação para eventos de segurança?

**Resposta:** Segurança.

**Saiba mais:** Aplicar controles em camadas e observar o contexto do workload.

**Fonte:** [Security Pillar - AWS Well-Architected Framework - Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)


## SAA-26-001-C002

**Objetivo:** Pilar segurança: aplicar defesa em camadas ao cenário

**Pergunta:** Defesa em profundidade significa repetir o mesmo controle em todos os lugares?

**Resposta:** Não. Significa combinar camadas complementares.

**Saiba mais:** Rede, identidade, aplicação e dados têm riscos diferentes.

**Fonte:** [Security Pillar - AWS Well-Architected Framework - Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)


## SAA-26-002-C001

**Objetivo:** Pilar confiabilidade: reduzir falhas e recuperar serviço

**Pergunta:** Qual pilar trata de operação correta, recuperação e adaptação a mudanças de demanda?

**Resposta:** Confiabilidade.

**Saiba mais:** Falhas devem ser consideradas no desenho, não apenas após incidentes.

**Fonte:** [Reliability Pillar - AWS Well-Architected Framework - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)


## SAA-26-002-C002

**Objetivo:** Pilar confiabilidade: reduzir falhas e recuperar serviço

**Pergunta:** Por que remover um ponto único de falha pode exigir revisar dependências indiretas?

**Resposta:** A redundância visível pode depender do mesmo componente compartilhado.

**Saiba mais:** Analisar o sistema completo.

**Fonte:** [Reliability Pillar - AWS Well-Architected Framework - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)


## SAA-26-003-C001

**Objetivo:** Pilar eficiência de performance: escolher recursos pelo workload

**Pergunta:** Qual pilar orienta selecionar e utilizar recursos eficientemente para cumprir desempenho?

**Resposta:** Eficiência de performance.

**Saiba mais:** Escolhas devem evoluir conforme métricas, tecnologias e demanda.

**Fonte:** [Performance Efficiency Pillar - AWS Well-Architected Framework - Performance Efficiency Pillar](https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/welcome.html)


## SAA-26-003-C002

**Objetivo:** Pilar eficiência de performance: escolher recursos pelo workload

**Pergunta:** O recurso mais potente é sempre a escolha mais eficiente?

**Resposta:** Não.

**Saiba mais:** Pode haver outra arquitetura que entregue o requisito com melhor uso de recursos.

**Fonte:** [Performance Efficiency Pillar - AWS Well-Architected Framework - Performance Efficiency Pillar](https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/welcome.html)


## SAA-26-004-C001

**Objetivo:** Pilar otimização de custos: medir valor e utilização

**Pergunta:** Otimização de custos busca somente reduzir a fatura absoluta?

**Resposta:** Não. Busca atender objetivos de negócio com gasto eficiente.

**Saiba mais:** Uma redução que destrói o serviço não é uma otimização válida.

**Fonte:** [Cost Optimization Pillar - AWS Well-Architected Framework - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html)


## SAA-26-004-C002

**Objetivo:** Pilar otimização de custos: medir valor e utilização

**Pergunta:** Por que medir custo por unidade de trabalho pode ser útil?

**Resposta:** Relaciona gasto ao valor ou volume produzido.

**Saiba mais:** A conta total pode crescer enquanto a eficiência por transação melhora.

**Fonte:** [Cost Optimization Pillar - AWS Well-Architected Framework - Cost Optimization Pillar](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html)


## SAA-26-005-C001

**Objetivo:** Pilar excelência operacional: automatizar e observar mudanças

**Pergunta:** Qual pilar enfatiza execução de operações, aprendizado e melhoria contínua?

**Resposta:** Excelência operacional.

**Saiba mais:** Procedimentos, métricas e automação ajudam a operar de forma consistente.

**Fonte:** [Operational Excellence Pillar - AWS Well-Architected Framework - Operational Excellence Pillar](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/welcome.html)


## SAA-26-005-C002

**Objetivo:** Pilar excelência operacional: automatizar e observar mudanças

**Pergunta:** Por que mudanças pequenas e reversíveis ajudam operações?

**Resposta:** Reduzem o impacto e facilitam diagnóstico e retorno.

**Saiba mais:** Reversibilidade precisa ser planejada também para alterações de dados.

**Fonte:** [Operational Excellence Pillar - AWS Well-Architected Framework - Operational Excellence Pillar](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/welcome.html)


## SAA-26-006-C001

**Objetivo:** Pilar sustentabilidade: avaliar uso eficiente de recursos

**Pergunta:** Qual pilar trata de reduzir impacto ambiental dos workloads?

**Resposta:** Sustentabilidade.

**Saiba mais:** Melhor utilização e eliminação de trabalho desnecessário podem contribuir.

**Fonte:** [Sustainability Pillar - AWS Well-Architected Framework - Sustainability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/sustainability-pillar.html)


## SAA-26-006-C002

**Objetivo:** Pilar sustentabilidade: avaliar uso eficiente de recursos

**Pergunta:** Manter capacidade ociosa sem finalidade melhora automaticamente sustentabilidade por evitar scaling?

**Resposta:** Não.

**Saiba mais:** Utilização e demanda real precisam orientar a capacidade.

**Fonte:** [Sustainability Pillar - AWS Well-Architected Framework - Sustainability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/sustainability-pillar.html)


## SAA-26-007-C001

**Objetivo:** Trade-offs entre pilares: identificar requisito dominante

**Pergunta:** Uma solução active-active entre regiões pode melhorar recuperação e ao mesmo tempo aumentar quais custos?

**Resposta:** Complexidade operacional e gasto de infraestrutura e replicação.

**Saiba mais:** Trade-offs precisam ser justificados pelos objetivos.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)


## SAA-26-007-C002

**Objetivo:** Trade-offs entre pilares: identificar requisito dominante

**Pergunta:** Como desempatar duas soluções que cumprem a mesma funcionalidade em uma questão?

**Resposta:** Aplicar o critério explícito, como menor operação ou menor custo.

**Saiba mais:** Não trocar o critério pedido por uma preferência pessoal de tecnologia.

**Fonte:** [AWS Well-Architected Framework - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)


## SAA-26-008-C001

**Objetivo:** Well-Architected Tool: reconhecer função de revisão

**Pergunta:** Qual finalidade do AWS Well-Architected Tool?

**Resposta:** Apoiar revisões de workloads e identificar riscos conforme boas práticas.

**Saiba mais:** A ferramenta não redesenha automaticamente a aplicação.

**Fonte:** [What is AWS Well-Architected Tool? - AWS Well-Architected](https://docs.aws.amazon.com/wellarchitected/latest/userguide/tool.html)


## SAA-26-008-C002

**Objetivo:** Well-Architected Tool: reconhecer função de revisão

**Pergunta:** Uma revisão arquitetural deve ser executada apenas antes da primeira implantação?

**Resposta:** Não.

**Saiba mais:** Mudanças de requisitos e uso podem criar novos riscos.

**Fonte:** [What is AWS Well-Architected Tool? - AWS Well-Architected](https://docs.aws.amazon.com/wellarchitected/latest/userguide/tool.html)


## SAA-26-009-C001

**Objetivo:** Infraestrutura imutável e automação: reduzir divergência

**Pergunta:** Qual ideia central de infraestrutura imutável?

**Resposta:** Substituir componentes por versões definidas, em vez de acumular mudanças manuais neles.

**Saiba mais:** Ajuda a reduzir diferenças difíceis de reproduzir.

**Fonte:** [REL08-BP04 Deploy using immutable infrastructure - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_tracking_change_management_immutable_infrastructure.html)


## SAA-26-009-C002

**Objetivo:** Infraestrutura imutável e automação: reduzir divergência

**Pergunta:** Por que mudanças manuais não registradas dificultam recuperação?

**Resposta:** O ambiente real pode divergir do que os templates recriam.

**Saiba mais:** Rastrear e versionar configuração reduz essa lacuna.

**Fonte:** [REL08-BP04 Deploy using immutable infrastructure - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_tracking_change_management_immutable_infrastructure.html)


## SAA-26-010-C001

**Objetivo:** Quotas e capacidade: antecipar limites de expansão

**Pergunta:** Por que monitorar quotas antes de aumentar tráfego?

**Resposta:** O limite pode bloquear expansão mesmo quando a arquitetura suporta scaling.

**Saiba mais:** Solicitar ajuste durante uma emergência pode ser tarde.

**Fonte:** [Manage service quotas and constraints - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/manage-service-quotas-and-constraints.html)


## SAA-26-010-C002

**Objetivo:** Quotas e capacidade: antecipar limites de expansão

**Pergunta:** Quotas devem ser consideradas apenas na conta principal e região ativa?

**Resposta:** Não.

**Saiba mais:** Contas e regiões de contingência também precisam estar preparadas.

**Fonte:** [Manage service quotas and constraints - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/manage-service-quotas-and-constraints.html)

