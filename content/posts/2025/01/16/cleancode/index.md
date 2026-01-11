---
title: Clean Code Review
date: "2025-01-16T14:00:00-03:00"
slug: cleancode
tags:
  - clean code
  - book
  - review
  - clean code review
  - computer cience
  - ciencia da computcao
draft: false
---

Se você já pesquisou indicações de livros sobre programação, há uma grande chance de Clean Code, do Robert C. Martin (Uncle Bob), ter aparecido na lista.
É quase um rito de passagem: alguém vai te dizer “leia Clean Code".

## O que eu gostei no livro

Mais do que um manual de boas práticas de programação, eu enxergo o *Clean Code* como um verdadeiro ponto de virada na história do desenvolvimento. Ele conseguiu dar nome a um conceito que já existia, mas que ainda não tinha ganhado força suficiente: **a busca por código de qualidade**. Antes dele, falávamos sobre código “bom” ou “ruim” de forma solta e desorganizada. Depois dele, o debate ganhou um termo claro, uma bandeira, quase um movimento dentro da comunidade dev.

Uma das frases mais marcantes do livro traduz bem essa essência:

> **“A única maneira de ser rápido é fazer as coisas direito.” — Uncle Bob**

O impacto que essa obra causou no universo da programação é difícil de mensurar. De repente, temas como **clareza, leitura fácil e manutenção sem sofrimento** deixaram de ser vistos como “frescura” e passaram a ser tratados como prioridade. Na minha opinião, isso ajudou a elevar o nível das discussões técnicas e tornou nossa área mais madura, colaborativa e menos caótica.

Mesmo com a maioria dos exemplos sendo em Java, o livro não se limita a uma linguagem específica. Pelo contrário, os aprendizados são amplos e **se aplicam a praticamente qualquer stack**. Para quem está iniciando na carreira, o valor é ainda maior, porque o livro apresenta fundamentos que muitos desenvolvedores experientes já usam sem perceber. Como, por exemplo: **nomear variáveis, classes e funções de um jeito que revele intenção e facilite a busca no código**. Ele também reforça princípios clássicos, como o **DRY (evitar repetição)**, a separação entre comandos e consultas, além de metáforas poderosas que ficam na cabeça, como a **regra do escoteiro**, que nos lembra de sempre deixar o código melhor do que encontramos.

O livro também reúne uma série de práticas que parecem simples, mas que mudam tudo quando viram hábito:

- Usar nomes baseados no **domínio do problema**, e não termos genéricos, algo que se conecta diretamente com DDD.
- Lidar com erros usando exceções que **não atrapalham o fluxo o tempo todo**, mas que trazem o máximo de contexto quando algo falha.
- Criar testes unitários que sejam **rápidos, independentes, repetíveis, auto-validáveis e escritos no momento certo**, verificando apenas um comportamento por vez.
- Estruturar classes para que tenham **uma responsabilidade clara e única**.
- Garantir que cada função **faça só uma coisa**, mantendo a mesma camada de abstração do começo ao fim.
- Priorizar funções **puras**, sem efeitos colaterais inesperados.
- Separar métodos entre ações (que alteram estado) e perguntas (que retornam dados), seguindo **Command-Query Separation**.
- Evitar comentários desnecessários e **remover código obsoleto sem medo**, já que o versionamento guarda a história.
- Esconder dependências externas atrás de interfaces para manter o código **testável e desacoplado**.
- Usar encapsulamento e abstração de dados para criar APIs **mais seguras, compreensíveis e resistentes a erros**.

O mais curioso é que percebo esses ensinamentos voltando constantemente no meu dia a dia. Em revisões de PR, sessões de *pair programming* e conversas com o time, eu me pego repetindo esses mesmos conselhos, o que prova que o livro não ensina apenas a escrever código melhor, mas também a **identificar e consertar o que já existe**.

Outro ponto alto é o enorme catálogo de **code smells**. Ele treina nosso olhar para detectar padrões problemáticos no código e mostra caminhos práticos para combatê-los. Porque no fim, **código limpo não é só o que a gente escreve, é aquilo que a gente aprende a reconhecer e melhorar sempre que encontra**.

## O que eu não gostei no livro

<b> É muito opinativo </b>

O livro traz diretrizes como se fossem verdades absolutas.
Só que engenharia é contexto. Às vezes uma regra boa em Java 2008 não se aplica tão bem em projetos modernos, sistemas distribuídos, ou até times pequenos onde pragmatismo vence formalismo.

<b> Algumas recomendações envelheceram </b>

- Aversão a classes maiores pode não funcionar bem com design orientado a dados
- Nem todo código precisa ser hiper-abstrato pra ser limpo
- Às vezes menos padrões, mais clareza

<b> O lado perigoso </b>

A forma como o livro apresenta seus princípios pode ser vista como **rígida e inflexível**, o que acaba sendo uma faca de dois gumes. Ao mesmo tempo em que traz conselhos valiosos, ele **nem sempre explica o contexto ou os impactos negativos** de seguir essas ideias ao pé da letra. Isso pode confundir, principalmente quem está começando na carreira e ainda não desenvolveu um senso crítico mais apurado.

Levar regras como **“funções minúsculas”** ou **“não repita código (DRY)”** como verdades absolutas pode, na prática, piorar um projeto. Por exemplo: aplicar o DRY cegamente pode criar **abstrações demais**, gerando uma enxurrada de classes pequenas, mas **cheias de complexidade desnecessária**. O resultado é um código fragmentado, difícil de entender, e que dá mais trabalho para manter do que se algumas repetições tivessem sido toleradas.

Um bom desenvolvedor precisa entender que, às vezes, **duplicar um trecho é a escolha mais sensata** — seja para deixar a leitura mais clara, evitar indireções confusas ou até melhorar a performance. Em software, **nem toda repetição é um problema**, assim como **nem toda abstração é uma solução**.

Outro ponto crucial: práticas táticas de escrita de código **não podem vir acima de fundamentos maiores de design**, como:

- Acoplamento baixo
- Coesão alta
- Encapsulamento e ocultação de detalhes
- Separação clara de responsabilidades

Priorizar regras pontuais sem enxergar o impacto na estrutura do sistema pode levar a decisões que parecem “limpas” na teoria, mas **causam mais dano do que benefício no longo prazo**. No fim, código sustentável nasce do equilíbrio: seguir boas práticas, sim, **mas sempre considerando o cenário real, os custos e os trade-offs**.


## Conclusão

*Clean Code* é uma obra de grande influência e continua sendo uma leitura relevante.  
Seus princípios são valiosos, mas não devem ser tratados como regras universais e imutáveis.

O maior aprendizado que levo do livro não é seguir cada recomendação à risca, e sim desenvolver um olhar mais crítico sobre **qualidade, clareza e responsabilidade no código**.  
Código limpo, no fim, é aquele que equilibra boas práticas com contexto, evitando complexidade desnecessária e favorecendo a colaboração.

Vale a leitura. Melhor ainda é a aplicação consciente.