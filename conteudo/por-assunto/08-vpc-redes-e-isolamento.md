# 08 · VPC, redes e isolamento

41 cartões · primeira edição · 05/10/2026.


## SAA-08-001-C001

**Objetivo:** CIDR e sub-redes: dimensionar endereçamento sem sobreposição

**Pergunta:** Por que evitar CIDRs sobrepostos ao planejar VPCs que precisarão se comunicar?

**Resposta:** A sobreposição dificulta ou impede roteamento direto em mecanismos como peering.

**Saiba mais:** Planejar endereçamento antes da integração evita redesenho posterior.

**Fonte:** [VPC CIDR blocks - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-cidr-blocks.html)


## SAA-08-001-C002

**Objetivo:** CIDR e sub-redes: dimensionar endereçamento sem sobreposição

**Pergunta:** Por que considerar crescimento ao escolher o tamanho de uma subnet?

**Resposta:** Os recursos precisam de endereços disponíveis.

**Saiba mais:** Uma subnet sem IPs livres pode impedir novos lançamentos mesmo havendo quota de computação.

**Fonte:** [VPC CIDR blocks - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-cidr-blocks.html)


## SAA-08-002-C001

**Objetivo:** Subnets públicas e privadas: classificar pelo roteamento

**Pergunta:** O que caracteriza uma subnet pública no roteamento IPv4 tradicional?

**Resposta:** Uma rota para Internet Gateway.

**Saiba mais:** Uma instância ainda precisa de endereço e controles adequados para comunicação pública.

**Fonte:** [Subnets for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html)


## SAA-08-002-C002

**Objetivo:** Subnets públicas e privadas: classificar pelo roteamento

**Pergunta:** Uma subnet com saída por NAT Gateway é necessariamente pública?

**Resposta:** Não.

**Saiba mais:** Saída via NAT permite manter instâncias sem acesso direto por Internet Gateway.

**Fonte:** [Subnets for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html)


## SAA-08-003-C001

**Objetivo:** Route tables: interpretar prioridade e destino mais específico

**Pergunta:** Entre rotas que correspondem ao mesmo destino, qual princípio seleciona a mais específica?

**Resposta:** Longest prefix match.

**Saiba mais:** Outras regras de prioridade podem importar quando os prefixos são iguais.

**Fonte:** [How route priority works - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/route-tables-priority.html)


## SAA-08-003-C002

**Objetivo:** Route tables: interpretar prioridade e destino mais específico

**Pergunta:** Uma rota 10.0.0.0/16 é mais específica que 0.0.0.0/0?

**Resposta:** Sim.

**Saiba mais:** O prefixo maior cobre um conjunto menor de destinos.

**Fonte:** [How route priority works - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/route-tables-priority.html)


## SAA-08-004-C001

**Objetivo:** Internet Gateway: reconhecer condições para acesso à internet

**Pergunta:** Uma EC2 IPv4 em subnet pública acessa a internet só porque existe um Internet Gateway na VPC?

**Resposta:** Não.

**Saiba mais:** São necessários roteamento, endereço público apropriado e regras permitindo o tráfego.

**Fonte:** [Enable internet access for a VPC using an internet gateway - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)


## SAA-08-004-C002

**Objetivo:** Internet Gateway: reconhecer condições para acesso à internet

**Pergunta:** Internet Gateway funciona como uma política de segurança que libera todas as portas?

**Resposta:** Não.

**Saiba mais:** Security groups e NACLs continuam controlando tráfego.

**Fonte:** [Enable internet access for a VPC using an internet gateway - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)


## SAA-08-005-C001

**Objetivo:** NAT Gateway e NAT instance: avaliar saída IPv4

**Pergunta:** Qual é o papel de um NAT Gateway público em uma arquitetura IPv4 privada?

**Resposta:** Permitir conexões iniciadas por recursos privados para destinos externos pela internet.

**Saiba mais:** Isso não torna os recursos privados diretamente acessíveis por conexões externas iniciadas do lado de fora.

**Fonte:** [NAT gateways - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)


## SAA-08-005-C002

**Objetivo:** NAT Gateway e NAT instance: avaliar saída IPv4

**Pergunta:** Um NAT Gateway substitui um bastion para conexões SSH iniciadas da internet?

**Resposta:** Não.

**Saiba mais:** O fluxo de NAT de saída não é uma publicação genérica de portas de entrada.

**Fonte:** [NAT gateways - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)


## SAA-08-006-C001

