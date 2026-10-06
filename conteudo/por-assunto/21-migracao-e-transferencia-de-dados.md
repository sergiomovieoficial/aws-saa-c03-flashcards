# 21 · Migração e transferência de dados

26 cartões · primeira edição · 05/10/2026.


## SAA-21-001-C001

**Objetivo:** Estratégias de migração: selecionar abordagem pelo esforço permitido

**Pergunta:** Antes de migrar um sistema pouco usado, qual possibilidade pode evitar custo desnecessário?

**Resposta:** Verificar se ele pode ser retirado de uso.

**Saiba mais:** Migrar tudo indiscriminadamente preserva desperdícios existentes.

**Fonte:** [About the migration strategies - AWS Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/large-migration-guide/migration-strategies.html)


## SAA-21-001-C002

**Objetivo:** Estratégias de migração: selecionar abordagem pelo esforço permitido

**Pergunta:** Qual diferença entre rehost e refactor em uma migração?

**Resposta:** Rehost move com poucas mudanças; refactor altera a arquitetura de forma mais profunda.

**Saiba mais:** Prazo, risco e benefícios esperados orientam a escolha.

**Fonte:** [About the migration strategies - AWS Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/large-migration-guide/migration-strategies.html)


## SAA-21-002-C001

**Objetivo:** Application Migration Service: identificar migração de servidores

**Pergunta:** Qual serviço AWS ajuda a migrar servidores para AWS por replicação e lançamento de destino?

**Resposta:** AWS Application Migration Service.

**Saiba mais:** É distinto de uma ferramenta especializada em replicar tabelas de banco.

