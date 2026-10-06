# 17 · Lambda, API Gateway e serverless

36 cartões · primeira edição · 05/10/2026.


## SAA-17-001-C001

**Objetivo:** Lambda: seleção por duração, estado e padrão de execução

**Pergunta:** Qual padrão favorece Lambda?

**Resposta:** Execução de código orientada a eventos, com duração e recursos compatíveis com o serviço.

**Saiba mais:** Não depender de um processo indefinido para manter estado local permanente.

**Fonte:** [What is AWS Lambda? - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)


## SAA-17-001-C002

**Objetivo:** Lambda: seleção por duração, estado e padrão de execução

**Pergunta:** Uma rotina que excede o tempo máximo de uma invocação Lambda deve ser mantida como uma única função longa?

**Resposta:** Não.

**Saiba mais:** Dividir ou usar execução apropriada, como containers ou jobs.

**Fonte:** [What is AWS Lambda? - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)


## SAA-17-002-C001

**Objetivo:** Memória e CPU: avaliar desempenho e custo por invocação

**Pergunta:** Aumentar memória da Lambda pode alterar mais que a quantidade de RAM?

**Resposta:** Sim. A alocação de CPU acompanha a configuração conforme o serviço.

**Saiba mais:** Uma função pode executar mais rápido e mudar o custo total.

**Fonte:** [Configure Lambda function memory - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-memory.html)


## SAA-17-002-C002

**Objetivo:** Memória e CPU: avaliar desempenho e custo por invocação

**Pergunta:** Por que menor memória não garante menor custo de uma função?

**Resposta:** A execução pode demorar mais.

**Saiba mais:** Comparar duração e recursos com medições.

**Fonte:** [Configure Lambda function memory - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-memory.html)


## SAA-17-003-C001

**Objetivo:** Concorrência reservada e provisionada: distinguir objetivos

**Pergunta:** Qual controle reserva uma parcela da concorrência para uma função e estabelece seu limite?

**Resposta:** Reserved concurrency.

**Saiba mais:** Ele não pré-inicializa ambientes de execução.

**Fonte:** [Understanding Lambda function scaling - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html)


## SAA-17-003-C002

**Objetivo:** Concorrência reservada e provisionada: distinguir objetivos

**Pergunta:** Qual controle prepara ambientes antecipadamente para reduzir latência de inicialização?

**Resposta:** Provisioned concurrency.

**Saiba mais:** Há custo e requisitos de configuração próprios.

**Fonte:** [Understanding Lambda function scaling - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html)


## SAA-17-004-C001

**Objetivo:** Cold start: identificar impacto e estratégias de mitigação

**Pergunta:** O que é um cold start no contexto Lambda?

**Resposta:** Inicialização de um ambiente antes de atender uma invocação.

**Saiba mais:** Dependências e código de inicialização influenciam o tempo.

**Fonte:** [Understanding the Lambda execution environment lifecycle - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtime-environment.html)


## SAA-17-004-C002

**Objetivo:** Cold start: identificar impacto e estratégias de mitigação

**Pergunta:** É seguro depender de reuso garantido do mesmo ambiente para preservar dados essenciais?

**Resposta:** Não.

**Saiba mais:** O ambiente pode ser substituído; estado durável deve estar em recurso apropriado.

**Fonte:** [Understanding the Lambda execution environment lifecycle - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtime-environment.html)


## SAA-17-005-C001

**Objetivo:** Invocações síncronas, assíncronas e event source mappings

**Pergunta:** Qual mecanismo Lambda lê de fontes como filas e streams para invocar a função?

**Resposta:** Event source mapping.

**Saiba mais:** A forma de lote, retry e checkpoint depende da origem.

**Fonte:** [How Lambda processes records from stream and queue-based event sources - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/invocation-eventsourcemapping.html)


## SAA-17-005-C002

**Objetivo:** Invocações síncronas, assíncronas e event source mappings

