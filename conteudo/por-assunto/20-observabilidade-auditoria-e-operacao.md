# 20 · Observabilidade, auditoria e operação

30 cartões · primeira edição · 05/10/2026.


## SAA-20-001-C001

**Objetivo:** CloudWatch, CloudTrail e Config: distinguir métricas, chamadas e configuração

**Pergunta:** Qual serviço AWS acompanha métricas, logs e alarmes de workloads?

**Resposta:** Amazon CloudWatch.

**Saiba mais:** Ele observa comportamento operacional; auditoria de chamadas possui outra função central.

**Fonte:** [What is Amazon CloudWatch? - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html)


## SAA-20-001-C002

**Objetivo:** CloudWatch, CloudTrail e Config: distinguir métricas, chamadas e configuração

**Pergunta:** Qual serviço ajuda a responder quem executou uma chamada de API AWS?

**Resposta:** AWS CloudTrail.

**Saiba mais:** O tipo de evento e a configuração de registro determinam a evidência disponível.

**Fonte:** [What Is AWS CloudTrail? - AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)


## SAA-20-002-C001

**Objetivo:** CloudWatch metrics e dimensions: localizar sinais de comportamento

**Pergunta:** Qual papel das dimensions em uma métrica CloudWatch?

**Resposta:** Identificar características da série, como o recurso monitorado.

**Saiba mais:** Misturar séries pode ocultar o comportamento de uma instância específica.

**Fonte:** [Metrics concepts - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html)


## SAA-20-002-C002

**Objetivo:** CloudWatch metrics e dimensions: localizar sinais de comportamento

**Pergunta:** Por que a média de latência não descreve sozinha a experiência dos usuários?

**Resposta:** Ela pode esconder a cauda de requisições lentas.

**Saiba mais:** Percentis e distribuição ajudam a entender o problema.

**Fonte:** [Metrics concepts - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html)


## SAA-20-003-C001

**Objetivo:** Alarmes e ações: conectar limiar a resposta operacional

**Pergunta:** Qual objetivo de um alarme CloudWatch?

**Resposta:** Avaliar uma condição de métrica e realizar ações configuradas ao mudar de estado.

**Saiba mais:** Métrica sem resposta operacional não garante reação ao incidente.

**Fonte:** [Using Amazon CloudWatch alarms - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html)


## SAA-20-003-C002

**Objetivo:** Alarmes e ações: conectar limiar a resposta operacional

**Pergunta:** Definir um threshold sem considerar períodos de avaliação pode causar qual problema?

**Resposta:** Alarmes excessivos ou detecção tardia.

**Saiba mais:** A configuração precisa equilibrar ruído e tempo de resposta.

**Fonte:** [Using Amazon CloudWatch alarms - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html)


## SAA-20-004-C001

**Objetivo:** Logs, filtros de métricas e consultas: investigar sintomas

**Pergunta:** Qual recurso permite consultar logs de forma interativa no CloudWatch?

**Resposta:** CloudWatch Logs Insights.

**Saiba mais:** Escolher intervalo e grupos relevantes reduz trabalho de análise.

**Fonte:** [Analyzing log data with CloudWatch Logs Insights - Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AnalyzingLogData.html)


## SAA-20-004-C002

**Objetivo:** Logs, filtros de métricas e consultas: investigar sintomas

**Pergunta:** Como transformar ocorrências específicas de logs em sinal para alarmes?

**Resposta:** Criar filtros de métricas compatíveis.

**Saiba mais:** O padrão deve corresponder ao formato real dos logs.

**Fonte:** [Creating metrics from log events using filters - Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/MonitoringLogData.html)


## SAA-20-005-C001

**Objetivo:** Métricas do sistema e agente: identificar visibilidade adicional

**Pergunta:** Métricas padrão EC2 incluem automaticamente toda métrica interna de memória e disco do sistema operacional?

**Resposta:** Não.

**Saiba mais:** CloudWatch agent ou instrumentação apropriada pode ser necessário.

**Fonte:** [Collect metrics, logs, and traces using the CloudWatch agent - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html)


## SAA-20-005-C002

**Objetivo:** Métricas do sistema e agente: identificar visibilidade adicional

**Pergunta:** Por que memória deve ser monitorada mesmo com CPU saudável?

**Resposta:** Uma aplicação pode estar limitada por RAM.

**Saiba mais:** Analisar apenas CPU pode levar a dimensionamento incorreto.

**Fonte:** [Collect metrics, logs, and traces using the CloudWatch agent - Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html)


