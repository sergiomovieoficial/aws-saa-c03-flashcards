# 19 · IA e ML: escolha de serviços gerenciados

20 cartões · primeira edição · 05/10/2026.


## SAA-19-001-C001

**Objetivo:** Rekognition: identificar cenário de imagem e vídeo

**Pergunta:** Qual serviço AWS oferece análise gerenciada de imagens e vídeos?

**Resposta:** Amazon Rekognition.

**Saiba mais:** Verificar as capacidades específicas necessárias ao caso.

**Fonte:** [What is Amazon Rekognition? - Amazon Rekognition](https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html)


## SAA-19-001-C002

**Objetivo:** Rekognition: identificar cenário de imagem e vídeo

**Pergunta:** Uma equipe que só precisa de uma capacidade visual pronta deve começar obrigatoriamente treinando modelo próprio?

**Resposta:** Não.

**Saiba mais:** Um serviço especializado pode reduzir esforço quando atende ao requisito.

**Fonte:** [What is Amazon Rekognition? - Amazon Rekognition](https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html)


## SAA-19-002-C001

**Objetivo:** Textract: identificar extração de texto e estrutura documental

**Pergunta:** Qual serviço extrai texto e estruturas como tabelas e campos de documentos?

**Resposta:** Amazon Textract.

**Saiba mais:** É mais específico para documentos que uma simples classificação de imagem.

