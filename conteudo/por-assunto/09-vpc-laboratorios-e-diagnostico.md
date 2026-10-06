# 09 · VPC: laboratórios e diagnóstico

16 cartões · primeira edição · 05/10/2026.


## SAA-09-001-C001

**Objetivo:** Instância pública sem internet: verificar rota, endereço e regras

**Pergunta:** Uma EC2 tem rota para IGW, mas não tem IPv4 público. Essa rota basta para acesso IPv4 direto à internet?

**Resposta:** Não.

**Saiba mais:** O modelo de comunicação pública exige o endereço apropriado além da rota.

**Fonte:** [Enable internet access for a VPC using an internet gateway - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)


## SAA-09-001-C002

**Objetivo:** Instância pública sem internet: verificar rota, endereço e regras

**Pergunta:** Uma porta liberada no SG garante acesso público se não existe rota válida?

**Resposta:** Não.

**Saiba mais:** Roteamento e permissão precisam funcionar em conjunto.

**Fonte:** [Enable internet access for a VPC using an internet gateway - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)


## SAA-09-002-C001

**Objetivo:** Instância privada sem saída: seguir o caminho até o NAT

**Pergunta:** Instâncias privadas perderam saída após alterar a route table. Qual destino padrão investigar?

**Resposta:** O caminho para o NAT ou outro mecanismo de saída utilizado.

**Saiba mais:** Confirmar também saúde e conectividade do componente de saída.

**Fonte:** [Troubleshoot NAT gateways - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-troubleshooting.html)


## SAA-09-002-C002

**Objetivo:** Instância privada sem saída: seguir o caminho até o NAT

**Pergunta:** Um NAT público está em subnet sem rota para IGW. Qual parte do fluxo fica comprometida?

**Resposta:** A saída do NAT para a internet.

**Saiba mais:** A rota da subnet privada até o NAT é só uma etapa do caminho.

**Fonte:** [Troubleshoot NAT gateways - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-troubleshooting.html)


## SAA-09-003-C001

**Objetivo:** ALB não alcança aplicação: verificar porta e security groups

**Pergunta:** O ALB marca todos os targets como não saudáveis após mudar a porta da aplicação. O que conferir?

**Resposta:** Porta do target group, health check e regras de rede.

**Saiba mais:** A aplicação pode estar saudável em uma porta diferente da configurada no balanceador.

**Fonte:** [Troubleshoot your Application Load Balancers - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-troubleshooting.html)


## SAA-09-003-C002

**Objetivo:** ALB não alcança aplicação: verificar porta e security groups

**Pergunta:** O health check recebe código inesperado, mas a rede responde. Qual configuração analisar?

**Resposta:** Path e códigos aceitos pelo health check.

**Saiba mais:** Uma resposta HTTP existente não é necessariamente uma resposta considerada saudável.

**Fonte:** [Troubleshoot your Application Load Balancers - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-troubleshooting.html)


## SAA-09-004-C001

**Objetivo:** Aplicação não alcança banco privado: separar DNS, rota e autorização

**Pergunta:** Uma aplicação resolve o endpoint RDS, mas a conexão expira. Qual camada investigar antes da senha?

**Resposta:** Conectividade, rotas e regras de rede.

**Saiba mais:** Erro de autenticação e timeout de transporte indicam problemas diferentes.

**Fonte:** [Connecting to your MySQL DB instance - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html)


## SAA-09-004-C002

**Objetivo:** Aplicação não alcança banco privado: separar DNS, rota e autorização

**Pergunta:** Liberar o banco para 0.0.0.0/0 é a correção adequada para um SG interno mal configurado?

**Resposta:** Não.

**Saiba mais:** Ajustar a origem e a porta necessárias preserva o isolamento.

**Fonte:** [Connecting to your MySQL DB instance - Amazon Relational Database Service](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html)


## SAA-09-005-C001

**Objetivo:** NACL bloqueia retorno: identificar portas e direções

**Pergunta:** Uma NACL permite entrada TCP 443, mas nega a saída de retorno. Por que o serviço não responde?

**Resposta:** A NACL é stateless e avalia o retorno separadamente.

**Saiba mais:** É necessário considerar portas de origem e destino em cada direção.

**Fonte:** [Custom network ACLs for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/custom-network-acl.html)


## SAA-09-005-C002

**Objetivo:** NACL bloqueia retorno: identificar portas e direções

**Pergunta:** Em uma NACL, uma regra deny de número menor pode prevalecer sobre allow posterior?

**Resposta:** Sim.

**Saiba mais:** A avaliação segue a ordem numérica até encontrar correspondência.

**Fonte:** [Custom network ACLs for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/custom-network-acl.html)


## SAA-09-006-C001

**Objetivo:** Endpoint privado não resolve: inspecionar DNS e conectividade

**Pergunta:** Um interface endpoint existe, mas seu SG não aceita o tráfego do cliente. O DNS privado resolve o problema?

**Resposta:** Não.

**Saiba mais:** Resolver o endereço não concede transporte pela interface.

**Fonte:** [Configure an interface endpoint - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/interface-endpoints.html)


## SAA-09-006-C002

**Objetivo:** Endpoint privado não resolve: inspecionar DNS e conectividade

**Pergunta:** Clientes continuam usando endereço público de serviço apesar de endpoint privado. O que investigar?

**Resposta:** DNS privado, resolução do cliente e nome de serviço utilizado.

**Saiba mais:** O endpoint precisa ser efetivamente usado pelo fluxo.

**Fonte:** [Configure an interface endpoint - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/interface-endpoints.html)


## SAA-09-007-C001

**Objetivo:** VPC peering não comunica: avaliar rotas dos dois lados

**Pergunta:** Há rota de A para B no peering, mas falta rota de retorno. O que pode acontecer?

**Resposta:** Falha de comunicação bidirecional.

**Saiba mais:** Verificar as route tables de ambos os lados.

**Fonte:** [Update your route tables for a VPC peering connection - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/peering/vpc-peering-routing.html)


## SAA-09-007-C002

**Objetivo:** VPC peering não comunica: avaliar rotas dos dois lados

**Pergunta:** Uma conexão de peering ativa supera automaticamente SGs que bloqueiam a porta?

**Resposta:** Não.

**Saiba mais:** O peering fornece conectividade potencial; os controles continuam aplicáveis.

**Fonte:** [Update your route tables for a VPC peering connection - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/peering/vpc-peering-routing.html)


## SAA-09-008-C001

**Objetivo:** Falha de uma AZ: rastrear dependência de NAT zonal

**Pergunta:** Recursos em AZs saudáveis perderam saída quando a AZ do único NAT zonal falhou. Qual dependência foi revelada?

**Resposta:** Uma dependência de saída centralizada naquele NAT zonal.

**Saiba mais:** Espalhar instâncias não remove dependências compartilhadas.

**Fonte:** [NAT gateway basics - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-basics.html)


## SAA-09-008-C002

**Objetivo:** Falha de uma AZ: rastrear dependência de NAT zonal

**Pergunta:** Como avaliar uma correção para falha de saída zonal?

**Resposta:** Selecionar topologia de saída compatível com a disponibilidade requerida.

**Saiba mais:** Comparar redundância, modalidade do NAT e custo do caminho.

**Fonte:** [NAT gateway basics - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-basics.html)