## SAA-20-006-C001

**Objetivo:** CloudTrail management events e data events: selecionar auditoria

**Pergunta:** Qual categoria CloudTrail registra operações de administração de recursos?

**Resposta:** Management events.

**Saiba mais:** É diferente de registrar cada operação de dados do recurso.

**Fonte:** [Logging management events - AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-management-events-with-cloudtrail.html)


## SAA-20-006-C002

**Objetivo:** CloudTrail management events e data events: selecionar auditoria

**Pergunta:** Para auditar operações como acesso a objetos S3, qual categoria CloudTrail verificar?

**Resposta:** Data events para os recursos suportados.

**Saiba mais:** É preciso configurar o registro adequado; não presumir cobertura por qualquer trilha padrão.

**Fonte:** [Logging data events - AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-data-events-with-cloudtrail.html)


## SAA-20-007-C001

**Objetivo:** Trails entre regiões e contas: planejar centralização

**Pergunta:** Qual recurso centraliza uma trilha para contas de uma organização AWS?

**Resposta:** Organization trail.

**Saiba mais:** Permissões e armazenamento central precisam ser protegidos.

**Fonte:** [Creating a trail for an organization - AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html)


## SAA-20-007-C002

**Objetivo:** Trails entre regiões e contas: planejar centralização

**Pergunta:** Por que guardar logs de auditoria apenas na conta administrada pelo workload pode ser insuficiente?

**Resposta:** O comprometimento dessa conta pode afetar a preservação da evidência.

**Saiba mais:** Separação de funções e controles de retenção ajudam a proteger a auditoria.

**Fonte:** [Creating a trail for an organization - AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html)


## SAA-20-008-C001

**Objetivo:** Config rules e histórico: avaliar conformidade

**Pergunta:** Qual serviço mantém histórico de configurações e avalia regras de conformidade de recursos?

**Resposta:** AWS Config.

**Saiba mais:** Ele complementa a auditoria de APIs e a observação de métricas.

**Fonte:** [What Is AWS Config? - AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html)


## SAA-20-008-C002

**Objetivo:** Config rules e histórico: avaliar conformidade

**Pergunta:** Uma regra Config não conforme prova que uma requisição foi bloqueada em tempo real?

**Resposta:** Não.

**Saiba mais:** Detecção de configuração e prevenção de ação são mecanismos diferentes.

**Fonte:** [What Is AWS Config? - AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html)


## SAA-20-009-C001

**Objetivo:** X-Ray: localizar dependências e latência distribuída

**Pergunta:** Qual recurso ajuda a rastrear requisições por serviços e localizar latência distribuída?

**Resposta:** AWS X-Ray.

**Saiba mais:** Instrumentação e suporte do workload determinam a visibilidade.

