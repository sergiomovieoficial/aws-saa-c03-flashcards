# 13 · Route 53, CloudFront e entrega global

32 cartões · primeira edição · 05/10/2026.


## SAA-13-001-C001

**Objetivo:** DNS records, TTL, Alias e CNAME: escolher registro

**Pergunta:** Qual é a função do TTL em um registro DNS?

**Resposta:** Orientar por quanto tempo resolvedores podem manter a resposta em cache.

**Saiba mais:** Uma mudança de registro não atualiza instantaneamente todos os caches existentes.

**Fonte:** [Supported DNS record types - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html)


## SAA-13-001-C002

**Objetivo:** DNS records, TTL, Alias e CNAME: escolher registro

**Pergunta:** Qual recurso Route 53 permite apontar o domínio raiz para recursos AWS suportados?

**Resposta:** Alias record.

**Saiba mais:** CNAME não pode ocupar o apex da zona da mesma maneira.

**Fonte:** [Choosing between alias and non-alias records - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resource-record-sets-choosing-alias-non-alias.html)


## SAA-13-002-C001

**Objetivo:** Route 53 simple, weighted e multivalue: selecionar distribuição

**Pergunta:** Qual política Route 53 distribui respostas entre destinos conforme pesos configurados?

**Resposta:** Weighted routing.

**Saiba mais:** É útil em migrações graduais e testes de distribuição de tráfego.

**Fonte:** [Weighted routing - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-weighted.html)


## SAA-13-002-C002

**Objetivo:** Route 53 simple, weighted e multivalue: selecionar distribuição

**Pergunta:** Multivalue answer routing é um substituto completo de um load balancer?

**Resposta:** Não.

**Saiba mais:** Ele responde DNS com múltiplos valores; não gerencia cada conexão como um balanceador.

**Fonte:** [Multivalue answer routing - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-multivalue.html)


## SAA-13-003-C001

**Objetivo:** Route 53 latency e geolocation: distinguir critérios

**Pergunta:** Qual política Route 53 seleciona destino com base na latência estimada das regiões?

**Resposta:** Latency-based routing.

**Saiba mais:** Não é a mesma seleção que escolher por país do usuário.

**Fonte:** [Latency-based routing - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-latency.html)


## SAA-13-003-C002

**Objetivo:** Route 53 latency e geolocation: distinguir critérios

**Pergunta:** Qual política Route 53 atende necessidade de respostas diferentes por localização geográfica do solicitante?

**Resposta:** Geolocation routing.

**Saiba mais:** Pode ser útil para direcionamento por territórios conforme o desenho.

**Fonte:** [Geolocation routing - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geo.html)


## SAA-13-004-C001

**Objetivo:** Route 53 geoproximity e IP-based: reconhecer casos de uso

**Pergunta:** Qual política usa proximidade geográfica e permite ajustar a área atendida por bias?

**Resposta:** Geoproximity routing.

**Saiba mais:** O bias altera a influência relativa das localizações configuradas.

**Fonte:** [Geoproximity routing - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geoproximity.html)


## SAA-13-004-C002

**Objetivo:** Route 53 geoproximity e IP-based: reconhecer casos de uso

**Pergunta:** Qual política Route 53 permite decisões com base em faixas de IP conhecidas dos usuários?

**Resposta:** IP-based routing.

**Saiba mais:** É útil quando a organização possui informação específica sobre origem de rede.

**Fonte:** [IP-based routing - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-ipbased.html)


## SAA-13-005-C001

**Objetivo:** Route 53 failover e health checks: projetar continuidade

**Pergunta:** Qual política Route 53 é apropriada para destino primário e secundário de contingência?

**Resposta:** Failover routing.

**Saiba mais:** A saúde e as condições de avaliação precisam estar configuradas corretamente.

**Fonte:** [Creating Amazon Route 53 health checks - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html)


## SAA-13-005-C002

**Objetivo:** Route 53 failover e health checks: projetar continuidade

**Pergunta:** Failover DNS elimina a influência de caches dos clientes?

**Resposta:** Não.

**Saiba mais:** TTL, cache e comportamento do cliente afetam a transição efetiva.

**Fonte:** [Creating Amazon Route 53 health checks - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html)


## SAA-13-006-C001

**Objetivo:** Hosted zones públicas e privadas: escolher visibilidade

**Pergunta:** Para que serve uma private hosted zone?

**Resposta:** Resolver nomes de domínio no contexto das VPCs associadas e caminhos compatíveis.

**Saiba mais:** Ela não publica automaticamente os registros para toda a internet.

**Fonte:** [Working with private hosted zones - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-private.html)


## SAA-13-006-C002

**Objetivo:** Hosted zones públicas e privadas: escolher visibilidade