**Pergunta:** Em uma invocação assíncrona, o chamador aguarda o resultado completo da execução no mesmo fluxo de resposta?

**Resposta:** Não.

**Saiba mais:** Recebimento do evento e conclusão da execução são etapas distintas.

**Fonte:** [Invoking a Lambda function asynchronously - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html)


## SAA-17-006-C001

**Objetivo:** Retry, destinations e DLQ: interpretar tratamento por origem

**Pergunta:** Existe uma única política de retry Lambda igual para todas as origens?

**Resposta:** Não.

**Saiba mais:** Invocação síncrona, assíncrona e mapeamentos de origem têm comportamentos diferentes.

**Fonte:** [Understanding retry behavior in Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/invocation-retries.html)


## SAA-17-006-C002

**Objetivo:** Retry, destinations e DLQ: interpretar tratamento por origem

**Pergunta:** Por que configurar destino de falha ou DLQ exige conhecer o tipo de invocação?

**Resposta:** Porque os recursos e a responsabilidade pelo retry variam por integração.

**Saiba mais:** Não aplicar uma configuração de assíncrono indiscriminadamente ao polling de fila.

**Fonte:** [Understanding retry behavior in Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/invocation-retries.html)


## SAA-17-007-C001

**Objetivo:** Lambda com SQS: lotes, falhas parciais e concorrência

**Pergunta:** Uma função Lambda consumindo SQS recebe necessariamente uma mensagem por invocação?

**Resposta:** Não. Pode receber lotes conforme a configuração.

**Saiba mais:** O código deve tratar cada item e o comportamento de falha do lote.

**Fonte:** [Using Lambda with Amazon SQS - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html)


## SAA-17-007-C002

**Objetivo:** Lambda com SQS: lotes, falhas parciais e concorrência

**Pergunta:** Como limitar pressão de um consumidor Lambda sobre um banco?

**Resposta:** Controlar concorrência e dimensionar o fluxo e as dependências.

**Saiba mais:** Elasticidade do consumidor não significa elasticidade ilimitada do banco.

**Fonte:** [Using Lambda with Amazon SQS - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html)


## SAA-17-008-C001

**Objetivo:** Lambda na VPC: avaliar acesso privado e saída para internet

**Pergunta:** Colocar Lambda em uma subnet pública dá automaticamente acesso à internet pela interface da função?

**Resposta:** Não.

**Saiba mais:** É preciso configurar o caminho de saída apropriado para a função conectada à VPC.

**Fonte:** [Enable internet access for VPC-connected Lambda functions - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-vpc-internet.html)


## SAA-17-008-C002

**Objetivo:** Lambda na VPC: avaliar acesso privado e saída para internet

**Pergunta:** Por que adicionar VPC a uma Lambda sem necessidade pode introduzir dependências de rede?

**Resposta:** A função passa a depender da conectividade configurada para alcançar recursos.

**Saiba mais:** Mapear destinos privados e públicos antes de decidir.

**Fonte:** [Enable internet access for VPC-connected Lambda functions - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-vpc-internet.html)


## SAA-17-009-C001

**Objetivo:** Armazenamento temporário e EFS: avaliar estado e persistência

**Pergunta:** O diretório temporário da Lambda deve ser a única cópia durável de um arquivo importante?

**Resposta:** Não.

**Saiba mais:** O armazenamento é associado ao ambiente e não oferece persistência de negócio garantida.

**Fonte:** [Configure ephemeral storage for Lambda functions - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-ephemeral-storage.html)


## SAA-17-009-C002

**Objetivo:** Armazenamento temporário e EFS: avaliar estado e persistência

**Pergunta:** Qual integração oferece filesystem compartilhado para funções Lambda compatíveis?

**Resposta:** Amazon EFS.

**Saiba mais:** Exige configuração de rede, acesso e montagem apropriadas.

**Fonte:** [Configuring file system access for Lambda functions - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-filesystem.html)


## SAA-17-010-C001

**Objetivo:** Permissões de execução e de invocação: separar atores

