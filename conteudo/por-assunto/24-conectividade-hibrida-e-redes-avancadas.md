# 24 · Conectividade híbrida e redes avançadas

30 cartões · primeira edição · 05/10/2026.


## SAA-24-001-C001

**Objetivo:** Site-to-Site VPN e Direct Connect: escolher conectividade híbrida

**Pergunta:** Quando comparar Site-to-Site VPN com Direct Connect?

**Resposta:** Ao conectar redes locais à AWS com requisitos de segurança, previsibilidade e capacidade.

**Saiba mais:** Prazo de implantação e custo também influenciam a escolha.

**Fonte:** [Network-to-Amazon VPC connectivity options - Amazon Virtual Private Cloud Connectivity Options](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/network-to-amazon-vpc-connectivity-options.html)


## SAA-24-001-C002

**Objetivo:** Site-to-Site VPN e Direct Connect: escolher conectividade híbrida

**Pergunta:** Qual opção usa túneis IPsec para conectar a rede local à AWS?

**Resposta:** AWS Site-to-Site VPN.

**Saiba mais:** A disponibilidade depende também do equipamento e dos caminhos externos.

**Fonte:** [Network-to-Amazon VPC connectivity options - Amazon Virtual Private Cloud Connectivity Options](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/network-to-amazon-vpc-connectivity-options.html)


## SAA-24-002-C001

**Objetivo:** Direct Connect e criptografia: separar enlace privado de proteção criptográfica

**Pergunta:** Uma conexão Direct Connect cifra automaticamente todo o tráfego fim a fim?

**Resposta:** Não.

**Saiba mais:** Avaliar TLS, VPN sobre conectividade apropriada ou outros mecanismos suportados conforme o requisito.

**Fonte:** [Encryption in AWS Direct Connect - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/encryption-in-transit.html)


## SAA-24-002-C002

**Objetivo:** Direct Connect e criptografia: separar enlace privado de proteção criptográfica

**Pergunta:** Por que enlace privado e criptografia não são sinônimos?

**Resposta:** O isolamento do caminho não é a mesma proteção que cifrar o conteúdo.

**Saiba mais:** O enunciado pode exigir os dois controles.

**Fonte:** [Encryption in AWS Direct Connect - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/encryption-in-transit.html)


## SAA-24-003-C001

**Objetivo:** Redundância híbrida: avaliar enlaces, locais e túneis

**Pergunta:** Duas conexões que dependem do mesmo equipamento e local garantem resiliência completa?

**Resposta:** Não.

**Saiba mais:** Uma falha compartilhada pode atingir ambas.

**Fonte:** [AWS Direct Connect Resiliency Toolkit - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/resiliency_toolkit.html)


## SAA-24-003-C002

**Objetivo:** Redundância híbrida: avaliar enlaces, locais e túneis

**Pergunta:** O que avaliar para tornar conectividade híbrida resiliente?

**Resposta:** Diversidade de equipamentos, enlaces, locais e rotas conforme o objetivo.

**Saiba mais:** Redundância precisa separar domínios de falha.

**Fonte:** [AWS Direct Connect Resiliency Toolkit - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/resiliency_toolkit.html)


## SAA-24-004-C001

**Objetivo:** VIFs e Direct Connect Gateway: interpretar destinos

**Pergunta:** Para que serve uma virtual interface no Direct Connect?

**Resposta:** Estabelecer conectividade lógica com os destinos suportados pela modalidade.

**Saiba mais:** Private, public e transit VIF atendem usos diferentes.

**Fonte:** [Direct Connect virtual interfaces and hosted virtual interfaces - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/WorkingWithVirtualInterfaces.html)


## SAA-24-004-C002

**Objetivo:** VIFs e Direct Connect Gateway: interpretar destinos

**Pergunta:** Qual recurso ajuda a conectar Direct Connect a recursos compatíveis em múltiplas regiões?

**Resposta:** Direct Connect Gateway.

**Saiba mais:** As associações e restrições dependem da topologia escolhida.

**Fonte:** [Direct Connect gateways - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/direct-connect-gateways-intro.html)


## SAA-24-005-C001

**Objetivo:** Transit Gateway: selecionar topologia hub-and-spoke

**Pergunta:** Qual serviço centraliza conectividade entre múltiplas VPCs e redes locais em um hub?

**Resposta:** AWS Transit Gateway.

**Saiba mais:** Pode reduzir a complexidade de muitas conexões ponto a ponto.

**Fonte:** [What is AWS Transit Gateway for Amazon VPC? - Amazon VPC](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html)


## SAA-24-005-C002

**Objetivo:** Transit Gateway: selecionar topologia hub-and-spoke

**Pergunta:** Transit Gateway significa que todas as redes anexadas devem se comunicar livremente?

**Resposta:** Não.

**Saiba mais:** As route tables permitem controlar segmentação e alcance.

**Fonte:** [What is AWS Transit Gateway for Amazon VPC? - Amazon VPC](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html)


