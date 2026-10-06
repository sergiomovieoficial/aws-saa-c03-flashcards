# Seu primeiro estudo

## Importar no Anki

1. Tenha o Anki instalado. O ponto de entrada oficial é [apps.ankiweb.net](https://apps.ankiweb.net/).
2. Baixe [AWS-SAA-C03-Sergio-Movie.apkg](baralhos/AWS-SAA-C03-Sergio-Movie.apkg?raw=true). No GitHub, use o download do arquivo bruto se aparecer uma página sem prévia.
3. Abra o Anki, escolha **Arquivo → Importar** e selecione o pacote.
4. Expanda **AWS SAA-C03 · Sergio Movie** para escolher um dos 30 assuntos.
5. Use **Estudar agora**, tente responder e só então escolha **Mostrar resposta**.

No verso, **Saiba mais** abre a explicação. As referências técnicas são links clicáveis. Para só olhar o visual, use **Navegar**, selecione uma nota e abra **Pré-visualizar**.

Os [pacotes individuais](ASSUNTOS.md) contêm as mesmas notas do completo. Você pode começar por um assunto. Ajuste novos cartões e revisões ao tempo disponível.

## Experimentar no navegador

Baixe o repositório completo pelo menu **Code → Download ZIP**, extraia e abra `previa/index.html`. A prévia permite selecionar assunto, buscar na pergunta, virar o cartão, abrir Saiba mais e alternar o tema. Ela não registra progresso nem substitui o agendamento do Anki.

## Atualizar uma edição

Os pacotes completo e individuais compartilham IDs. A primeira edição teve reimportação testada sem duplicar notas. Faça backup das suas edições pessoais e confira as opções de atualização do Anki antes de reimportar: elas controlam como mudanças no conteúdo e no modelo são aplicadas. Consulte o [manual oficial de pacotes](https://docs.ankiweb.net/importing/packaged-decks.html).

## Criar seus próprios cartões

Na janela **Adicionar**, escolha o tipo de nota **Sergio Movie • AWS SAA-C03**, selecione o baralho e preencha:

| Campo | Conteúdo |
| --- | --- |
| Pergunta | Uma pergunta independente |
| Resposta | Uma resposta direta |
| Comentarios | Contexto exibido no Saiba mais |
| Logo | Imagem opcional inserida pelo editor |
| Materia | Nome da matéria |
| Assunto | Tema que não revele a resposta |
| Fonte | Referência técnica ou link |

Sem logo, o cartão mostra o monograma `sm.`. Para manter a aparência, evite colar textos com cores e tamanhos de fonte próprios. Editar o estilo de um tipo de nota afeta todas as notas que o utilizam.

## Consultar os cartões sem importar

Em `conteudo/por-assunto/`, você encontra os cartões em Markdown: perguntas, respostas, comentários e fontes, organizados por tema. Use o [índice de assuntos](ASSUNTOS.md) para escolher por onde começar.

Para sugerir uma correção, informe o ID do cartão seguindo o [guia de contribuição](CONTRIBUTING.md). Alterações nos textos serão revisadas antes de entrar nos pacotes de uma atualização.