**Pergunta:** Permissão para invocar uma Lambda concede ao invocador as permissões da execution role?

**Resposta:** Não.

**Saiba mais:** A role é usada pela função durante sua execução; a autorização de invocação é separada.

**Fonte:** [Managing permissions in AWS Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions.html)


## SAA-17-010-C002

**Objetivo:** Permissões de execução e de invocação: separar atores

**Pergunta:** Qual autorização revisar se a função executa, mas não consegue gravar em S3?

**Resposta:** A execution role e os controles do recurso de destino.

**Saiba mais:** Não ampliar apenas a policy de invocação.

**Fonte:** [Managing permissions in AWS Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions.html)


## SAA-17-011-C001

**Objetivo:** API Gateway REST, HTTP e WebSocket: escolher API

**Pergunta:** Ao escolher entre HTTP API e REST API, qual critério deve vir antes do preço?

**Resposta:** Os recursos necessários e suportados por cada modalidade.

**Saiba mais:** Uma opção mais simples pode não oferecer uma funcionalidade exigida.

**Fonte:** [Choose between REST APIs and HTTP APIs - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vs-rest.html)


## SAA-17-011-C002

**Objetivo:** API Gateway REST, HTTP e WebSocket: escolher API

**Pergunta:** Qual modalidade API Gateway atende comunicação bidirecional persistente por WebSocket?

**Resposta:** WebSocket API.

**Saiba mais:** É distinta de requisições HTTP convencionais de pergunta e resposta.

**Fonte:** [Overview of WebSocket APIs in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api-overview.html)


## SAA-17-012-C001

**Objetivo:** API Gateway throttling, quotas e cache: controlar consumo

**Pergunta:** Qual objetivo de throttling em uma API?

**Resposta:** Limitar taxa e rajadas de requisições para proteger capacidade.

**Saiba mais:** O cliente deve tratar respostas de limitação e retries adequados.

**Fonte:** [Throttle requests to your REST APIs for better throughput in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-request-throttling.html)


## SAA-17-012-C002

**Objetivo:** API Gateway throttling, quotas e cache: controlar consumo

**Pergunta:** Quando cache de API pode reduzir carga do backend?

**Resposta:** Quando respostas reutilizáveis podem ser armazenadas dentro da validade correta.

**Saiba mais:** Cuidado com respostas personalizadas e parâmetros que alteram o resultado.

**Fonte:** [Cache settings for REST APIs in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-caching.html)


## SAA-17-013-C001

**Objetivo:** API keys e autenticação: distinguir finalidade

**Pergunta:** API keys do API Gateway devem ser usadas como substituto geral de autenticação e autorização?

**Resposta:** Não.

**Saiba mais:** São voltadas a identificação e gestão de uso; aplicar mecanismo de autorização adequado.

**Fonte:** [Usage plans and API keys for REST APIs in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-api-usage-plans.html)


## SAA-17-013-C002

**Objetivo:** API keys e autenticação: distinguir finalidade

**Pergunta:** Quotas de usage plans devem ser tratadas como um mecanismo rígido para impor controle financeiro absoluto?

**Resposta:** Não.

**Saiba mais:** Verificar sua semântica e usar controles de custo e proteção adicionais.

**Fonte:** [Usage plans and API keys for REST APIs in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-api-usage-plans.html)


## SAA-17-014-C001

**Objetivo:** IAM, Cognito e Lambda authorizers: escolher autorização

**Pergunta:** Qual alternativa autoriza chamadas de identidades AWS usando assinatura apropriada?

**Resposta:** Autorização IAM.

**Saiba mais:** É adequada quando os clientes podem usar credenciais e assinatura AWS.

**Fonte:** [Control and manage access to REST APIs in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-control-access-to-api.html)


## SAA-17-014-C002

**Objetivo:** IAM, Cognito e Lambda authorizers: escolher autorização

**Pergunta:** Quando considerar um Lambda authorizer?