## SAA-24-006-C001

**Objetivo:** Route tables do TGW: associação, propagação e segmentação

**Pergunta:** Qual diferença entre associação e propagação em route tables do TGW?

**Resposta:** Associação seleciona a tabela usada pelo attachment; propagação insere rotas aprendidas nas tabelas permitidas.

**Saiba mais:** As duas decisões influenciam caminhos e isolamento.

**Fonte:** [Transit gateway route tables in AWS Transit Gateway - Amazon VPC](https://docs.aws.amazon.com/vpc/latest/tgw/tgw-route-tables.html)


## SAA-24-006-C002

**Objetivo:** Route tables do TGW: associação, propagação e segmentação

**Pergunta:** Uma rota presente em uma tabela TGW ajuda um attachment associado a outra tabela que não a contém?

**Resposta:** Não necessariamente.

**Saiba mais:** É preciso analisar a tabela efetivamente usada pelo fluxo.

**Fonte:** [Transit gateway route tables in AWS Transit Gateway - Amazon VPC](https://docs.aws.amazon.com/vpc/latest/tgw/tgw-route-tables.html)


## SAA-24-007-C001

**Objetivo:** VPC peering, Transit Gateway e PrivateLink: comparar objetivos

**Pergunta:** Qual diferença de objetivo existe entre PrivateLink e conectividade ampla por peering?

**Resposta:** PrivateLink expõe acesso a um serviço; peering conecta redes conforme rotas e regras.

**Saiba mais:** Escolher acesso limitado ao serviço quando não se deseja abrir toda a topologia.

**Fonte:** [VPC to VPC connectivity - Building a Scalable and Secure Multi-VPC AWS Network Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/vpc-to-vpc-connectivity.html)


## SAA-24-007-C002

**Objetivo:** VPC peering, Transit Gateway e PrivateLink: comparar objetivos

**Pergunta:** Qual opção tende a simplificar malha extensa de VPCs: múltiplos peerings ou TGW?

**Resposta:** Transit Gateway, quando seus requisitos e custos são adequados.

**Saiba mais:** Uma malha ponto a ponto cresce em quantidade de conexões a administrar.

**Fonte:** [VPC to VPC connectivity - Building a Scalable and Secure Multi-VPC AWS Network Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/vpc-to-vpc-connectivity.html)


## SAA-24-008-C001

**Objetivo:** PrivateLink: publicar serviço sem conectividade ampla entre redes

**Pergunta:** Como publicar um serviço privado para consumidores em outras VPCs sem expor toda a rede?

**Resposta:** Usar um endpoint service compatível com AWS PrivateLink.

**Saiba mais:** O consumidor acessa interfaces privadas e o serviço controla aceitação e permissões.

**Fonte:** [What is AWS PrivateLink? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html)


## SAA-24-008-C002

**Objetivo:** PrivateLink: publicar serviço sem conectividade ampla entre redes

**Pergunta:** PrivateLink exige necessariamente exposição do serviço à internet pública?

**Resposta:** Não.

**Saiba mais:** A finalidade é conectividade privada para serviços suportados.

**Fonte:** [What is AWS PrivateLink? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html)


## SAA-24-009-C001

**Objetivo:** Client VPN e Site-to-Site VPN: distinguir usuários e redes

**Pergunta:** Qual opção AWS atende usuários remotos individualmente, em vez de ligar duas redes inteiras?

**Resposta:** AWS Client VPN.

**Saiba mais:** Autenticação e autorização do usuário fazem parte do desenho.

**Fonte:** [What is AWS Client VPN? - AWS Client VPN](https://docs.aws.amazon.com/vpn/latest/clientvpn-admin/what-is.html)


## SAA-24-009-C002

**Objetivo:** Client VPN e Site-to-Site VPN: distinguir usuários e redes

**Pergunta:** Uma VPN Site-to-Site e uma Client VPN têm o mesmo modelo de consumidor?

**Resposta:** Não.

**Saiba mais:** Uma atende conexão entre redes; a outra, clientes remotos autorizados.

**Fonte:** [What is AWS Client VPN? - AWS Client VPN](https://docs.aws.amazon.com/vpn/latest/clientvpn-admin/what-is.html)


## SAA-24-010-C001

**Objetivo:** DNS híbrido com Route 53 Resolver: selecionar direção da consulta

**Pergunta:** Qual endpoint Resolver recebe consultas de uma rede externa para resolução na VPC?

**Resposta:** Inbound endpoint.

**Saiba mais:** Outbound endpoint atende encaminhamento de consultas da VPC para resolvedores externos.

**Fonte:** [What is Route 53 VPC Resolver? - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)


## SAA-24-010-C002

**Objetivo:** DNS híbrido com Route 53 Resolver: selecionar direção da consulta

**Pergunta:** Qual mecanismo encaminha nomes corporativos da VPC para o DNS local?

**Resposta:** Resolver outbound endpoint com regras apropriadas.

**Saiba mais:** É preciso estabelecer conectividade e permitir o tráfego DNS.

**Fonte:** [What is Route 53 VPC Resolver? - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)


## SAA-24-011-C001

**Objetivo:** Endereços sobrepostos: identificar limitação e opções arquiteturais

**Pergunta:** Duas VPCs com CIDRs sobrepostos podem usar peering direto normalmente?

**Resposta:** Não.

**Saiba mais:** A sobreposição é uma restrição importante de endereçamento.

**Fonte:** [How VPC peering connections work - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/peering/invalid-peering-configurations.html)


## SAA-24-011-C002

**Objetivo:** Endereços sobrepostos: identificar limitação e opções arquiteturais

**Pergunta:** Ao integrar redes sobrepostas, qual deve ser a análise arquitetural?

**Resposta:** Avaliar renumeração ou alternativas compatíveis com o acesso necessário, como exposição de serviço.

**Saiba mais:** Não assumir que trocar peering por outra conexão resolve todo conflito automaticamente.

**Fonte:** [How VPC peering connections work - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/peering/invalid-peering-configurations.html)


## SAA-24-012-C001

**Objetivo:** Inspeção centralizada: avaliar GWLB e Network Firewall

**Pergunta:** Qual balanceador pode distribuir tráfego por appliances de inspeção virtual?

**Resposta:** Gateway Load Balancer.

**Saiba mais:** As rotas devem direcionar tráfego aos componentes de inspeção adequados.

**Fonte:** [What is a Gateway Load Balancer? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/gateway/introduction.html)


## SAA-24-012-C002

**Objetivo:** Inspeção centralizada: avaliar GWLB e Network Firewall

**Pergunta:** Por que inspeção stateful pode exigir atenção ao caminho de ida e volta?

**Resposta:** O estado da conexão precisa ser visto de forma consistente pelo mecanismo de inspeção.

**Saiba mais:** Roteamento assimétrico pode prejudicar o funcionamento.

**Fonte:** [What is a Gateway Load Balancer? - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/gateway/introduction.html)


## SAA-24-013-C001

**Objetivo:** Egress centralizado: comparar custo, dependência e isolamento

**Pergunta:** Qual possível vantagem operacional existe em centralizar saída de várias VPCs?

**Resposta:** Concentrar controles e administração do caminho de egress.

**Saiba mais:** A economia depende do volume, dos componentes e da disponibilidade necessária.

**Fonte:** [Using the NAT gateway for centralized IPv4 egress - Building a Scalable and Secure Multi-VPC AWS Network Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/using-nat-gateway-for-centralized-egress.html)


## SAA-24-013-C002

**Objetivo:** Egress centralizado: comparar custo, dependência e isolamento

**Pergunta:** Qual custo pode surgir ao centralizar saída usando TGW?

**Resposta:** Processamento e transferência adicionais no caminho.

**Saiba mais:** Não comparar apenas a contagem de NATs.

**Fonte:** [Using the NAT gateway for centralized IPv4 egress - Building a Scalable and Secure Multi-VPC AWS Network Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/using-nat-gateway-for-centralized-egress.html)


## SAA-24-014-C001

**Objetivo:** MTU e largura de banda: reconhecer sinais de desempenho

**Pergunta:** O que representa MTU?

**Resposta:** O tamanho máximo de unidade de transmissão suportada no enlace ou caminho considerado.

**Saiba mais:** Diferenças no caminho podem exigir fragmentação ou descoberta de MTU.

**Fonte:** [Network maximum transmission unit (MTU) for your EC2 instance - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/network_mtu.html)


## SAA-24-014-C002

**Objetivo:** MTU e largura de banda: reconhecer sinais de desempenho

**Pergunta:** Ter uma instância com rede rápida garante a mesma largura de banda até qualquer destino?

**Resposta:** Não.

**Saiba mais:** O menor limite entre os componentes do caminho pode ser o gargalo.

**Fonte:** [Network maximum transmission unit (MTU) for your EC2 instance - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/network_mtu.html)


## SAA-24-015-C001

**Objetivo:** Conectividade híbrida em contingência: planejar rota alternativa

**Pergunta:** Como uma VPN pode participar de uma estratégia de contingência para Direct Connect?

**Resposta:** Como caminho alternativo, com roteamento e capacidade planejados.

**Saiba mais:** É preciso validar failover, throughput e requisitos de segurança.

**Fonte:** [Configure a Direct Connect Classic connection - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/toolkit-classic.html)


## SAA-24-015-C002

**Objetivo:** Conectividade híbrida em contingência: planejar rota alternativa

**Pergunta:** Por que testar a rota de backup antes de uma falha real?

**Resposta:** Para verificar que configuração e capacidade atendem aos objetivos de recuperação.

**Saiba mais:** A existência de uma conexão não prova que o tráfego será recuperado corretamente.

**Fonte:** [Configure a Direct Connect Classic connection - AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/toolkit-classic.html)