**Fonte:** [What is Amazon Textract? - Amazon Textract](https://docs.aws.amazon.com/textract/latest/dg/what-is.html)


## SAA-19-002-C002

**Objetivo:** Textract: identificar extração de texto e estrutura documental

**Pergunta:** Digitalizar uma imagem de formulário é o mesmo que extrair campos estruturados?

**Resposta:** Não.

**Saiba mais:** A extração precisa reconhecer e organizar as informações úteis ao fluxo.

**Fonte:** [What is Amazon Textract? - Amazon Textract](https://docs.aws.amazon.com/textract/latest/dg/what-is.html)


## SAA-19-003-C001

**Objetivo:** Comprehend: identificar análise de linguagem

**Pergunta:** Qual serviço oferece análise de linguagem natural, como entidades e sentimento?

**Resposta:** Amazon Comprehend.

**Saiba mais:** É diferente de converter fala em texto.

**Fonte:** [What is Amazon Comprehend? - Amazon Comprehend](https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html)


## SAA-19-003-C002

**Objetivo:** Comprehend: identificar análise de linguagem

**Pergunta:** Um conjunto de avaliações textuais precisa de análise de sentimento. Qual serviço especializado avaliar?

**Resposta:** Amazon Comprehend.

**Saiba mais:** Confirmar suporte de idioma e capacidade desejada.

**Fonte:** [What is Amazon Comprehend? - Amazon Comprehend](https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html)


## SAA-19-004-C001

**Objetivo:** Transcribe e Polly: distinguir áudio para texto e texto para áudio

**Pergunta:** Qual serviço converte fala em texto?

**Resposta:** Amazon Transcribe.

**Saiba mais:** O resultado pode alimentar análises textuais posteriores.

**Fonte:** [What is Amazon Transcribe? - Amazon Transcribe](https://docs.aws.amazon.com/transcribe/latest/dg/what-is.html)


## SAA-19-004-C002

**Objetivo:** Transcribe e Polly: distinguir áudio para texto e texto para áudio

**Pergunta:** Qual serviço transforma texto em fala sintetizada?

**Resposta:** Amazon Polly.

**Saiba mais:** É o fluxo inverso ao reconhecimento de fala.

**Fonte:** [What Is Amazon Polly? - Amazon Polly](https://docs.aws.amazon.com/polly/latest/dg/what-is.html)


## SAA-19-005-C001

**Objetivo:** Translate: identificar tradução gerenciada

**Pergunta:** Qual serviço fornece tradução de texto gerenciada?

**Resposta:** Amazon Translate.

**Saiba mais:** Avaliar idiomas, formato e necessidade de terminologia específica.

**Fonte:** [What is Amazon Translate? - Amazon Translate](https://docs.aws.amazon.com/translate/latest/dg/what-is.html)


## SAA-19-005-C002

**Objetivo:** Translate: identificar tradução gerenciada

**Pergunta:** Traduzir texto é a mesma tarefa que determinar seu sentimento?

**Resposta:** Não.

**Saiba mais:** São objetivos diferentes e podem usar serviços distintos no pipeline.

**Fonte:** [What is Amazon Translate? - Amazon Translate](https://docs.aws.amazon.com/translate/latest/dg/what-is.html)


## SAA-19-006-C001

**Objetivo:** Lex: reconhecer interface conversacional

**Pergunta:** Qual serviço AWS é voltado à construção de interfaces conversacionais por voz e texto?

**Resposta:** Amazon Lex.

**Saiba mais:** A integração com lógica de negócio precisa ser definida.

**Fonte:** [What is Amazon Lex V2? - Amazon Lex](https://docs.aws.amazon.com/lexv2/latest/dg/what-is.html)


## SAA-19-006-C002

**Objetivo:** Lex: reconhecer interface conversacional

**Pergunta:** Uma interface conversacional substitui automaticamente autorização para executar ações de negócio?

**Resposta:** Não.

**Saiba mais:** A aplicação deve verificar identidade e permissões antes de realizar operações sensíveis.

**Fonte:** [What is Amazon Lex V2? - Amazon Lex](https://docs.aws.amazon.com/lexv2/latest/dg/what-is.html)


## SAA-19-007-C001

**Objetivo:** SageMaker AI: reconhecer criação e implantação de modelos

**Pergunta:** Qual plataforma AWS oferece recursos para desenvolver, treinar e implantar modelos de ML?

**Resposta:** Amazon SageMaker AI.

**Saiba mais:** Ela atende necessidades de modelos próprios e gestão do ciclo de ML.

**Fonte:** [What is Amazon SageMaker AI? - Amazon SageMaker AI](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)


## SAA-19-007-C002

**Objetivo:** SageMaker AI: reconhecer criação e implantação de modelos

**Pergunta:** Treinar um modelo e disponibilizar inferência são a mesma etapa?

**Resposta:** Não.

**Saiba mais:** São workloads com padrões de execução e recursos distintos.

**Fonte:** [What is Amazon SageMaker AI? - Amazon SageMaker AI](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)


## SAA-19-008-C001

**Objetivo:** Serviço pré-treinado versus modelo próprio: avaliar esforço e controle

**Pergunta:** Quando um modelo próprio pode ser necessário em vez de uma API especializada pronta?

**Resposta:** Quando a capacidade pronta não atende aos requisitos ou ao domínio dos dados.

**Saiba mais:** O controle adicional vem com trabalho de dados, avaliação e operação.

**Fonte:** [AWS Machine Learning category iconMachine Learning (ML) and Artificial Intelligence (AI) - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/machine-learning.html)


## SAA-19-008-C002

**Objetivo:** Serviço pré-treinado versus modelo próprio: avaliar esforço e controle

**Pergunta:** Menor esforço operacional favorece uma API pronta mesmo quando ela não cumpre a precisão exigida?

**Resposta:** Não.

**Saiba mais:** Primeiro é preciso atender ao requisito funcional e de qualidade.

**Fonte:** [AWS Machine Learning category iconMachine Learning (ML) and Artificial Intelligence (AI) - Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/machine-learning.html)


## SAA-19-009-C001

**Objetivo:** Pipeline de documentos: combinar storage, eventos e análise

**Pergunta:** Por que processamento assíncrono pode ser adequado para documentos extensos?

**Resposta:** Permite desacoplar recebimento e conclusão de uma análise demorada.

**Saiba mais:** A aplicação acompanha o resultado sem manter uma requisição aberta por todo o processo.

**Fonte:** [Processing Documents Asynchronously - Amazon Textract](https://docs.aws.amazon.com/textract/latest/dg/async.html)


## SAA-19-009-C002

**Objetivo:** Pipeline de documentos: combinar storage, eventos e análise

**Pergunta:** Como evitar que reprocessar o mesmo documento gere registros duplicados?

**Resposta:** Usar identificação estável e processamento idempotente.

**Saiba mais:** O pipeline pode repetir eventos após falhas.

**Fonte:** [Processing Documents Asynchronously - Amazon Textract](https://docs.aws.amazon.com/textract/latest/dg/async.html)


## SAA-19-010-C001

**Objetivo:** Escopo do exame versus material complementar de IA generativa

**Pergunta:** A ausência de um serviço na lista não exaustiva de escopo prova que ele jamais será mencionado?

**Resposta:** Não.

**Saiba mais:** O guia declara que a lista não é exaustiva e pode mudar.

**Fonte:** [In-Scope AWS Services - AWS Certified Solutions Architect - Associate](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03/saa-03-in-scope-services.html)


## SAA-19-010-C002

**Objetivo:** Escopo do exame versus material complementar de IA generativa

**Pergunta:** Por que manter aprofundamento de IA generativa separado da revisão central SAA-C03?

**Resposta:** Para priorizar os objetivos arquiteturais e o escopo documentado da certificação.

**Saiba mais:** Conhecimento complementar não precisa inflar a base principal de revisão.

**Fonte:** [In-Scope AWS Services - AWS Certified Solutions Architect - Associate](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03/saa-03-in-scope-services.html)