**Fonte:** [What Is AWS Transform MGN? - AWS Transform MGN](https://docs.aws.amazon.com/mgn/latest/ug/what-is-application-migration-service.html)


## SAA-21-002-C002

**Objetivo:** Application Migration Service: identificar migração de servidores

**Pergunta:** Uma migração de servidor concluída elimina a necessidade de validar a aplicação no destino?

**Resposta:** Não.

**Saiba mais:** Rede, credenciais, dependências e comportamento devem ser testados.

**Fonte:** [What Is AWS Transform MGN? - AWS Transform MGN](https://docs.aws.amazon.com/mgn/latest/ug/what-is-application-migration-service.html)


## SAA-21-003-C001

**Objetivo:** DMS full load e CDC: selecionar continuidade da replicação

**Pergunta:** Qual diferença entre full load e CDC no DMS?

**Resposta:** Full load transfere dados existentes; CDC replica alterações contínuas suportadas.

**Saiba mais:** Combinar os modos pode reduzir a janela de mudança final.

**Fonte:** [AWS DMS Terminology and concepts - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Introduction.html)


## SAA-21-003-C002

**Objetivo:** DMS full load e CDC: selecionar continuidade da replicação

**Pergunta:** CDC implica que nenhuma preparação da origem é necessária?

**Resposta:** Não.

**Saiba mais:** Logs, permissões e configuração devem atender aos requisitos da origem.

**Fonte:** [AWS DMS Terminology and concepts - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Introduction.html)


## SAA-21-004-C001

**Objetivo:** Migração homogênea e heterogênea: avaliar conversão de esquema

**Pergunta:** Por que uma migração entre engines diferentes pode exigir conversão de esquema?

**Resposta:** Tipos, objetos e recursos SQL podem não ser compatíveis diretamente.

**Saiba mais:** Replicar dados não converte automaticamente toda lógica da aplicação.

**Fonte:** [Converting database schemas using DMS Schema Conversion - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_SchemaConversion.html)


## SAA-21-004-C002

**Objetivo:** Migração homogênea e heterogênea: avaliar conversão de esquema

**Pergunta:** Uma migração homogênea é aquela entre engines diferentes?

**Resposta:** Não. Homogênea usa engines iguais ou compatíveis na definição do cenário.

**Saiba mais:** Heterogênea exige atenção adicional à conversão.

**Fonte:** [Converting database schemas using DMS Schema Conversion - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_SchemaConversion.html)


## SAA-21-005-C001

**Objetivo:** DataSync: transferência recorrente de arquivos e objetos

**Pergunta:** Qual serviço automatiza transferência de dados entre storages suportados, como arquivos locais e S3/EFS/FSx?

**Resposta:** AWS DataSync.

**Saiba mais:** Conferir locais, agentes e modos compatíveis.

**Fonte:** [What is AWS DataSync? - AWS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html)


## SAA-21-005-C002

**Objetivo:** DataSync: transferência recorrente de arquivos e objetos

**Pergunta:** DataSync substitui um filesystem que a aplicação monta continuamente em todo cenário?

**Resposta:** Não.

**Saiba mais:** Transferir dados e servir acesso diário ao storage são funções diferentes.

**Fonte:** [What is AWS DataSync? - AWS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html)


## SAA-21-006-C001

**Objetivo:** Transfer Family: acesso gerenciado por protocolos de transferência

**Pergunta:** Qual serviço oferece endpoints gerenciados para protocolos de transferência como SFTP?

**Resposta:** AWS Transfer Family.

**Saiba mais:** É apropriado quando clientes precisam continuar usando esses protocolos.

**Fonte:** [What is AWS Transfer Family? - AWS Transfer Family](https://docs.aws.amazon.com/transfer/latest/userguide/what-is-aws-transfer-family.html)


## SAA-21-006-C002

**Objetivo:** Transfer Family: acesso gerenciado por protocolos de transferência

**Pergunta:** Qual diferença entre Transfer Family e usar diretamente a API S3?

**Resposta:** Transfer Family oferece a interface de protocolo exigida pelo cliente.

**Saiba mais:** O armazenamento de destino pode continuar sendo um serviço AWS suportado.

**Fonte:** [What is AWS Transfer Family? - AWS Transfer Family](https://docs.aws.amazon.com/transfer/latest/userguide/what-is-aws-transfer-family.html)


## SAA-21-007-C001

**Objetivo:** Storage Gateway file, volume e tape: selecionar integração híbrida

**Pergunta:** Qual modalidade Storage Gateway expõe arquivos e os integra a objetos no S3?

**Resposta:** S3 File Gateway.

**Saiba mais:** É uma ponte de acesso por arquivos, com comportamento de cache e sincronização próprio.

**Fonte:** [What is Amazon S3 File Gateway - AWS Storage Gateway](https://docs.aws.amazon.com/filegateway/latest/files3/what-is-file-s3.html)


## SAA-21-007-C002

**Objetivo:** Storage Gateway file, volume e tape: selecionar integração híbrida

**Pergunta:** Qual modalidade ajuda a integrar software de backup que espera uma biblioteca de fitas?

**Resposta:** Tape Gateway.

**Saiba mais:** Apresenta uma interface de fita virtual com armazenamento AWS.

**Fonte:** [What is Tape Gateway? - AWS Storage Gateway](https://docs.aws.amazon.com/storagegateway/latest/tgw/WhatIsStorageGateway.html)


## SAA-21-008-C001

**Objetivo:** Snow Family: cenário offline e verificação de disponibilidade atual

**Pergunta:** Qual problema histórico Snowball Edge atende em transferência de dados?

**Resposta:** Movimentação física de grandes volumes quando transferência pela rede é inadequada.

**Saiba mais:** Reconhecer o cenário não significa presumir disponibilidade comercial para novos clientes.

**Fonte:** [What is Snowball Edge? - AWS Snowball Edge Developer Guide](https://docs.aws.amazon.com/snowball/latest/developer-guide/whatisedge.html)


## SAA-21-008-C002

**Objetivo:** Snow Family: cenário offline e verificação de disponibilidade atual

**Pergunta:** Por que um projeto atual não deve assumir que Snowball Edge pode ser contratado por qualquer novo cliente?

**Resposta:** O serviço possui restrições de disponibilidade para novos clientes documentadas pela AWS.

**Saiba mais:** Conferir elegibilidade antes de recomendar implantação.

**Fonte:** [AWS Snow device updates | AWS Storage Blog](https://aws.amazon.com/blogs/storage/aws-snow-device-updates/)


## SAA-21-009-C001

**Objetivo:** Transferência online versus offline: estimar tempo com premissas

**Pergunta:** Para estimar duração mínima teórica de transferência, qual relação usar?

**Resposta:** Volume de dados dividido pela taxa efetiva de transferência.

**Saiba mais:** Converter bits e bytes corretamente e considerar eficiência e restrições.

**Fonte:** [Network-to-Amazon VPC connectivity options - Amazon Virtual Private Cloud Connectivity Options](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/network-to-amazon-vpc-connectivity-options.html)


## SAA-21-009-C002

**Objetivo:** Transferência online versus offline: estimar tempo com premissas

**Pergunta:** Uma conexão de 1 Gbit/s transfere 1 GB por segundo?

**Resposta:** Não. Oito bits formam um byte.

**Saiba mais:** A taxa efetiva ainda será afetada por overhead e outros limites.

**Fonte:** [Network-to-Amazon VPC connectivity options - Amazon Virtual Private Cloud Connectivity Options](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/network-to-amazon-vpc-connectivity-options.html)


## SAA-21-010-C001

**Objetivo:** Conectividade de migração: VPN, Direct Connect e internet

**Pergunta:** Quais caminhos devem ser verificados para uma tarefa DMS conectar origem e destino?

**Resposta:** Rotas, firewalls/SGs, portas, DNS e credenciais de ambos.

**Saiba mais:** Conectividade de um lado não prova conectividade completa.

**Fonte:** [Security in AWS Database Migration Service - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Security.html)


## SAA-21-010-C002

**Objetivo:** Conectividade de migração: VPN, Direct Connect e internet

**Pergunta:** Uma migração por conexão privada dispensa criptografia quando ela é requisito explícito?

**Resposta:** Não.

**Saiba mais:** Privacidade do enlace e criptografia são controles separados.

**Fonte:** [Security in AWS Database Migration Service - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Security.html)


## SAA-21-011-C001

**Objetivo:** Cutover e rollback: planejar validação e retorno

**Pergunta:** O que um plano de cutover deve definir além de trocar o endpoint?

**Resposta:** Validação, sequência, responsáveis, critérios de sucesso e retorno.

**Saiba mais:** A mudança deve ser executável e verificável.

**Fonte:** [Pre-cutover stage - AWS Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-migration-cutover/pre-cutover-stage.html)


## SAA-21-011-C002

**Objetivo:** Cutover e rollback: planejar validação e retorno

**Pergunta:** Por que rollback precisa ser planejado antes de iniciar escrita no novo ambiente?

**Resposta:** Os dados podem divergir entre origem e destino.

**Saiba mais:** Voltar não é apenas restaurar uma string de conexão.

**Fonte:** [Pre-cutover stage - AWS Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-migration-cutover/pre-cutover-stage.html)


## SAA-21-012-C001

**Objetivo:** Segurança da transferência: credenciais, chaves e criptografia

**Pergunta:** Qual princípio aplicar às credenciais usadas em transferência de dados?

**Resposta:** Menor privilégio sobre origens e destinos necessários.

**Saiba mais:** Uma migração temporária não justifica acesso irrestrito permanente.

**Fonte:** [Security in AWS DataSync - AWS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/security.html)


## SAA-21-012-C002

**Objetivo:** Segurança da transferência: credenciais, chaves e criptografia

**Pergunta:** Por que remover acessos temporários após concluir uma migração?

**Resposta:** Para reduzir permissões que deixaram de ser necessárias.

**Saiba mais:** O encerramento do projeto inclui credenciais e recursos auxiliares.

**Fonte:** [Security in AWS DataSync - AWS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/security.html)


## SAA-21-013-C001

**Objetivo:** Migração inicial e sincronização contínua: separar etapas

**Pergunta:** Por que uma cópia inicial não basta se a aplicação continua alterando a origem?

**Resposta:** O destino ficará defasado pelas novas alterações.

**Saiba mais:** Uma etapa de sincronização ou parada coordenada precisa fechar a diferença.

**Fonte:** [Creating tasks for ongoing replication using AWS DMS - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Task.CDC.html)


## SAA-21-013-C002

**Objetivo:** Migração inicial e sincronização contínua: separar etapas

**Pergunta:** Antes de encerrar replicação contínua, o que validar?

**Resposta:** Atraso, integridade e prontidão do destino para assumir o workload.

**Saiba mais:** Replicação aparentemente ativa não comprova sincronização completa.

**Fonte:** [Creating tasks for ongoing replication using AWS DMS - AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Task.CDC.html)

