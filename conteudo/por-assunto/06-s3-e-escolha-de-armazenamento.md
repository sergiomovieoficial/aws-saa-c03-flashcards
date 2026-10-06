# 06 · S3 e escolha de armazenamento

65 cartões · primeira edição · 05/10/2026.


## SAA-06-001-C001

**Objetivo:** Objeto, bloco e arquivo: escolher modelo de armazenamento

**Pergunta:** Uma aplicação exige um disco formatado e anexado a uma VM. Qual modelo de storage é esperado?

**Resposta:** Armazenamento em bloco.

**Saiba mais:** Um bucket de objetos não equivale diretamente a um disco do sistema operacional.

**Fonte:** [AWS Storage category iconStorage - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/storage-services.html)


## SAA-06-001-C002

**Objetivo:** Objeto, bloco e arquivo: escolher modelo de armazenamento

**Pergunta:** Várias instâncias Linux precisam montar o mesmo filesystem por NFS. Qual serviço avaliar?

**Resposta:** Amazon EFS.

**Saiba mais:** Selecionar armazenamento por protocolo e semântica, não só por capacidade.

**Fonte:** [AWS Storage category iconStorage - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/storage-services.html)


## SAA-06-001-C003

**Objetivo:** Objeto, bloco e arquivo: escolher modelo de armazenamento

**Pergunta:** Arquivos acessados por API HTTP sem necessidade de filesystem compartilhado combinam com qual modelo?

**Resposta:** Armazenamento de objetos.

**Saiba mais:** Amazon S3 é a opção central para esse padrão.

**Fonte:** [AWS Storage category iconStorage - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/storage-services.html)


## SAA-06-002-C001

**Objetivo:** S3 buckets, objetos e chaves: reconhecer organização dos dados

**Pergunta:** O que identifica um objeto dentro de um bucket S3?

**Resposta:** Sua chave, com a versão quando aplicável.

**Saiba mais:** Pastas exibidas no console normalmente representam prefixos das chaves.

**Fonte:** [Amazon S3 objects overview - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingObjects.html)


## SAA-06-002-C002

**Objetivo:** S3 buckets, objetos e chaves: reconhecer organização dos dados

**Pergunta:** Um prefixo S3 é necessariamente um diretório físico como em um filesystem?

**Resposta:** Não.

**Saiba mais:** A organização visual não transforma o modelo de objetos em um filesystem POSIX.

**Fonte:** [Amazon S3 objects overview - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingObjects.html)


## SAA-06-003-C001

**Objetivo:** Consistência de operações S3: interpretar leitura após gravação

**Pergunta:** Após um PUT bem-sucedido no S3, a leitura do objeto usa consistência forte?

**Resposta:** Sim, para as operações de leitura de objetos descritas pelo modelo atual.

**Saiba mais:** Não confundir consistência do armazenamento com caches de clientes ou CDN.

