# 07 · S3: laboratórios e diagnóstico

16 cartões · primeira edição · 05/10/2026.


## SAA-07-001-C001

**Objetivo:** Diagnosticar AccessDenied ao ler objeto criptografado

**Pergunta:** GetObject é permitido, mas um objeto SSE-KMS retorna AccessDenied. O que revisar além do bucket?

**Resposta:** Permissão de uso da chave, key policy e demais controles KMS.

**Saiba mais:** A autorização S3 não substitui autorização criptográfica.

**Fonte:** [Troubleshoot access denied (403 Forbidden) errors in Amazon S3 - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/troubleshoot-403-errors.html)


## SAA-07-001-C002

**Objetivo:** Diagnosticar AccessDenied ao ler objeto criptografado

**Pergunta:** Um Deny em bucket policy por condição de transporte pode bloquear um usuário com permissão IAM?

**Resposta:** Sim.

**Saiba mais:** Uma negação explícita aplicável prevalece.

**Fonte:** [Troubleshoot access denied (403 Forbidden) errors in Amazon S3 - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/troubleshoot-403-errors.html)


## SAA-07-002-C001

**Objetivo:** Recuperar arquivo sobrescrito usando versões

**Pergunta:** Após sobrescrever um objeto versionado, o que procurar para recuperar o conteúdo anterior?

**Resposta:** A versão anterior do objeto.

**Saiba mais:** O identificador de versão distingue os conteúdos da mesma chave.

**Fonte:** [Restoring previous versions - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/RestoringPreviousVersions.html)


## SAA-07-002-C002

**Objetivo:** Recuperar arquivo sobrescrito usando versões

**Pergunta:** O objeto parece excluído por delete marker. Todas as versões foram necessariamente perdidas?

**Resposta:** Não.

**Saiba mais:** Inspecionar versões antes de concluir que os dados foram removidos definitivamente.

**Fonte:** [Restoring previous versions - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/RestoringPreviousVersions.html)


## SAA-07-003-C001

**Objetivo:** Diagnosticar regra de lifecycle que não produz a transição esperada

**Pergunta:** Uma regra de lifecycle não afeta os objetos esperados. O que conferir primeiro?

**Resposta:** Filtros, prefixos, tags, idade e elegibilidade da ação.

**Saiba mais:** Uma regra existente pode não selecionar os objetos pretendidos.

**Fonte:** [Troubleshooting Amazon S3 Lifecycle issues - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/troubleshoot-lifecycle.html)


## SAA-07-003-C002

**Objetivo:** Diagnosticar regra de lifecycle que não produz a transição esperada

**Pergunta:** Habilitar lifecycle garante que a interface reflita toda transição instantaneamente?

**Resposta:** Não.

**Saiba mais:** As ações de lifecycle seguem processamento assíncrono e condições do serviço.

**Fonte:** [Troubleshooting Amazon S3 Lifecycle issues - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/troubleshoot-lifecycle.html)


## SAA-07-004-C001

**Objetivo:** Validar pré-requisitos e escopo de replicação

**Pergunta:** Que configuração básica dos buckets deve ser verificada para replicação S3 baseada em versões?

**Resposta:** Versioning nos buckets envolvidos, conforme os requisitos.

**Saiba mais:** Também verificar role, políticas e criptografia.

**Fonte:** [Requirements and considerations for replication - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication-requirements.html)


## SAA-07-004-C002

**Objetivo:** Validar pré-requisitos e escopo de replicação

**Pergunta:** Objetos antigos ficaram fora de uma regra recém-criada. Isso prova falha da replicação contínua?

**Resposta:** Não.

**Saiba mais:** Pode ser necessário Batch Replication para conteúdo preexistente.

**Fonte:** [Requirements and considerations for replication - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication-requirements.html)


## SAA-07-005-C001

**Objetivo:** Distinguir bloqueio de acesso público de ausência de permissão

**Pergunta:** Desativar Block Public Access concede automaticamente leitura a todos?

**Resposta:** Não.

**Saiba mais:** Ainda seria necessária uma concessão de acesso correspondente.

**Fonte:** [Blocking public access to your Amazon S3 storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html)


## SAA-07-005-C002

**Objetivo:** Distinguir bloqueio de acesso público de ausência de permissão

**Pergunta:** Uma bucket policy pública não funciona com bloqueios públicos aplicáveis habilitados. O que está ocorrendo?

**Resposta:** A proteção contra acesso público está restringindo a configuração ou o acesso.

**Saiba mais:** Corrigir a arquitetura pretendida sem remover controles indiscriminadamente.

**Fonte:** [Blocking public access to your Amazon S3 storage - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html)


## SAA-07-006-C001

**Objetivo:** Avaliar acesso por URL pré-assinada expirada

**Pergunta:** Uma URL assinada por sessão temporária expirou antes do prazo anunciado na URL. Qual causa investigar?

**Resposta:** Expiração ou revogação das credenciais da sessão.

**Saiba mais:** O prazo informado na URL não estende a vida das credenciais.

**Fonte:** [Download and upload objects with presigned URLs - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)


## SAA-07-006-C002

**Objetivo:** Avaliar acesso por URL pré-assinada expirada

**Pergunta:** Uma URL pré-assinada deve ser publicada livremente enquanto válida?

**Resposta:** Não.

**Saiba mais:** Quem a possui pode usá-la conforme as condições da assinatura.

**Fonte:** [Download and upload objects with presigned URLs - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)


## SAA-07-007-C001

**Objetivo:** Interpretar proteção por retenção e legal hold

**Pergunta:** Um administrador não consegue excluir uma versão sob compliance mode antes do prazo. Isso é necessariamente erro de permissão?

**Resposta:** Não. Pode ser o comportamento esperado da retenção.

**Saiba mais:** A proteção foi desenhada para resistir a exclusões antes do término.

**Fonte:** [Locking objects with Object Lock - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html)


## SAA-07-007-C002

**Objetivo:** Interpretar proteção por retenção e legal hold

**Pergunta:** Remover legal hold elimina automaticamente uma retenção temporal ainda ativa?

**Resposta:** Não.

**Saiba mais:** São mecanismos distintos e podem coexistir.

**Fonte:** [Locking objects with Object Lock - Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html)


## SAA-07-008-C001

**Objetivo:** Diagnosticar origem S3 privada em uma distribuição CloudFront

**Pergunta:** CloudFront recebe 403 de bucket privado após configurar OAC. Qual autorização revisar?

**Resposta:** A política do bucket para a distribuição e as permissões KMS, se aplicáveis.

**Saiba mais:** Criar o OAC não resolve sozinho todos os controles do recurso.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)


## SAA-07-008-C002

**Objetivo:** Diagnosticar origem S3 privada em uma distribuição CloudFront

**Pergunta:** Por que testar diretamente a URL pública do bucket não é suficiente para validar uma origem privada correta?

**Resposta:** O acesso direto pode ser intencionalmente negado.

**Saiba mais:** O fluxo permitido é o acesso pela distribuição autorizada.

**Fonte:** [Restrict access to an Amazon S3 origin - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)