**Objetivo:** NAT por AZ e saída centralizada: comparar falha e transferência

**Pergunta:** Qual risco existe quando subnets privadas de várias AZs dependem de um único NAT Gateway zonal?

**Resposta:** A falha da AZ do NAT pode interromper a saída dessas subnets.

**Saiba mais:** Este cartão trata da modalidade zonal; conferir modalidades atuais antes de generalizar.

**Fonte:** [NAT gateway basics - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-basics.html)


## SAA-08-006-C002

**Objetivo:** NAT por AZ e saída centralizada: comparar falha e transferência

**Pergunta:** Qual trade-off existe ao criar NAT zonal em cada AZ?

**Resposta:** Aumentar redundância e manter caminhos locais, com mais recursos cobrados.

**Saiba mais:** Comparar requisitos de disponibilidade e padrões de tráfego.

**Fonte:** [NAT gateway basics - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-basics.html)


## SAA-08-007-C001

**Objetivo:** IPv6 e egress-only Internet Gateway: distinguir fluxo de saída

**Pergunta:** Qual recurso permite saída IPv6 para a internet sem permitir conexões iniciadas externamente?

**Resposta:** Egress-only Internet Gateway.

**Saiba mais:** Seu papel não é o mesmo de um NAT IPv4.

**Fonte:** [Enable outbound IPv6 traffic using an egress-only internet gateway - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/egress-only-internet-gateway.html)


## SAA-08-007-C002

**Objetivo:** IPv6 e egress-only Internet Gateway: distinguir fluxo de saída

**Pergunta:** IPv6 elimina a necessidade de security groups?

**Resposta:** Não.

**Saiba mais:** Endereçamento e autorização de tráfego são preocupações distintas.

**Fonte:** [Enable outbound IPv6 traffic using an egress-only internet gateway - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/egress-only-internet-gateway.html)


## SAA-08-008-C001

**Objetivo:** Security groups e NACLs: comparar estado, regras e escopo

**Pergunta:** Security groups são stateful ou stateless?

**Resposta:** Stateful.

**Saiba mais:** Tráfego de resposta a conexões permitidas é tratado conforme o estado mantido.

**Fonte:** [Ensure internetwork traffic privacy in Amazon VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html)


## SAA-08-008-C002

**Objetivo:** Security groups e NACLs: comparar estado, regras e escopo

**Pergunta:** NACLs são stateful ou stateless?

**Resposta:** Stateless.

**Saiba mais:** É necessário permitir separadamente os fluxos de ida e retorno.

**Fonte:** [Ensure internetwork traffic privacy in Amazon VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html)


## SAA-08-008-C003

**Objetivo:** Security groups e NACLs: comparar estado, regras e escopo

**Pergunta:** Qual controle suporta regras explícitas de allow e deny ordenadas por número: SG ou NACL?

**Resposta:** NACL.

**Saiba mais:** Security groups usam regras de permissão, não uma lista ordenada de negações.

**Fonte:** [Ensure internetwork traffic privacy in Amazon VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html)


## SAA-08-009-C001

**Objetivo:** Portas efêmeras e tráfego de retorno: diagnosticar bloqueios

**Pergunta:** Uma NACL permite a porta do serviço na ida, mas bloqueia portas efêmeras no retorno. Qual sintoma pode ocorrer?

**Resposta:** Falha na conexão ou na resposta.

**Saiba mais:** Uma NACL não libera automaticamente o retorno por conhecer a conexão.

**Fonte:** [Custom network ACLs for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/custom-network-acl.html)


## SAA-08-009-C002

**Objetivo:** Portas efêmeras e tráfego de retorno: diagnosticar bloqueios

**Pergunta:** Por que as portas efêmeras relevantes variam conforme o cenário?

**Resposta:** Dependem do cliente e dos componentes no caminho.

**Saiba mais:** Não aplicar um intervalo decorado sem entender o fluxo.

**Fonte:** [Custom network ACLs for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/custom-network-acl.html)


## SAA-08-010-C001

**Objetivo:** Security group referencing: permitir comunicação entre camadas

**Pergunta:** Como permitir que apenas servidores de aplicação de um SG acessem um banco em um cenário suportado?

**Resposta:** Referenciar o SG da aplicação na regra de entrada do SG do banco.

**Saiba mais:** A referência precisa ser compatível com a topologia e o serviço.

**Fonte:** [Security group rules - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/security-group-rules.html)


## SAA-08-010-C002

**Objetivo:** Security group referencing: permitir comunicação entre camadas

