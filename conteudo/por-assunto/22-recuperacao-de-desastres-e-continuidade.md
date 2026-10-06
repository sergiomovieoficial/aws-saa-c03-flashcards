# 22 · Recuperação de desastres e continuidade

28 cartões · primeira edição · 05/10/2026.


## SAA-22-001-C001

**Objetivo:** RTO e RPO: selecionar arquitetura por objetivos mensuráveis

**Pergunta:** Um negócio tolera perder até dez minutos de dados. Qual objetivo esse requisito descreve?

**Resposta:** RPO de dez minutos.

**Saiba mais:** É uma restrição de perda de dados, não de duração da indisponibilidade.

**Fonte:** [What is Recovery Time Objective (RTO)? - RTO Explained - AWS](https://aws.amazon.com/what-is/recovery-time-objective/)


## SAA-22-001-C002

**Objetivo:** RTO e RPO: selecionar arquitetura por objetivos mensuráveis

**Pergunta:** Um negócio exige retorno do serviço em meia hora. Qual objetivo descreve isso?

**Resposta:** RTO de trinta minutos.

**Saiba mais:** Medir o tempo completo de recuperação e validação.

**Fonte:** [What is Recovery Time Objective (RTO)? - RTO Explained - AWS](https://aws.amazon.com/what-is/recovery-time-objective/)


## SAA-22-002-C001

**Objetivo:** Backup and restore: avaliar tempo e custo de recuperação

**Pergunta:** Qual estratégia de DR reconstrói o ambiente a partir de cópias protegidas após o evento?

**Resposta:** Backup and restore.

**Saiba mais:** Costuma exigir mais etapas de recuperação que um ambiente já operante.

**Fonte:** [Disaster recovery options in the cloud - Disaster Recovery of Workloads on AWS: Recovery in the Cloud](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html)


## SAA-22-003-C001

**Objetivo:** Pilot light: identificar componentes ativos e recomposição

**Pergunta:** Qual estratégia mantém componentes essenciais e dados preparados, ativando o restante no desastre?

**Resposta:** Pilot light.

**Saiba mais:** É preciso planejar como a capacidade restante será criada.

**Fonte:** [Disaster recovery options in the cloud - Disaster Recovery of Workloads on AWS: Recovery in the Cloud](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html)


## SAA-22-004-C001

**Objetivo:** Warm standby: avaliar ambiente reduzido pronto para escalar

**Pergunta:** Qual estratégia mantém uma versão funcional reduzida pronta para ampliar capacidade?

**Resposta:** Warm standby.

**Saiba mais:** Seu custo e tempo de recuperação diferem de simplesmente guardar backups.

**Fonte:** [Disaster recovery options in the cloud - Disaster Recovery of Workloads on AWS: Recovery in the Cloud](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html)


## SAA-22-005-C001

**Objetivo:** Active-active: avaliar tráfego e sincronização de dados

**Pergunta:** Qual estratégia mantém múltiplos locais atendendo tráfego normalmente?

**Resposta:** Multi-site active-active.

**Saiba mais:** Dados, conflitos e failover precisam ser projetados explicitamente.

**Fonte:** [Disaster recovery options in the cloud - Disaster Recovery of Workloads on AWS: Recovery in the Cloud](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html)


## SAA-22-006-C001

**Objetivo:** Multi-AZ e Multi-Region: distinguir tipos de falha atendidos

**Pergunta:** Multi-AZ dentro de uma região protege automaticamente contra toda interrupção regional?

**Resposta:** Não.

**Saiba mais:** Falhas regionais podem exigir uma estratégia entre regiões.

**Fonte:** [REL10-BP01 Deploy the workload to multiple locations - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_fault_isolation_multiaz_region_system.html)


## SAA-22-006-C002

**Objetivo:** Multi-AZ e Multi-Region: distinguir tipos de falha atendidos

**Pergunta:** Multi-Region é necessário para todo sistema, independentemente do requisito?

**Resposta:** Não.

**Saiba mais:** Complexidade e custo devem ser justificados pelos objetivos do negócio.

**Fonte:** [REL10-BP01 Deploy the workload to multiple locations - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_fault_isolation_multiaz_region_system.html)


## SAA-22-007-C001

**Objetivo:** Failover e failback: planejar ida e retorno

**Pergunta:** O que é failback?

**Resposta:** O retorno planejado ao ambiente preferencial após operar em contingência.

**Saiba mais:** Pode exigir sincronizar alterações feitas durante a contingência.

**Fonte:** [Testing disaster recovery - Disaster Recovery of Workloads on AWS: Recovery in the Cloud](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/testing-disaster-recovery.html)


## SAA-22-007-C002

**Objetivo:** Failover e failback: planejar ida e retorno

**Pergunta:** Por que testar apenas a ida para contingência deixa um risco operacional?

**Resposta:** O retorno pode ter dependências e conflitos não avaliados.

**Saiba mais:** O plano precisa cobrir os dois sentidos.

**Fonte:** [Testing disaster recovery - Disaster Recovery of Workloads on AWS: Recovery in the Cloud](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/testing-disaster-recovery.html)


## SAA-22-008-C001

**Objetivo:** Backup, réplica e alta disponibilidade: distinguir proteções

**Pergunta:** Uma réplica que reproduz uma exclusão acidental substitui backup histórico?

**Resposta:** Não.

**Saiba mais:** Replicação e recuperação de versões anteriores têm finalidades distintas.

**Fonte:** [Back up data - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/back-up-data.html)


## SAA-22-008-C002

**Objetivo:** Backup, réplica e alta disponibilidade: distinguir proteções

**Pergunta:** Ter alta disponibilidade dispensa backup para corrupção lógica?

**Resposta:** Não.

**Saiba mais:** Um sistema disponível pode replicar dados incorretos rapidamente.

**Fonte:** [Back up data - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/back-up-data.html)


## SAA-22-009-C001

**Objetivo:** AWS Backup: planos, cofres e políticas de retenção

**Pergunta:** Qual serviço centraliza políticas de backup para recursos AWS suportados?

**Resposta:** AWS Backup.

**Saiba mais:** Verificar suporte de recurso, região e modalidade de cópia.

**Fonte:** [What is AWS Backup? - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html)


## SAA-22-009-C002

**Objetivo:** AWS Backup: planos, cofres e políticas de retenção

**Pergunta:** O que uma política de retenção define no contexto de backup?

**Resposta:** Por quanto tempo a cópia deve ser mantida conforme as regras aplicáveis.

**Saiba mais:** Retenção precisa atender recuperação e obrigações de guarda.

**Fonte:** [What is AWS Backup? - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html)


## SAA-22-010-C001

**Objetivo:** Backup entre contas e regiões: separar domínios de falha

**Pergunta:** Por que copiar backups para outra conta pode melhorar proteção?

**Resposta:** Separa administração e reduz dependência da conta do workload.

**Saiba mais:** Políticas e chaves precisam permitir a cópia e proteger o destino.

**Fonte:** [Creating backup copies across AWS accounts - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/create-cross-account-backup.html)


## SAA-22-010-C002

**Objetivo:** Backup entre contas e regiões: separar domínios de falha

**Pergunta:** Qual benefício de cópia de backup para outra região?

**Resposta:** Reduz dependência da região de origem para recuperação.

**Saiba mais:** Tempo de cópia e restauração precisam atender RPO e RTO.

**Fonte:** [Creating backup copies across AWS Regions - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/cross-region-backup.html)


## SAA-22-011-C001

**Objetivo:** Imutabilidade e proteção de backup: avaliar exclusão e ransomware

**Pergunta:** Qual recurso AWS Backup pode impor retenção protegida contra exclusões conforme o modo configurado?

**Resposta:** Backup Vault Lock.

**Saiba mais:** Governance e compliance possuem condições diferentes.

**Fonte:** [AWS Backup Vault Lock - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html)


## SAA-22-011-C002

**Objetivo:** Imutabilidade e proteção de backup: avaliar exclusão e ransomware

**Pergunta:** Um backup protegido contra exclusão dispensa testes de restauração?

**Resposta:** Não.

**Saiba mais:** Proteção da cópia não prova que a aplicação poderá ser recuperada corretamente.

**Fonte:** [AWS Backup Vault Lock - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html)


## SAA-22-012-C001

**Objetivo:** Replicação assíncrona: interpretar perda de dados possível

**Pergunta:** Por que replicação assíncrona pode implicar perda de dados em failover não planejado?

**Resposta:** Algumas alterações podem ainda não ter chegado ao destino.

**Saiba mais:** Avaliar lag e garantias da modalidade usada.

**Fonte:** [Using switchover or failover in Amazon Aurora Global Database - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database-disaster-recovery.html)


## SAA-22-012-C002

**Objetivo:** Replicação assíncrona: interpretar perda de dados possível

**Pergunta:** RPO zero deve ser presumido apenas porque há replicação entre regiões?

**Resposta:** Não.

**Saiba mais:** A garantia depende da arquitetura e do modo de replicação.

**Fonte:** [Using switchover or failover in Amazon Aurora Global Database - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database-disaster-recovery.html)


## SAA-22-013-C001

**Objetivo:** DNS e recuperação: avaliar propagação e cache

**Pergunta:** Por que uma mudança DNS de contingência pode não atingir todos os clientes imediatamente?

**Resposta:** Cópias em cache podem continuar válidas.

**Saiba mais:** Planejar TTL e comportamento de reconexão.

**Fonte:** [Creating Amazon Route 53 health checks - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html)


## SAA-22-013-C002

**Objetivo:** DNS e recuperação: avaliar propagação e cache

**Pergunta:** Apontar DNS para a região secundária basta se os dados e segredos não estão disponíveis lá?

**Resposta:** Não.

**Saiba mais:** O destino precisa estar operacional como sistema completo.

**Fonte:** [Creating Amazon Route 53 health checks - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html)


## SAA-22-014-C001

**Objetivo:** Quotas e capacidade na região de contingência

**Pergunta:** Qual risco existe se a região de DR tem quota menor que a capacidade necessária?

**Resposta:** A expansão de recuperação pode ser impedida.

**Saiba mais:** Quotas precisam ser preparadas antes do incidente.

**Fonte:** [Manage service quotas and constraints - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/manage-service-quotas-and-constraints.html)


## SAA-22-014-C002

**Objetivo:** Quotas e capacidade na região de contingência

**Pergunta:** Uma quota aprovada garante disponibilidade instantânea de qualquer tipo de instância?

**Resposta:** Não.

**Saiba mais:** Quota e capacidade física disponível são questões diferentes.

**Fonte:** [Manage service quotas and constraints - Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/manage-service-quotas-and-constraints.html)


## SAA-22-015-C001

**Objetivo:** Teste de restauração: comprovar objetivos de recuperação

**Pergunta:** Qual evidência comprova melhor capacidade de recuperação: backup concluído ou restauração testada?

**Resposta:** Restauração testada com validação de integridade e funcionamento.

**Saiba mais:** A existência do arquivo de backup é apenas parte da prova.

**Fonte:** [Restore testing - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/restore-testing.html)


## SAA-22-015-C002

**Objetivo:** Teste de restauração: comprovar objetivos de recuperação

**Pergunta:** O que medir em um exercício de restauração além do tempo de criar recursos?

**Resposta:** O tempo até o serviço validado voltar a atender e o ponto dos dados recuperados.

**Saiba mais:** Isso relaciona o teste aos objetivos reais.

**Fonte:** [Restore testing - AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/restore-testing.html)


## SAA-22-016-C001

**Objetivo:** Dependências externas: incluir certificados, segredos e artefatos

**Pergunta:** Além dos dados, o que precisa estar preparado para recriar a aplicação em DR?

**Resposta:** Código, configuração, infraestrutura e dependências de acesso.

**Saiba mais:** Uma base restaurada sozinha não é a aplicação completa.

**Fonte:** [Disaster recovery options in the cloud - Disaster Recovery of Workloads on AWS: Recovery in the Cloud](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html)


## SAA-22-016-C002

**Objetivo:** Dependências externas: incluir certificados, segredos e artefatos

**Pergunta:** Por que incluir chaves e permissões criptográficas no plano de recuperação?

**Resposta:** Dados cifrados podem ficar inacessíveis sem a autorização e a chave necessárias.

**Saiba mais:** O armazenamento da cópia não basta para provar recuperabilidade.

**Fonte:** [Multi-Region keys in AWS KMS - AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/multi-region-keys-overview.html)