**Pergunta:** Um domínio público e um privado podem exigir análise de resolução diferente mesmo com o mesmo nome?

**Resposta:** Sim.

**Saiba mais:** O contexto do resolvedor determina qual zona é consultada.

**Fonte:** [Working with private hosted zones - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-private.html)


## SAA-13-007-C001

**Objetivo:** Route 53 Resolver: integrar resolução híbrida

**Pergunta:** Como permitir que a rede local consulte nomes privados resolvidos na VPC?

**Resposta:** Usar Resolver inbound endpoints e conectividade apropriada.

**Saiba mais:** Autorizar o tráfego DNS e configurar encaminhamento no resolvedor de origem.

**Fonte:** [What is Route 53 VPC Resolver? - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)


## SAA-13-007-C002

**Objetivo:** Route 53 Resolver: integrar resolução híbrida

**Pergunta:** Uma private hosted zone é automaticamente conhecida por todo DNS on-premises?

**Resposta:** Não.

**Saiba mais:** É necessário integrar a resolução.

**Fonte:** [What is Route 53 VPC Resolver? - Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)


## SAA-13-008-C001

**Objetivo:** CloudFront origins, behaviors e cache keys: definir cache

**Pergunta:** O que determina quais requisições podem compartilhar um objeto em cache no CloudFront?

**Resposta:** A cache key e as políticas relacionadas.

**Saiba mais:** Incluir parâmetros desnecessários fragmenta o cache.

**Fonte:** [Control the cache key with a policy - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/controlling-the-cache-key.html)


## SAA-13-008-C002

**Objetivo:** CloudFront origins, behaviors e cache keys: definir cache

**Pergunta:** Qual risco existe ao excluir da cache key um parâmetro que altera conteúdo por usuário?

**Resposta:** Servir conteúdo inadequado a outro usuário.

**Saiba mais:** O desenho deve respeitar personalização e privacidade.

**Fonte:** [Control the cache key with a policy - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/controlling-the-cache-key.html)


## SAA-13-009-C001

**Objetivo:** CloudFront TTL, invalidação e versionamento: atualizar conteúdo

**Pergunta:** Quais duas abordagens comuns permitem atualizar conteúdo distribuído em cache?

**Resposta:** Invalidar objetos ou usar nomes versionados.

**Saiba mais:** Versionamento de nome evita depender da substituição imediata de uma chave já armazenada.

**Fonte:** [Invalidate files to remove content - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html)


## SAA-13-009-C002

**Objetivo:** CloudFront TTL, invalidação e versionamento: atualizar conteúdo

**Pergunta:** Invalidar cache muda o arquivo da origem?

**Resposta:** Não.

**Saiba mais:** A invalidação força nova obtenção; o conteúdo correto precisa existir na origem.

**Fonte:** [Invalidate files to remove content - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html)


## SAA-13-010-C001

**Objetivo:** CloudFront OAC: proteger origem S3

**Pergunta:** Qual mecanismo atual controlar para autorizar CloudFront a acessar uma origem S3 privada?

**Resposta:** Origin Access Control, com política compatível no bucket.

**Saiba mais:** OAC trata o trecho distribuição-origem.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)


## SAA-13-010-C002

**Objetivo:** CloudFront OAC: proteger origem S3

**Pergunta:** OAC autentica automaticamente os usuários finais da aplicação?

**Resposta:** Não.

**Saiba mais:** Controle de acesso à origem e autorização do usuário final são diferentes.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)


## SAA-13-011-C001

**Objetivo:** Signed URLs e signed cookies: restringir conteúdo

**Pergunta:** Quando signed URL é uma opção adequada no CloudFront?

**Resposta:** Para conceder acesso controlado a um conteúdo ou URL específico.

**Saiba mais:** A política e a validade delimitam o uso.

**Fonte:** [Use signed URLs - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-signed-urls.html)


## SAA-13-011-C002

**Objetivo:** Signed URLs e signed cookies: restringir conteúdo

**Pergunta:** Quando signed cookies podem ser mais convenientes que assinar cada URL?

**Resposta:** Quando o usuário precisa acessar vários arquivos restritos.

**Saiba mais:** O mecanismo pode autorizar um conjunto de recursos sem modificar cada link.

**Fonte:** [Use signed cookies - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-signed-cookies.html)


## SAA-13-012-C001

**Objetivo:** HTTPS e certificados em CloudFront: verificar requisitos

**Pergunta:** Em qual região um certificado ACM usado entre viewers e CloudFront deve ser solicitado ou importado?

**Resposta:** US East (N. Virginia), us-east-1.

**Saiba mais:** Essa exigência refere-se ao certificado para o lado do viewer.

**Fonte:** [Requirements for using SSL/TLS certificates with CloudFront - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cnames-and-https-requirements.html)


## SAA-13-012-C002