**Pergunta:** Referenciar um SG concede permissão IAM para consultar o banco?

**Resposta:** Não.

**Saiba mais:** Permissão de rede e autorização da aplicação são camadas diferentes.

**Fonte:** [Security group rules - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/security-group-rules.html)


## SAA-08-011-C001

**Objetivo:** VPC endpoints gateway e interface: comparar conectividade

**Pergunta:** Quais serviços são atendidos por gateway endpoints tradicionais?

**Resposta:** Amazon S3 e DynamoDB.

**Saiba mais:** Eles são associados ao roteamento, diferentemente de interface endpoints.

**Fonte:** [AWS PrivateLink concepts - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints.html)


## SAA-08-011-C002

**Objetivo:** VPC endpoints gateway e interface: comparar conectividade

**Pergunta:** Como um interface endpoint fornece acesso privado a um serviço suportado?

**Resposta:** Por interfaces de rede privadas usando AWS PrivateLink.

**Saiba mais:** Há requisitos de DNS, permissões e segurança do endpoint.

**Fonte:** [AWS PrivateLink concepts - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints.html)


## SAA-08-012-C001

**Objetivo:** Endpoint policies, IAM e políticas de recurso: avaliar controles combinados

**Pergunta:** Uma endpoint policy permissiva concede automaticamente acesso a um bucket?

**Resposta:** Não.

**Saiba mais:** As políticas de identidade, recurso e demais controles ainda são avaliados.

**Fonte:** [Control access to VPC endpoints using endpoint policies - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html)


## SAA-08-012-C002

**Objetivo:** Endpoint policies, IAM e políticas de recurso: avaliar controles combinados

**Pergunta:** Para que restringir uma endpoint policy?

**Resposta:** Para limitar o que pode ser acessado por aquele endpoint.

**Saiba mais:** Ela complementa os outros controles, não os substitui.

**Fonte:** [Control access to VPC endpoints using endpoint policies - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html)


## SAA-08-013-C001

**Objetivo:** DNS da VPC: resolução e nomes privados

**Pergunta:** Por que DNS deve ser investigado quando um endpoint privado não é utilizado pela aplicação?

**Resposta:** O nome consultado pode não estar resolvendo para os endereços privados esperados.

**Saiba mais:** Ter o endpoint criado não garante que todos os clientes resolvam os nomes corretamente.

**Fonte:** [DNS attributes for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html)


## SAA-08-013-C002

**Objetivo:** DNS da VPC: resolução e nomes privados

**Pergunta:** Qual diferença investigar quando acesso por IP funciona, mas por nome falha?

**Resposta:** Configuração e resolução DNS.

**Saiba mais:** Isso ajuda a separar falha de resolução de falha de transporte.

**Fonte:** [DNS attributes for your VPC - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html)


## SAA-08-014-C001

**Objetivo:** VPC peering: rotas, CIDRs e ausência de trânsito implícito

**Pergunta:** VPC peering entre A-B e B-C cria automaticamente comunicação A-C?

**Resposta:** Não.

**Saiba mais:** VPC peering não oferece roteamento transitivo automático.

**Fonte:** [What is VPC peering? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html)


## SAA-08-014-C002

**Objetivo:** VPC peering: rotas, CIDRs e ausência de trânsito implícito

**Pergunta:** Criar a conexão de peering basta para o tráfego fluir?

**Resposta:** Não.

**Saiba mais:** Rotas e controles de rede dos participantes precisam permitir a comunicação.

**Fonte:** [What is VPC peering? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html)


## SAA-08-015-C001

**Objetivo:** VPC Flow Logs: interpretar evidências de comunicação

**Pergunta:** VPC Flow Logs capturam o conteúdo completo de cada pacote?

**Resposta:** Não.

**Saiba mais:** Eles registram informações sobre fluxos de tráfego, úteis para análise de comunicação.

**Fonte:** [Logging IP traffic using VPC Flow Logs - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html)


## SAA-08-015-C002

**Objetivo:** VPC Flow Logs: interpretar evidências de comunicação

**Pergunta:** Que tipo de evidência um registro REJECT em Flow Logs fornece?

**Resposta:** Que o fluxo observado foi rejeitado pelos controles reportados.

**Saiba mais:** É necessário analisar contexto e regras para encontrar a causa.

**Fonte:** [Logging IP traffic using VPC Flow Logs - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html)


## SAA-08-016-C001