**Resposta:** Quando a API precisa de lógica de autorização personalizada suportada pela modalidade.

**Saiba mais:** A função de autorização também precisa ter latência, segurança e cache bem definidos.

**Fonte:** [Control and manage access to REST APIs in API Gateway - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-control-access-to-api.html)


## SAA-17-015-C001

**Objetivo:** Integrações privadas e VPC Link: conectar backends

**Pergunta:** Para que serve uma private integration com VPC Link no API Gateway?

**Resposta:** Conectar a API a backends privados compatíveis na VPC.

**Saiba mais:** Verificar modalidade de API e destinos suportados.

**Fonte:** [Set up a private integration - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-private-integration.html)


## SAA-17-015-C002

**Objetivo:** Integrações privadas e VPC Link: conectar backends

**Pergunta:** Uma private integration significa necessariamente que a API pública deixou de ser pública?

**Resposta:** Não.

**Saiba mais:** A visibilidade da entrada e o caminho até o backend são decisões distintas.

**Fonte:** [Set up a private integration - Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-private-integration.html)


## SAA-17-016-C001

**Objetivo:** Serverless com Step Functions: coordenar tarefas

**Pergunta:** Por que usar Step Functions para coordenar várias etapas em vez de uma função com espera e lógica extensa?

**Resposta:** Para tornar transições, erros e estado do workflow explícitos e gerenciados.

**Saiba mais:** A escolha deve considerar integrações e duração do processo.

**Fonte:** [What is Step Functions? - AWS Step Functions](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)


## SAA-17-016-C002

**Objetivo:** Serverless com Step Functions: coordenar tarefas

**Pergunta:** Step Functions substitui automaticamente o código de todas as tarefas?

**Resposta:** Não.

**Saiba mais:** Ele coordena etapas e integra serviços; cada tarefa ainda precisa realizar seu trabalho.

**Fonte:** [What is Step Functions? - AWS Step Functions](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)


## SAA-17-017-C001

**Objetivo:** Amplify e Serverless Application Repository: reconhecer abstrações

**Pergunta:** Qual serviço oferece recursos gerenciados para desenvolvimento e hospedagem de aplicações web compatíveis?

**Resposta:** AWS Amplify.

**Saiba mais:** É preciso avaliar quais componentes da solução são cobertos.

**Fonte:** [Welcome to AWS Amplify Hosting - AWS Amplify Hosting](https://docs.aws.amazon.com/amplify/latest/userguide/welcome.html)


## SAA-17-017-C002

**Objetivo:** Amplify e Serverless Application Repository: reconhecer abstrações

**Pergunta:** Qual recurso permite descobrir e implantar aplicações serverless empacotadas?

**Resposta:** AWS Serverless Application Repository.

**Saiba mais:** Revisar permissões e composição antes de adotar uma aplicação.

**Fonte:** [What Is the AWS Serverless Application Repository? - AWS Serverless Application Repository](https://docs.aws.amazon.com/serverlessrepo/latest/devguide/what-is-serverlessrepo.html)


## SAA-17-018-C001

**Objetivo:** Lambda, containers e EC2: decidir a partir das restrições

**Pergunta:** Qual opção avaliar se uma tarefa precisa de controle do sistema operacional?

**Resposta:** EC2, quando esse controle não é atendido pelos serviços mais gerenciados.

**Saiba mais:** O benefício de abstração não deve violar requisito funcional.

**Fonte:** [Choosing an AWS compute service - AWS Decision Guides](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/choosing-aws-compute-service.html)


## SAA-17-018-C002

**Objetivo:** Lambda, containers e EC2: decidir a partir das restrições

**Pergunta:** Qual fator pode favorecer Lambda para carga esporádica curta?

**Resposta:** Execução por evento sem manter capacidade de aplicação continuamente ativa.

**Saiba mais:** Comparar custo e limites do cenário específico.

**Fonte:** [Choosing an AWS compute service - AWS Decision Guides](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/choosing-aws-compute-service.html)