**Objetivo:** HTTPS e certificados em CloudFront: verificar requisitos

**Pergunta:** O certificado usado na origem deve ser considerado igual ao certificado apresentado ao viewer?

**Resposta:** Não necessariamente.

**Saiba mais:** São conexões TLS distintas com requisitos próprios.

**Fonte:** [Requirements for using SSL/TLS certificates with CloudFront - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cnames-and-https-requirements.html)


## SAA-13-013-C001

**Objetivo:** CloudFront origin groups: avaliar failover de origem

**Pergunta:** Para que servem origin groups no CloudFront?

**Resposta:** Permitir failover entre origem primária e secundária nas condições suportadas.

**Saiba mais:** Métodos de requisição e códigos de falha precisam ser considerados.

**Fonte:** [Optimize high availability with CloudFront origin failover - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/high_availability_origin_failover.html)


## SAA-13-013-C002

**Objetivo:** CloudFront origin groups: avaliar failover de origem

**Pergunta:** CloudFront origin failover replica automaticamente os dados entre as origens?

**Resposta:** Não.

**Saiba mais:** A consistência e disponibilidade do conteúdo secundário devem ser preparadas separadamente.

**Fonte:** [Optimize high availability with CloudFront origin failover - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/high_availability_origin_failover.html)


## SAA-13-014-C001

**Objetivo:** CloudFront e Global Accelerator: escolher conforme aplicação

**Pergunta:** Qual diferença central entre CloudFront e Global Accelerator?

**Resposta:** CloudFront é uma CDN com cache; Global Accelerator otimiza encaminhamento global para endpoints de aplicações.

**Saiba mais:** Escolher por protocolo, cache e requisitos de endereço.

**Fonte:** [What is AWS Global Accelerator? - AWS Global Accelerator](https://docs.aws.amazon.com/global-accelerator/latest/dg/what-is-global-accelerator.html)


## SAA-13-014-C002

**Objetivo:** CloudFront e Global Accelerator: escolher conforme aplicação

**Pergunta:** Uma aplicação TCP global precisa de IPs estáticos e não de cache HTTP. Qual serviço avaliar?

**Resposta:** AWS Global Accelerator.

**Saiba mais:** Validar os tipos de endpoint e o protocolo da aplicação.

**Fonte:** [What is AWS Global Accelerator? - AWS Global Accelerator](https://docs.aws.amazon.com/global-accelerator/latest/dg/what-is-global-accelerator.html)


## SAA-13-015-C001

**Objetivo:** Global Accelerator: endereços estáticos e tráfego global

**Pergunta:** Qual benefício de IPs estáticos do Global Accelerator para parceiros que usam allowlists?

**Resposta:** Oferecer endereços estáveis de entrada para a aplicação.

**Saiba mais:** Isso desacopla a allowlist de mudanças dos endpoints suportados.

**Fonte:** [Adding an accelerator when you create a load balancer - AWS Global Accelerator](https://docs.aws.amazon.com/global-accelerator/latest/dg/about-accelerators.alb-accelerator.html)


## SAA-13-015-C002

**Objetivo:** Global Accelerator: endereços estáticos e tráfego global

**Pergunta:** Alterar um endpoint de um accelerator exige necessariamente alterar seus IPs estáticos de entrada?

**Resposta:** Não.

**Saiba mais:** Os IPs de entrada e o conjunto de endpoints têm papéis separados.

**Fonte:** [Adding an accelerator when you create a load balancer - AWS Global Accelerator](https://docs.aws.amazon.com/global-accelerator/latest/dg/about-accelerators.alb-accelerator.html)


## SAA-13-016-C001

**Objetivo:** WAF na borda: aplicar proteção a aplicações

**Pergunta:** Qual proteção pode ser associada ao CloudFront para filtrar requisições web?

**Resposta:** Uma web ACL do AWS WAF.

**Saiba mais:** As regras precisam corresponder ao comportamento que se pretende bloquear.

**Fonte:** [Using AWS WAF with Amazon CloudFront - AWS WAF, AWS Firewall Manager, AWS Shield Advanced, and AWS Shield network security director](https://docs.aws.amazon.com/waf/latest/developerguide/cloudfront-features.html)


## SAA-13-016-C002

**Objetivo:** WAF na borda: aplicar proteção a aplicações

**Pergunta:** Um cache hit no CloudFront torna irrelevante a proteção contra requisições maliciosas?

**Resposta:** Não.

**Saiba mais:** A distribuição continua sendo um ponto de entrada da aplicação.

**Fonte:** [Using AWS WAF with Amazon CloudFront - AWS WAF, AWS Firewall Manager, AWS Shield Advanced, and AWS Shield network security director](https://docs.aws.amazon.com/waf/latest/developerguide/cloudfront-features.html)

