# 11 · RDS: laboratórios e diagnóstico

16 cartões · primeira edição · 05/10/2026.


## SAA-11-001-C001

**Objetivo:** Falha do banco primário: distinguir failover de promoção manual

**Pergunta:** Uma aplicação perde conexões durante failover RDS. Qual comportamento ela deve implementar?

**Resposta:** Reconectar e tratar falhas transitórias apropriadamente.

**Saiba mais:** Alta disponibilidade do serviço não torna toda conexão cliente indestrutível.

**Fonte:** [Failing over a Multi-AZ DB instance for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.Failover.html)


## SAA-11-001-C002

**Objetivo:** Falha do banco primário: distinguir failover de promoção manual

**Pergunta:** É seguro fixar permanentemente o IP resolvido do endpoint RDS?

**Resposta:** Não.

**Saiba mais:** Mudanças de infraestrutura e failover podem alterar o destino.

**Fonte:** [Failing over a Multi-AZ DB instance for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.Failover.html)


## SAA-11-002-C001

**Objetivo:** Lentidão de leitura: escolher réplica ou cache pelo acesso

**Pergunta:** Aumentou a carga de consultas de leitura. Uma standby tradicional Multi-AZ resolve diretamente a distribuição dessas consultas?

**Resposta:** Não.

**Saiba mais:** Avaliar read replicas e cache conforme consistência e padrão de acesso.

**Fonte:** [Working with DB instance read replicas - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)


## SAA-11-002-C002

**Objetivo:** Lentidão de leitura: escolher réplica ou cache pelo acesso

**Pergunta:** Uma consulta na réplica não vê uma gravação recente. Qual hipótese investigar?

**Resposta:** Atraso da replicação.

**Saiba mais:** Direcionar leituras sensíveis à consistência ao destino apropriado.

**Fonte:** [Working with DB instance read replicas - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)


## SAA-11-003-C001

**Objetivo:** Tempestade de conexões: avaliar uso de proxy

**Pergunta:** Milhares de funções abrem conexões curtas ao banco. Qual recurso pode reduzir essa pressão?

**Resposta:** RDS Proxy.

**Saiba mais:** Ainda dimensionar concorrência e capacidade do banco.

**Fonte:** [Amazon RDS Proxy - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-proxy.html)


## SAA-11-003-C002

**Objetivo:** Tempestade de conexões: avaliar uso de proxy

**Pergunta:** Se o banco está lento por consulta sem índice, pooling resolve a causa automaticamente?

**Resposta:** Não.

**Saiba mais:** É necessário otimizar o acesso aos dados.

**Fonte:** [Amazon RDS Proxy - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-proxy.html)


## SAA-11-004-C001

**Objetivo:** Restauração de snapshot: identificar recurso criado e ponto recuperado

**Pergunta:** Restaurar snapshot RDS substitui automaticamente os dados da instância original?

**Resposta:** Não. A restauração cria uma nova instância.

**Saiba mais:** Planejar validação e mudança de endpoint da aplicação.

**Fonte:** [Restoring to a DB instance - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_RestoreFromSnapshot.html)


## SAA-11-004-C002

**Objetivo:** Restauração de snapshot: identificar recurso criado e ponto recuperado

**Pergunta:** Após restaurar um snapshot, basta presumir que toda configuração operacional está idêntica?

**Resposta:** Não.

**Saiba mais:** Verificar grupos de parâmetros, rede, segurança e opções aplicáveis.

**Fonte:** [Restoring to a DB instance - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_RestoreFromSnapshot.html)


## SAA-11-005-C001

**Objetivo:** Recuperação point-in-time: interpretar janela disponível

**Pergunta:** É possível escolher qualquer data histórica para PITR independentemente da retenção?

**Resposta:** Não.

**Saiba mais:** O instante precisa estar dentro da janela recuperável disponível.

**Fonte:** [Restoring a DB instance to a specified time for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIT.html)


## SAA-11-005-C002

**Objetivo:** Recuperação point-in-time: interpretar janela disponível

**Pergunta:** PITR e read replica resolvem o mesmo problema?

**Resposta:** Não.

**Saiba mais:** PITR recupera um estado anterior; réplica atende replicação e outros objetivos conforme o desenho.

**Fonte:** [Restoring a DB instance to a specified time for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIT.html)


## SAA-11-006-C001

**Objetivo:** Criptografia e snapshots compartilhados: identificar permissões necessárias

**Pergunta:** Ao compartilhar snapshot criptografado, qual dependência precisa de análise além do snapshot?

**Resposta:** A chave KMS e suas permissões.

**Saiba mais:** Existem restrições conforme o tipo de chave e o procedimento de compartilhamento.

**Fonte:** [Sharing a DB snapshot for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ShareSnapshot.html)


## SAA-11-006-C002

**Objetivo:** Criptografia e snapshots compartilhados: identificar permissões necessárias

**Pergunta:** Por que uma cópia cifrada por chave própria pode fazer parte do fluxo de compartilhamento?

**Resposta:** Para viabilizar controle de autorização adequado à conta destinatária.

**Saiba mais:** Verificar o procedimento suportado antes de compartilhar.

**Fonte:** [Sharing a DB snapshot for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ShareSnapshot.html)


## SAA-11-007-C001

**Objetivo:** Endpoint incorreto: diagnosticar leitura enviada ao writer

**Pergunta:** Leituras destinadas às réplicas continuam chegando ao writer. O que verificar na aplicação?

**Resposta:** O endpoint e a separação de conexões de leitura e escrita.

**Saiba mais:** Criar réplicas não altera automaticamente strings de conexão.

**Fonte:** [Amazon Aurora endpoint connections - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Endpoints.html)


## SAA-11-007-C002

**Objetivo:** Endpoint incorreto: diagnosticar leitura enviada ao writer

**Pergunta:** O reader endpoint deve ser usado indiscriminadamente para transações de escrita?

**Resposta:** Não.

**Saiba mais:** O acesso deve usar o endpoint compatível com a operação.

**Fonte:** [Amazon Aurora endpoint connections - Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Endpoints.html)


## SAA-11-008-C001

**Objetivo:** Métrica de CPU, IOPS e conexões: identificar gargalo dominante

**Pergunta:** CPU normal e aumento de latência de armazenamento indicam investigar qual recurso?

**Resposta:** I/O do banco.

**Saiba mais:** Usar métricas de espera, throughput e IOPS para confirmar.

**Fonte:** [Monitoring tools for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/MonitoringOverview.html)


## SAA-11-008-C002

**Objetivo:** Métrica de CPU, IOPS e conexões: identificar gargalo dominante

**Pergunta:** Muitas conexões ociosas podem consumir recursos mesmo com poucas consultas?

**Resposta:** Sim.

**Saiba mais:** Gerenciar pools e limites de conexões ajuda a evitar desperdício.

**Fonte:** [Monitoring tools for Amazon RDS - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/MonitoringOverview.html)