**Fonte:** [What is AWS X-Ray? - AWS X-Ray](https://docs.aws.amazon.com/xray/latest/devguide/aws-xray.html)


## SAA-20-009-C002

**Objetivo:** X-Ray: localizar dependências e latência distribuída

**Pergunta:** Logs isolados de cada serviço mostram automaticamente a relação completa entre chamadas?

**Resposta:** Não.

**Saiba mais:** Correlação e tracing ajudam a reconstruir o caminho da requisição.

**Fonte:** [What is AWS X-Ray? - AWS X-Ray](https://docs.aws.amazon.com/xray/latest/devguide/aws-xray.html)


## SAA-20-010-C001

**Objetivo:** Health Dashboard: distinguir incidente AWS de problema da aplicação

**Pergunta:** Qual serviço fornece informações sobre eventos de saúde AWS relevantes à conta e recursos?

**Resposta:** AWS Health.

**Saiba mais:** Complementa a observabilidade da aplicação do cliente.

**Fonte:** [What is AWS Health? - AWS Health](https://docs.aws.amazon.com/health/latest/ug/what-is-aws-health.html)


## SAA-20-010-C002

**Objetivo:** Health Dashboard: distinguir incidente AWS de problema da aplicação

**Pergunta:** Ausência de incidente AWS publicado garante que a aplicação está saudável?

**Resposta:** Não.

**Saiba mais:** O defeito pode estar no código, nos dados ou na configuração do cliente.

**Fonte:** [What is AWS Health? - AWS Health](https://docs.aws.amazon.com/health/latest/ug/what-is-aws-health.html)


## SAA-20-011-C001

**Objetivo:** Systems Manager: relacionar inventário, parâmetros e automação

**Pergunta:** Qual serviço reúne capacidades como inventário, automação e gerenciamento operacional de recursos?

**Resposta:** AWS Systems Manager.

**Saiba mais:** A disponibilidade de cada capacidade depende dos recursos e configurações suportados.

**Fonte:** [What is AWS Systems Manager? - AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html)


## SAA-20-011-C002

**Objetivo:** Systems Manager: relacionar inventário, parâmetros e automação

**Pergunta:** Automatizar uma tarefa administrativa dispensa definir permissões da automação?

**Resposta:** Não.

**Saiba mais:** A identidade de execução deve possuir apenas o necessário.

**Fonte:** [What is AWS Systems Manager? - AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html)


## SAA-20-012-C001

**Objetivo:** CloudFormation: projetar infraestrutura reproduzível

**Pergunta:** Qual serviço provisiona recursos a partir de templates declarativos de infraestrutura?

**Resposta:** AWS CloudFormation.

**Saiba mais:** A infraestrutura descrita pode ser versionada e reproduzida.

**Fonte:** [What is CloudFormation? - AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)


## SAA-20-012-C002

**Objetivo:** CloudFormation: projetar infraestrutura reproduzível

**Pergunta:** Por que infraestrutura como código ajuda recuperação de desastres?

**Resposta:** Reduz dependência de recriação manual e configurações esquecidas.

**Saiba mais:** Código, parâmetros e artefatos também precisam estar disponíveis na recuperação.

**Fonte:** [What is CloudFormation? - AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)


## SAA-20-013-C001

**Objetivo:** CloudFormation drift, change sets e StackSets: reconhecer controles

**Pergunta:** O que drift representa em CloudFormation?

**Resposta:** Diferença entre a configuração esperada e o estado detectado de recursos suportados.

**Saiba mais:** Nem todo atributo pode ser detectado; conhecer o alcance da verificação.

**Fonte:** [Detect unmanaged configuration changes to stacks and resources with drift detection - AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-stack-drift.html)


## SAA-20-013-C002

**Objetivo:** CloudFormation drift, change sets e StackSets: reconhecer controles

**Pergunta:** Qual recurso CloudFormation distribui stacks por múltiplas contas e regiões?

**Resposta:** StackSets.

**Saiba mais:** Permissões, organização e parâmetros precisam ser planejados.

**Fonte:** [StackSets concepts - AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-concepts.html)


## SAA-20-014-C001

**Objetivo:** Managed Prometheus e Grafana: reconhecer observabilidade gerenciada

**Pergunta:** Qual serviço gerencia armazenamento e consulta de métricas compatíveis com Prometheus?

**Resposta:** Amazon Managed Service for Prometheus.

**Saiba mais:** É útil para workloads instrumentados nesse ecossistema.

**Fonte:** [What is Amazon Managed Service for Prometheus? - Amazon Managed Service for Prometheus](https://docs.aws.amazon.com/prometheus/latest/userguide/what-is-Amazon-Managed-Service-Prometheus.html)


## SAA-20-014-C002

**Objetivo:** Managed Prometheus e Grafana: reconhecer observabilidade gerenciada

**Pergunta:** Qual serviço fornece Grafana gerenciado para visualização de dados de fontes suportadas?

**Resposta:** Amazon Managed Grafana.

**Saiba mais:** Dashboards dependem das fontes e permissões configuradas.

**Fonte:** [What is Amazon Managed Grafana? - Amazon Managed Grafana](https://docs.aws.amazon.com/grafana/latest/userguide/what-is-Amazon-Managed-Service-Grafana.html)


## SAA-20-015-C001

**Objetivo:** Retenção e centralização de logs: avaliar custo e segurança

**Pergunta:** Por que definir retenção explícita para logs?

**Resposta:** Para equilibrar investigação, requisitos de guarda e custo.

**Saiba mais:** Guardar tudo indefinidamente pode acumular despesas sem necessidade.

**Fonte:** [Working with log groups and log streams - Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/Working-with-log-groups-and-streams.html)


## SAA-20-015-C002

**Objetivo:** Retenção e centralização de logs: avaliar custo e segurança

**Pergunta:** Por que dados sensíveis não devem ser registrados indiscriminadamente em logs?

**Resposta:** Logs também exigem proteção e controle de acesso.

**Saiba mais:** Observabilidade não justifica expor segredos ou dados pessoais sem necessidade.

**Fonte:** [Working with log groups and log streams - Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/Working-with-log-groups-and-streams.html)

