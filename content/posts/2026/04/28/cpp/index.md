---
title: C++ Review
date: "2026-04-28T14:00:00-03:00"
slug: cpp
tags:
  - cpp
  - c++
  - linguagem de programação
  - review
  - computer cience
  - ciencia da computcao
draft: false
---

Se você já se aventurou pelo mundo da programação, em algum momento o nome **C++** vai cruzar o seu caminho. Seja em listas de linguagens "que todo dev deveria conhecer", em vagas para áreas de alta performance, ou em discussões sobre os fundamentos da computação, C++ está sempre lá. É quase um rito de passagem: alguém vai te dizer "aprende C++ pra entender de verdade como as coisas funcionam".

## O que eu gostei na linguagem

Mais do que apenas uma linguagem de programação, eu enxergo o **C++** como uma das fundações do desenvolvimento moderno. Boa parte das ferramentas que usamos no dia a dia — sistemas operacionais, navegadores, engines de jogos, bancos de dados, compiladores — foram escritas em C++. Estudar a linguagem é como olhar por baixo do capô e entender de onde vêm muitas das abstrações que usamos hoje em linguagens mais "amigáveis".

Uma frase atribuída ao criador da linguagem traduz bem essa essência:

> **"C++ é projetado para permitir que você escreva programas eficientes e elegantes." — Bjarne Stroustrup**

O impacto que a linguagem causou no universo da programação é difícil de mensurar. De repente, conceitos como **gerenciamento manual de memória, ponteiros, RAII e templates** deixaram de ser detalhes obscuros e passaram a ser tratados como ferramentas poderosas para construir software de alta qualidade. Na minha opinião, isso ajuda a elevar o nível técnico de qualquer desenvolvedor que se dispõe a estudar a fundo.

Mesmo sendo uma linguagem com fama de "complicada", C++ não é apenas sobre sintaxe difícil. Pelo contrário, os aprendizados são amplos e **se aplicam a praticamente qualquer stack moderna**. Para quem está iniciando na carreira, o valor é ainda maior, porque a linguagem apresenta fundamentos que muitos desenvolvedores experientes já usam sem perceber. Como, por exemplo: **entender o custo real de uma alocação, saber a diferença entre passagem por valor e por referência, e perceber quando uma cópia desnecessária está acontecendo**. Ela também reforça princípios clássicos, como o **RAII (Resource Acquisition Is Initialization)**, a separação entre stack e heap, além de paradigmas poderosos que coexistem na mesma linguagem, como a **programação orientada a objetos, genérica e funcional**.

A linguagem também reúne uma série de recursos que parecem complexos, mas que fazem total sentido quando você entende o porquê:

- Usar **smart pointers** (`unique_ptr`, `shared_ptr`) ao invés de `new` e `delete` manuais, deixando o gerenciamento de memória mais seguro.
- Aproveitar **templates** para criar código genérico e reutilizável, sem perder performance.
- Aplicar **move semantics** para evitar cópias desnecessárias e tornar o código mais eficiente.
- Estruturar classes com **construtores, destrutores e operadores** bem definidos, seguindo a regra dos cinco.
- Usar a **STL (Standard Template Library)** com `vector`, `map`, `unordered_map` e algoritmos prontos antes de reinventar a roda.
- Priorizar o uso de **const correctness**, deixando claro o que pode e o que não pode ser modificado.
- Separar interface e implementação com **headers e arquivos de implementação**, mantendo o projeto modular.
- Aproveitar **lambdas e std::function** para escrever código mais expressivo.
- Esconder dependências e detalhes internos atrás de **classes e namespaces**, mantendo o código organizado.
- Usar ferramentas modernas como **CMake, clang-tidy e sanitizers** para manter qualidade e segurança no projeto.

O mais curioso é que percebo esses ensinamentos voltando constantemente no meu dia a dia, mesmo quando estou trabalhando em outras linguagens. Em revisões de PR, sessões de *pair programming* e conversas com o time, eu me pego pensando em **custo de memória, tempo de vida de objetos e eficiência**, o que prova que C++ não ensina apenas a escrever código performático, mas também a **pensar como o computador realmente funciona**.

Outro ponto alto é o enorme arsenal de **recursos modernos** introduzidos a partir do C++11. Ele transformou a linguagem em algo muito mais expressivo e seguro do que era nos anos 90. Porque no fim, **C++ não é só uma linguagem antiga, é uma linguagem em constante evolução, que aprendeu com seus próprios erros e amadureceu junto com a indústria**.

## O que eu não gostei na linguagem

<b> É muito complexa </b>

A linguagem traz tantos recursos e formas de fazer a mesma coisa que pode assustar quem está começando.
Só que engenharia é contexto. Às vezes uma feature poderosa em um cenário se torna um pesadelo em outro, principalmente em times grandes onde cada pessoa escreve C++ de um jeito diferente.

<b> Algumas escolhas históricas envelheceram </b>

- Headers e arquivos de implementação podem deixar a build muito lenta
- Macros do pré-processador ainda estão por toda parte e geram dor de cabeça
- A compatibilidade com C traz junto várias armadilhas que poderiam ter sido evitadas

<b> O lado perigoso </b>

A forma como C++ entrega tanto poder ao desenvolvedor pode ser vista como **flexível e ao mesmo tempo perigosa**, o que acaba sendo uma faca de dois gumes. Ao mesmo tempo em que oferece controle absoluto sobre memória e performance, a linguagem **nem sempre protege você contra seus próprios erros**. Isso pode confundir, principalmente quem está começando na carreira e ainda não desenvolveu um senso crítico mais apurado.

Levar features como **herança múltipla** ou **sobrecarga de operadores** como soluções universais pode, na prática, piorar um projeto. Por exemplo: usar herança múltipla cegamente pode criar **hierarquias confusas**, gerando uma teia de dependências, mas **cheias de complexidade desnecessária**. O resultado é um código fragmentado, difícil de entender, e que dá mais trabalho para manter do que se composição simples tivesse sido usada.

Um bom desenvolvedor precisa entender que, às vezes, **a abordagem mais simples é a escolha mais sensata** — seja para deixar a leitura mais clara, evitar indireções confusas ou até melhorar o tempo de compilação. Em C++, **nem todo recurso da linguagem precisa ser usado em todo projeto**, assim como **nem toda otimização precoce é uma solução**.

Outro ponto crucial: o controle de baixo nível **não pode vir acima de fundamentos maiores de design**, como:

- Acoplamento baixo
- Coesão alta
- Encapsulamento e ocultação de detalhes
- Separação clara de responsabilidades

Priorizar performance e truques da linguagem sem enxergar o impacto na estrutura do sistema pode levar a decisões que parecem "rápidas" na teoria, mas **causam mais dano do que benefício no longo prazo**. No fim, código sustentável nasce do equilíbrio: usar os recursos da linguagem, sim, **mas sempre considerando o cenário real, os custos e os trade-offs**.


## Conclusão

*C++* é uma linguagem de grande influência e continua sendo extremamente relevante.  
Seus recursos são poderosos, mas não devem ser tratados como ferramentas que precisam ser usadas a qualquer custo.

O maior aprendizado que levo da linguagem não é dominar cada recurso novo a cada padrão lançado, e sim desenvolver um olhar mais crítico sobre **performance, gerenciamento de recursos e responsabilidade no código**.  
Código bem escrito em C++, no fim, é aquele que equilibra controle de baixo nível com clareza, evitando complexidade desnecessária e favorecendo a manutenção.

Vale o estudo. Melhor ainda é a aplicação consciente.