**Fonte:** [What is Amazon S3? - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html#ConsistencyModel)


## SAA-06-003-C002

**Objetivo:** Consistência de operações S3: interpretar leitura após gravação

**Pergunta:** Uma cópia antiga servida por CloudFront prova que o S3 tem consistência eventual para GET?

**Resposta:** Não.

**Saiba mais:** A versão pode estar em cache na camada de entrega.

**Fonte:** [What is Amazon S3? - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html#ConsistencyModel)


## SAA-06-004-C001

**Objetivo:** S3 versioning e delete markers: recuperar alterações e exclusões

**Pergunta:** Como versioning ajuda após sobrescrever um objeto?

**Resposta:** Mantendo versões que podem ser recuperadas conforme a configuração.

**Saiba mais:** É preciso gerenciar retenção e custo das versões anteriores.

**Fonte:** [Retaining multiple versions of objects with S3 Versioning - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html)


## SAA-06-004-C002

**Objetivo:** S3 versioning e delete markers: recuperar alterações e exclusões

**Pergunta:** O que uma exclusão simples normalmente cria em um bucket com versioning habilitado?

**Resposta:** Um delete marker como versão atual.

**Saiba mais:** As versões anteriores não são necessariamente removidas por essa operação.

**Fonte:** [Working with delete markers - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/DeleteMarker.html)


## SAA-06-004-C003

**Objetivo:** S3 versioning e delete markers: recuperar alterações e exclusões

**Pergunta:** Versioning impede que alguém autorizado exclua permanentemente uma versão específica?

**Resposta:** Não, por si só.

**Saiba mais:** Controles como Object Lock podem acrescentar proteção de retenção.

**Fonte:** [Working with delete markers - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/DeleteMarker.html)


## SAA-06-005-C001

**Objetivo:** S3 Standard, Standard-IA e One Zone-IA: comparar disponibilidade e acesso

**Pergunta:** Para dados frequentemente acessados e que exigem resiliência entre AZs, qual classe S3 geral avaliar?

**Resposta:** S3 Standard.

**Saiba mais:** A frequência de acesso e requisitos de disponibilidade orientam a escolha.

**Fonte:** [Understanding and managing Amazon S3 storage classes - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html)


## SAA-06-005-C002

**Objetivo:** S3 Standard, Standard-IA e One Zone-IA: comparar disponibilidade e acesso

**Pergunta:** Qual diferença de resiliência importa entre Standard-IA e One Zone-IA?

**Resposta:** One Zone-IA mantém dados em uma única AZ.

**Saiba mais:** Ela exige aceitar esse domínio de falha, como para dados reconstruíveis.

**Fonte:** [Understanding and managing Amazon S3 storage classes - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html)


## SAA-06-006-C001

**Objetivo:** S3 Intelligent-Tiering: avaliar padrão de acesso variável

**Pergunta:** Qual classe S3 é voltada a padrões de acesso desconhecidos ou variáveis, com movimentação automática entre tiers?

**Resposta:** S3 Intelligent-Tiering.

**Saiba mais:** Verificar custos de monitoramento e características dos tiers utilizados.

**Fonte:** [Managing storage costs with Amazon S3 Intelligent-Tiering - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/intelligent-tiering.html)


## SAA-06-006-C002

**Objetivo:** S3 Intelligent-Tiering: avaliar padrão de acesso variável

**Pergunta:** Intelligent-Tiering significa que todos os objetos irão imediatamente para armazenamento de arquivo?

**Resposta:** Não.

**Saiba mais:** Movimentações dependem dos padrões de acesso e das opções habilitadas.

**Fonte:** [Managing storage costs with Amazon S3 Intelligent-Tiering - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/intelligent-tiering.html)


## SAA-06-007-C001

**Objetivo:** S3 Glacier Instant, Flexible e Deep Archive: comparar recuperação e retenção

**Pergunta:** Qual classe Glacier oferece acesso em milissegundos a objetos raramente acessados?

**Resposta:** S3 Glacier Instant Retrieval.

**Saiba mais:** O nome Glacier não implica sempre restauração demorada.

**Fonte:** [Understanding S3 Glacier storage classes for long-term data storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/glacier-storage-classes.html)


## SAA-06-007-C002

**Objetivo:** S3 Glacier Instant, Flexible e Deep Archive: comparar recuperação e retenção

**Pergunta:** Objetos em Glacier Flexible Retrieval ou Deep Archive são lidos diretamente como objetos Standard sem restauração?

**Resposta:** Não.

**Saiba mais:** Planejar restauração e tempo de recuperação conforme a classe e a modalidade escolhida.

**Fonte:** [Understanding S3 Glacier storage classes for long-term data storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/glacier-storage-classes.html)


## SAA-06-007-C003

**Objetivo:** S3 Glacier Instant, Flexible e Deep Archive: comparar recuperação e retenção

**Pergunta:** Qual requisito pode impedir usar Deep Archive para um dado?

**Resposta:** Necessidade de acesso imediato.

**Saiba mais:** Menor custo de armazenamento não atende toda exigência de recuperação.

**Fonte:** [Understanding S3 Glacier storage classes for long-term data storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/glacier-storage-classes.html)


## SAA-06-008-C001

**Objetivo:** S3 Express One Zone: avaliar escopo, desempenho e adequação

**Pergunta:** Qual classe S3 é voltada a acesso de baixa latência em uma única AZ usando directory buckets?

**Resposta:** S3 Express One Zone.

**Saiba mais:** A escolha envolve um domínio de falha diferente de classes multizona.

**Fonte:** [High performance workloads - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/directory-bucket-high-performance.html)


## SAA-06-008-C002

**Objetivo:** S3 Express One Zone: avaliar escopo, desempenho e adequação

**Pergunta:** É adequado presumir que S3 Express One Zone oferece a mesma distribuição entre AZs de S3 Standard?

**Resposta:** Não.

**Saiba mais:** A decisão deve considerar explicitamente o requisito de resiliência.

**Fonte:** [High performance workloads - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/directory-bucket-high-performance.html)


## SAA-06-009-C001

**Objetivo:** S3 lifecycle: transições, expiração e versões anteriores

**Pergunta:** Qual recurso automatiza transições de classe e expiração de objetos S3?

**Resposta:** S3 Lifecycle.

**Saiba mais:** As regras precisam respeitar as condições e transições suportadas.

**Fonte:** [Managing the lifecycle of objects - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html)


## SAA-06-009-C002

**Objetivo:** S3 lifecycle: transições, expiração e versões anteriores

**Pergunta:** Uma regra de expiração da versão atual elimina necessariamente todas as versões antigas?

**Resposta:** Não.

**Saiba mais:** Versões não atuais têm ações de lifecycle próprias.

**Fonte:** [Managing the lifecycle of objects - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html)


## SAA-06-010-C001

**Objetivo:** Custos de S3: requisições, recuperação e duração mínima

**Pergunta:** Por que escolher classe S3 apenas pelo custo por GB armazenado pode ser errado?

**Resposta:** Existem custos e condições de requisição, recuperação, tamanho e retenção mínima.

**Saiba mais:** O padrão de uso determina o custo total.

**Fonte:** [S3 Pricing](https://aws.amazon.com/s3/pricing/)


## SAA-06-010-C002

**Objetivo:** Custos de S3: requisições, recuperação e duração mínima

**Pergunta:** Objetos pequenos e acessados frequentemente sempre ficam mais baratos em classes infrequentes?

**Resposta:** Não.

**Saiba mais:** Cobranças mínimas e de acesso podem superar a economia de armazenamento.

**Fonte:** [S3 Pricing](https://aws.amazon.com/s3/pricing/)


## SAA-06-011-C001

**Objetivo:** S3 multipart upload e transferência de objetos grandes

**Pergunta:** Como multipart upload ajuda a enviar um objeto grande?

**Resposta:** Divide o envio em partes que podem ser transferidas e repetidas independentemente.

**Saiba mais:** Falhar uma parte não exige necessariamente reenviar todo o objeto.

**Fonte:** [Uploading and copying objects using multipart upload in Amazon S3 - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/mpuoverview.html)


## SAA-06-011-C002

**Objetivo:** S3 multipart upload e transferência de objetos grandes

**Pergunta:** Por que encerrar ou abortar uploads multipart incompletos?

**Resposta:** Partes armazenadas podem continuar gerando custo.

**Saiba mais:** Lifecycle pode ajudar a remover uploads incompletos conforme a regra.

**Fonte:** [Uploading and copying objects using multipart upload in Amazon S3 - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/mpuoverview.html)


## SAA-06-012-C001

**Objetivo:** S3 Transfer Acceleration: avaliar distância e alternativa de upload

**Pergunta:** Qual recurso S3 pode acelerar transferências de longa distância usando a rede de borda AWS?

**Resposta:** S3 Transfer Acceleration.

**Saiba mais:** É necessário avaliar benefício para a origem e o padrão de transferência.

**Fonte:** [Configuring fast, secure file transfers using Amazon S3 Transfer Acceleration - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/transfer-acceleration.html)


## SAA-06-012-C002

**Objetivo:** S3 Transfer Acceleration: avaliar distância e alternativa de upload

**Pergunta:** Transfer Acceleration substitui autorização de acesso ao bucket?

**Resposta:** Não.

**Saiba mais:** Acelerar o caminho não concede permissão aos dados.

**Fonte:** [Configuring fast, secure file transfers using Amazon S3 Transfer Acceleration - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/transfer-acceleration.html)


## SAA-06-013-C001

**Objetivo:** S3 CRR e SRR: comparar replicação e requisitos

**Pergunta:** Qual diferença entre SRR e CRR no S3?

**Resposta:** SRR replica na mesma região; CRR replica entre regiões.

**Saiba mais:** Ambas dependem da configuração e do conjunto de objetos elegíveis.

**Fonte:** [Replicating objects within and across Regions - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html)


## SAA-06-013-C002

**Objetivo:** S3 CRR e SRR: comparar replicação e requisitos

**Pergunta:** Habilitar uma regra de replicação cobre automaticamente todo objeto antigo que já existia?

**Resposta:** Não necessariamente. Para objetos existentes, avaliar S3 Batch Replication.

**Saiba mais:** Distinguir replicação contínua de cópia retroativa.

**Fonte:** [Replicating objects within and across Regions - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html)


## SAA-06-013-C003

**Objetivo:** S3 CRR e SRR: comparar replicação e requisitos

**Pergunta:** Replicação substitui retenção e proteção contra exclusões indevidas em todos os cenários?

**Resposta:** Não.

**Saiba mais:** Uma estratégia de proteção precisa considerar alterações propagadas e política de retenção.

**Fonte:** [Replicating objects within and across Regions - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html)


## SAA-06-014-C001

**Objetivo:** S3 Object Lock: retenção, legal hold e proteção contra exclusão

**Pergunta:** Qual recurso S3 oferece retenção WORM para versões de objetos?

**Resposta:** S3 Object Lock.

**Saiba mais:** Protege contra substituição ou exclusão conforme o modo e a retenção.

**Fonte:** [Locking objects with Object Lock - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html)


## SAA-06-014-C002

**Objetivo:** S3 Object Lock: retenção, legal hold e proteção contra exclusão

**Pergunta:** Qual diferença essencial existe entre governance mode e compliance mode?

**Resposta:** Governance permite bypass por autorização específica; compliance impõe retenção que não pode ser encurtada pelos usuários, inclusive root.

**Saiba mais:** Escolher o modo conforme o requisito de proteção.

**Fonte:** [Locking objects with Object Lock - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html)


## SAA-06-014-C003

**Objetivo:** S3 Object Lock: retenção, legal hold e proteção contra exclusão

**Pergunta:** Legal hold exige necessariamente uma data final predefinida?

**Resposta:** Não.

**Saiba mais:** Ele permanece até ser removido por quem possui a permissão apropriada.

**Fonte:** [Locking objects with Object Lock - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html)


## SAA-06-015-C001

**Objetivo:** S3 Block Public Access, bucket policies e Object Ownership

**Pergunta:** Qual controle S3 ajuda a impedir configurações que tornem dados públicos?

**Resposta:** Block Public Access.

**Saiba mais:** Ele complementa as permissões e pode ser configurado em níveis relevantes.

**Fonte:** [Blocking public access to your Amazon S3 storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html)


## SAA-06-015-C002

**Objetivo:** S3 Block Public Access, bucket policies e Object Ownership

**Pergunta:** No modo Bucket owner enforced, como fica o uso de ACLs para autorização S3?

**Resposta:** ACLs ficam desabilitadas; o acesso é controlado por políticas.

**Saiba mais:** Esse modo simplifica a propriedade e o controle dos objetos pelo dono do bucket.

**Fonte:** [Controlling ownership of objects and disabling ACLs for your bucket - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html)


## SAA-06-016-C001

**Objetivo:** S3 Access Points: organizar políticas para múltiplos consumidores

**Pergunta:** Para que servem S3 Access Points?

**Resposta:** Oferecer pontos de acesso com políticas específicas para conjuntos de consumidores.

**Saiba mais:** Permitem organizar acesso sem depender apenas de uma política monolítica de bucket.

**Fonte:** [Managing access to shared datasets with access points - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-points.html)


## SAA-06-016-C002

**Objetivo:** S3 Access Points: organizar políticas para múltiplos consumidores

**Pergunta:** Criar um access point remove a necessidade de verificar a política do bucket?

**Resposta:** Não.

**Saiba mais:** Os controles aplicáveis precisam funcionar em conjunto.

**Fonte:** [Managing access to shared datasets with access points - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-points.html)


## SAA-06-017-C001

**Objetivo:** S3 presigned URLs: conceder acesso temporário a objetos

**Pergunta:** Como fornecer download temporário de um objeto privado sem tornar o bucket público?

**Resposta:** Gerar uma presigned URL com as condições apropriadas.

**Saiba mais:** A URL funciona como acesso portador durante sua validade efetiva.

**Fonte:** [Download and upload objects with presigned URLs - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)


## SAA-06-017-C002

**Objetivo:** S3 presigned URLs: conceder acesso temporário a objetos

**Pergunta:** Uma URL pré-assinada continua válida após expirarem as credenciais temporárias usadas para assiná-la?

**Resposta:** Não.

**Saiba mais:** A expiração das credenciais pode encerrar sua validade antes do prazo solicitado para a URL.

**Fonte:** [Download and upload objects with presigned URLs - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)


## SAA-06-018-C001

**Objetivo:** S3 SSE-S3, SSE-KMS e criptografia no cliente: escolher controle

**Pergunta:** Qual diferença de controle existe entre SSE-S3 e SSE-KMS?

**Resposta:** SSE-KMS integra gestão e autorização de chaves no KMS; SSE-S3 usa gestão de chaves pelo S3.

**Saiba mais:** A escolha depende do controle e da auditoria exigidos.

**Fonte:** [Protecting data with encryption - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingEncryption.html)


## SAA-06-018-C002

**Objetivo:** S3 SSE-S3, SSE-KMS e criptografia no cliente: escolher controle

**Pergunta:** Criptografia no cliente e server-side encryption ocorrem no mesmo ponto do fluxo?

**Resposta:** Não.

**Saiba mais:** Na criptografia do cliente, os dados são cifrados antes de serem enviados ao serviço.

**Fonte:** [Protecting data with encryption - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingEncryption.html)


## SAA-06-019-C001

**Objetivo:** S3 event notifications: desenhar processamento desacoplado

**Pergunta:** Como disparar processamento quando um objeto chega ao S3?

**Resposta:** Configurar notificações ou integração de eventos para destinos suportados.

**Saiba mais:** O consumidor deve tratar a semântica de entrega e possíveis repetições.

**Fonte:** [Amazon S3 Event Notifications - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/EventNotifications.html)


## SAA-06-019-C002

**Objetivo:** S3 event notifications: desenhar processamento desacoplado

**Pergunta:** Por que evitar gravar resultados no mesmo prefixo que dispara uma função sem filtragem?

**Resposta:** Pode criar um ciclo de novos eventos e execuções.

**Saiba mais:** Separar prefixos ou aplicar filtros evita realimentação acidental.

**Fonte:** [Amazon S3 Event Notifications - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/EventNotifications.html)


## SAA-06-020-C001

**Objetivo:** S3 website endpoint e bucket privado via CloudFront: distinguir origens

**Pergunta:** É possível usar OAC com o website endpoint de S3 como se fosse uma origem S3 regular?

**Resposta:** Não.

**Saiba mais:** Website endpoints são tratados como origens personalizadas e têm características diferentes.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)


## SAA-06-020-C002

**Objetivo:** S3 website endpoint e bucket privado via CloudFront: distinguir origens

**Pergunta:** Como manter o bucket privado ao distribuir conteúdo por CloudFront?

**Resposta:** Usar origem S3 compatível, OAC e política adequada no bucket.

**Saiba mais:** Não é necessário tornar o bucket público para atender usuários pela distribuição.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)


## SAA-06-021-C001

**Objetivo:** EBS gp3, io2 e volumes HDD: escolher por IOPS e throughput

**Pergunta:** Qual família EBS avaliar para operações aleatórias de baixa latência e requisitos de IOPS?

**Resposta:** Volumes SSD adequados, como gp3 ou io2 conforme a necessidade.

**Saiba mais:** Volumes HDD são orientados a outros padrões, especialmente acesso sequencial.

**Fonte:** [Amazon EBS volume types - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html)


## SAA-06-021-C002

**Objetivo:** EBS gp3, io2 e volumes HDD: escolher por IOPS e throughput

**Pergunta:** Qual vantagem de gp3 em dimensionamento?

**Resposta:** Permite configurar desempenho dentro dos limites suportados sem depender apenas do tamanho do volume.

**Saiba mais:** Comparar IOPS, throughput, capacidade e custo.

**Fonte:** [Amazon EBS volume types - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html)


## SAA-06-022-C001

**Objetivo:** EBS snapshots, criptografia e restauração: planejar proteção

**Pergunta:** Para que serve um snapshot EBS?

**Resposta:** Proteger o estado do volume para criar volumes e recuperar dados.

**Saiba mais:** Consistência da aplicação pode exigir coordenação de gravações.

**Fonte:** [Amazon EBS snapshots - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-snapshots.html)


## SAA-06-022-C002

**Objetivo:** EBS snapshots, criptografia e restauração: planejar proteção

**Pergunta:** Um snapshot EBS é um volume diretamente montável pela instância?

**Resposta:** Não.

**Saiba mais:** Normalmente cria-se um volume a partir dele para usar como dispositivo de bloco.

**Fonte:** [Amazon EBS snapshots - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-snapshots.html)


## SAA-06-023-C001

**Objetivo:** EBS Multi-Attach: avaliar requisitos e responsabilidade da aplicação

**Pergunta:** EBS Multi-Attach torna qualquer filesystem comum seguro para escrita simultânea por várias instâncias?

**Resposta:** Não.

**Saiba mais:** A aplicação e o filesystem precisam coordenar acesso concorrente adequadamente.

**Fonte:** [Attach an EBS volume to multiple EC2 instances using Multi-Attach - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volumes-multi.html)


## SAA-06-023-C002

**Objetivo:** EBS Multi-Attach: avaliar requisitos e responsabilidade da aplicação

**Pergunta:** Multi-Attach elimina as restrições de tipo de volume, instância e AZ?

**Resposta:** Não.

**Saiba mais:** É um recurso com requisitos específicos, não compartilhamento universal de disco.

**Fonte:** [Attach an EBS volume to multiple EC2 instances using Multi-Attach - Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volumes-multi.html)


## SAA-06-024-C001

**Objetivo:** EFS: compartilhamento NFS e acesso por múltiplas instâncias

**Pergunta:** Qual serviço oferece filesystem NFS elástico para workloads compatíveis?

**Resposta:** Amazon EFS.

**Saiba mais:** É útil para compartilhamento entre múltiplos clientes.

**Fonte:** [What is Amazon Elastic File System? - Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html)


## SAA-06-024-C002

**Objetivo:** EFS: compartilhamento NFS e acesso por múltiplas instâncias

**Pergunta:** Por que EFS pode atender uma aplicação Linux que precisa compartilhar arquivos entre instâncias?

**Resposta:** Os clientes montam um filesystem comum.

**Saiba mais:** Verificar rede, permissões e modelo de acesso.

**Fonte:** [What is Amazon Elastic File System? - Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html)


## SAA-06-025-C001

**Objetivo:** EFS classes e modos de throughput: selecionar configuração

**Pergunta:** Por que capacidade armazenada e throughput precisam ser avaliados separadamente no EFS?

**Resposta:** O workload pode exigir uma taxa de transferência incompatível com a configuração escolhida.

**Saiba mais:** Selecionar o modo de throughput adequado ao padrão de uso.

**Fonte:** [Amazon EFS performance specifications - Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/performance.html)


## SAA-06-025-C002

**Objetivo:** EFS classes e modos de throughput: selecionar configuração

**Pergunta:** Como lifecycle no EFS pode ajudar custos de arquivos pouco acessados?

**Resposta:** Movendo dados para classes apropriadas conforme políticas e elegibilidade.

**Saiba mais:** A frequência de acesso e custos de recuperação influenciam o benefício.

**Fonte:** [Managing storage lifecycle - Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/lifecycle-management-efs.html)


## SAA-06-026-C001

**Objetivo:** FSx for Windows File Server: compartilhamento SMB e diretório

**Pergunta:** Uma aplicação Windows exige SMB e integração com Active Directory. Qual filesystem gerenciado avaliar?

**Resposta:** FSx for Windows File Server.

**Saiba mais:** EFS usa NFS e não é a substituição direta desse requisito.

**Fonte:** [What is FSx for Windows File Server? - Amazon FSx for Windows File Server](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/what-is.html)


## SAA-06-026-C002

**Objetivo:** FSx for Windows File Server: compartilhamento SMB e diretório

**Pergunta:** Que requisito diferencia esse caso de simplesmente guardar arquivos no S3?

**Resposta:** A necessidade de protocolo e semântica de filesystem SMB.

**Saiba mais:** Uma API de objetos não atende automaticamente a mesma interface.

**Fonte:** [What is FSx for Windows File Server? - Amazon FSx for Windows File Server](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/what-is.html)


## SAA-06-027-C001

**Objetivo:** FSx for Lustre: arquivos para processamento de alto desempenho

**Pergunta:** Qual opção FSx é voltada a workloads de computação de alto desempenho com filesystem paralelo?

**Resposta:** FSx for Lustre.

**Saiba mais:** É comum em processamento intenso de arquivos e integração com datasets.

**Fonte:** [What is Amazon FSx for Lustre? - FSx for Lustre](https://docs.aws.amazon.com/fsx/latest/LustreGuide/what-is.html)


## SAA-06-027-C002

**Objetivo:** FSx for Lustre: arquivos para processamento de alto desempenho

**Pergunta:** Qual benefício a integração de Lustre com S3 pode trazer?

**Resposta:** Processar dados em filesystem de alto desempenho mantendo integração com armazenamento de objetos.

**Saiba mais:** O fluxo de importação e exportação precisa ser planejado.

**Fonte:** [What is Amazon FSx for Lustre? - FSx for Lustre](https://docs.aws.amazon.com/fsx/latest/LustreGuide/what-is.html)


## SAA-06-028-C001

**Objetivo:** FSx for NetApp ONTAP e OpenZFS: reconhecer requisitos de filesystem

**Pergunta:** Qual FSx avaliar quando a aplicação depende de recursos e protocolos de NetApp ONTAP?

**Resposta:** FSx for NetApp ONTAP.

**Saiba mais:** Selecionar por compatibilidade e recursos necessários, não apenas por ser armazenamento de arquivos.

**Fonte:** [What is Amazon FSx for NetApp ONTAP? - FSx for ONTAP](https://docs.aws.amazon.com/fsx/latest/ONTAPGuide/what-is-fsx-ontap.html)


## SAA-06-028-C002

**Objetivo:** FSx for NetApp ONTAP e OpenZFS: reconhecer requisitos de filesystem

**Pergunta:** Qual FSx fornece um serviço de arquivos gerenciado baseado em OpenZFS?

**Resposta:** FSx for OpenZFS.

**Saiba mais:** É uma alternativa específica para workloads compatíveis com suas características.

**Fonte:** [What is Amazon FSx for OpenZFS? - FSx for OpenZFS](https://docs.aws.amazon.com/fsx/latest/OpenZFSGuide/what-is-fsx.html)


## SAA-06-029-C001

**Objetivo:** S3, EBS, EFS e FSx: comparar cenários com requisitos explícitos

**Pergunta:** Um sistema usa acesso por objeto e distribuição HTTP global. Por que não começar com um disco EBS compartilhado?

**Resposta:** O modelo de objetos e entrega é melhor atendido por serviços próprios para essa interface.

**Saiba mais:** Escolher a abstração pelo acesso, não pela palavra arquivo.

**Fonte:** [AWS Storage category iconStorage - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/storage-services.html)


## SAA-06-029-C002

**Objetivo:** S3, EBS, EFS e FSx: comparar cenários com requisitos explícitos

**Pergunta:** Uma base de dados precisa de volume de bloco de baixa latência em EC2. Qual família de serviço comparar primeiro?

**Resposta:** EBS ou armazenamento local conforme persistência e desempenho exigidos.

**Saiba mais:** EFS e S3 possuem semânticas diferentes.

**Fonte:** [AWS Storage category iconStorage - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/storage-services.html)


## SAA-06-030-C001

**Objetivo:** Storage Gateway: relacionar integração híbrida ao tipo de dado

**Pergunta:** Qual família de serviço conecta armazenamento local a serviços de storage AWS usando interfaces compatíveis?

**Resposta:** AWS Storage Gateway.

**Saiba mais:** O tipo de gateway depende de arquivo, volume ou fita.

**Fonte:** [AWS Storage Gateway FAQs | Amazon Web Services](https://aws.amazon.com/storagegateway/faqs/)


## SAA-06-030-C002

**Objetivo:** Storage Gateway: relacionar integração híbrida ao tipo de dado

**Pergunta:** Por que escolher o tipo de gateway pelo protocolo da aplicação?

**Resposta:** A aplicação precisa continuar acessando os dados pela interface suportada.

**Saiba mais:** Migração de armazenamento não elimina requisitos de compatibilidade.

**Fonte:** [AWS Storage Gateway FAQs | Amazon Web Services](https://aws.amazon.com/storagegateway/faqs/)