**Objetivo:** Reachability Analyzer: investigar caminhos de rede

**Pergunta:** Qual ferramenta analisa a configuração do caminho entre recursos de rede suportados?

**Resposta:** VPC Reachability Analyzer.

**Saiba mais:** É análise de alcançabilidade, não um teste completo da lógica da aplicação.

**Fonte:** [What is Reachability Analyzer? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/reachability/what-is-reachability-analyzer.html)


## SAA-08-016-C002

**Objetivo:** Reachability Analyzer: investigar caminhos de rede

**Pergunta:** Um caminho considerado alcançável comprova que o processo HTTP está saudável?

**Resposta:** Não.

**Saiba mais:** A aplicação pode falhar mesmo com rede configurada corretamente.

**Fonte:** [What is Reachability Analyzer? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/reachability/what-is-reachability-analyzer.html)


## SAA-08-017-C001

**Objetivo:** Bastion e Session Manager: comparar administração privada

**Pergunta:** Qual é uma vantagem de Session Manager sobre um bastion exposto com SSH?

**Resposta:** Pode permitir administração sem abrir portas de entrada para a sessão.

**Saiba mais:** Requer conectividade de saída apropriada e autorização.

**Fonte:** [AWS Systems Manager Session Manager - AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)


## SAA-08-017-C002

**Objetivo:** Bastion e Session Manager: comparar administração privada

**Pergunta:** Usar um bastion dispensa limitar acesso administrativo?

**Resposta:** Não.

**Saiba mais:** O bastion também deve ter acesso restrito, atualização e auditoria.

**Fonte:** [AWS Systems Manager Session Manager - AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)


## SAA-08-018-C001

**Objetivo:** Arquitetura pública-privada em três camadas: posicionar componentes

**Pergunta:** Em uma arquitetura web em três camadas, onde normalmente posicionar um banco que só recebe acesso da aplicação?

**Resposta:** Em subnets privadas com acesso restrito da aplicação.

**Saiba mais:** A entrada pública pode ficar no balanceador.

**Fonte:** [Example: VPC with servers in private subnets and NAT - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-example-private-subnets-nat.html)


## SAA-08-018-C002

**Objetivo:** Arquitetura pública-privada em três camadas: posicionar componentes

**Pergunta:** Por que colocar aplicação e banco em subnets diferentes não basta para isolá-los?

**Resposta:** O isolamento depende de rotas e regras de acesso efetivas.

**Saiba mais:** Subnets organizam a rede, mas não definem sozinhas toda a política de segurança.

**Fonte:** [Example: VPC with servers in private subnets and NAT - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-example-private-subnets-nat.html)


## SAA-08-019-C001

**Objetivo:** Rede sem internet: mapear dependências em endpoints

**Pergunta:** Uma aplicação sem internet precisa usar APIs AWS. Qual opção avaliar?

**Resposta:** VPC endpoints para os serviços necessários e suportados.

**Saiba mais:** Mapear todas as dependências, inclusive logs, imagens e segredos.

**Fonte:** [Access AWS services through AWS PrivateLink - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/privatelink-access-aws-services.html)


## SAA-08-019-C002

**Objetivo:** Rede sem internet: mapear dependências em endpoints

**Pergunta:** Criar apenas um endpoint S3 garante que uma tarefa privada consiga obter imagem do ECR e enviar logs?

**Resposta:** Não.

**Saiba mais:** Cada dependência precisa do caminho apropriado e das permissões necessárias.

**Fonte:** [Access AWS services through AWS PrivateLink - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/privatelink-access-aws-services.html)


## SAA-08-020-C001

**Objetivo:** Transferência de dados entre AZs e regiões: identificar custos

**Pergunta:** Por que acesso frequente ao S3 por NAT merece revisão de custo?

**Resposta:** Pode envolver processamento e transferência por componentes evitáveis com uma arquitetura adequada.

**Saiba mais:** Avaliar gateway endpoint e as condições de cobrança aplicáveis.

**Fonte:** [Amazon VPC Pricing](https://aws.amazon.com/vpc/pricing/)


## SAA-08-020-C002

**Objetivo:** Transferência de dados entre AZs e regiões: identificar custos

**Pergunta:** Deve-se considerar apenas a quantidade de NAT Gateways ao comparar duas redes?

**Resposta:** Não.

**Saiba mais:** Volume processado, caminhos entre AZs e disponibilidade também importam.

**Fonte:** [Amazon VPC Pricing](https://aws.amazon.com/vpc/pricing/)

