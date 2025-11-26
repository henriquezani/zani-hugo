---
title: Diferenças entre MVC, MVP e MVVM — Design Patterns
date: "2022-05-20T14:00:00-03:00"
slug: mvc-mvp-mvvm-design-patterns
tags:
  - Design Patterns
  - MVC
  - MVP
  - MVVM
draft: false
---

![inhibit list](https://miro.medium.com/v2/resize:fit:786/format:webp/1*8933YZqPjm3bjl_ySZR9kw.png)

No desenvolvimento de aplicativos, temos três principais tipos de padrões de projeto— MVC vs MVP vs MVVM.

Padrões de projeto são uma ótima maneira de reforçar as melhores práticas no desenvolvimento de software. Eles nos ajudam a estruturar nossos aplicativos para que sejam mais fáceis de manter e evoluir, garantindo modularidade, coesão e injeção de dependência.

Na superfície, esses três padrões podem parecer muito semelhantes. Todos eles envolvem uma interface de usuário e um controlador que interage com a interface de usuário de uma forma ou de outra.

No entanto, na realidade, esses tipos de padrões de projeto têm diferentes casos de uso e não devem ser usados ​​quando as situações ditam a necessidade de algo diferente do que eles oferecem.

Saiba mais sobre quando implementar cada tipo de padrão neste artigo! Neste artigo, faremos uma comparação MVC Vs MVP Vs MVVM para descobrir seus recursos especiais.


## MVC (Model-View-Controller)
![inhibit list](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ZB3ztISeyfETFPbH9nb-qw.png)

No padrão MVC, os recursos são divididos em três componentes com base em três preocupações separadas. Em primeiro lugar, a view é responsável por renderizar os elementos da interface do usuário. Em segundo lugar, o controller responde às ações da interface do usuário. E o model lida com comportamentos de negócios e gerenciamento de estado.

### Model

Representa basicamente os dados que serão exibidos na tela. Na maioria dos casos, isso se refere à comunicação entre os bancos de dados.

Essa comunicação pode ser na forma de adicionar novos dados, alterar os existentes ou selecionar dados específicos. Ele executa operações nos dados brutos. Os dados exibidos por ele para o usuário podem estar em qualquer formato.

### View

View é usado para exibir os dados tomados como entrada pelo model para o usuário. Ele representa os componentes da interface do usuário, como HTML e XML.

### Controller

Como o nome sugere, o Controller é responsável por tratar de todos os processos, ou seja, é responsável por resolver todas as requisições externas e atender essas requisições. Leva os dados do usuário através do modelo para visualização, atuando como um mediador entre os dois.

Ele recebe na entrada um conjunto de dados brutos que devem ser transmitidos ao usuário e o formata seguindo os requisitos do usuário.

### Vantagens
- O desenvolvimento do aplicativo se torna rápido.
- Fácil para vários desenvolvedores colaborarem e trabalharem juntos.
- Mais fácil de atualizar o aplicativo.
- Mais fácil de depurar, pois temos vários níveis escritos corretamente na aplicação.

### Desvantagens
- É difícil entender a arquitetura MVC.
- Deve ter regras rígidas sobre métodos.
- Custo de atualizações frequentes

Não há muito na parte de desvantagens da arquitetura. E as desvantagens não são tão grandes e são muito fáceis de ignorar em comparação com todos os benefícios que obtemos.

## MVP (Model–View–Presenter)
![inhibit list](https://miro.medium.com/v2/resize:fit:640/format:webp/1*NSMtVomjRCxN97E8omqw2Q.png)

O padrão MVP é um padrão de apresentação de interface do usuário baseado nos conceitos do padrão MVC. No entanto, não especifica como estruturar todo o sistema. Ele apenas determina como estruturar a view.

### Model

O Modelo representa um conjunto de classes que descreve a lógica e os dados de negócios. Ele também define regras de negócios para dados significa como os dados podem ser alterados e manipulados.

### View

View é usado para fazer interações com usuários. Não tem nada a ver com a lógica que deve ser implementada no processo.

### Presenter

É a unidade de processamento do sistema. O presenter obtém a entrada da View, processa os dados com a ajuda do Model e passa os resultados de volta para a View após o processamento ser concluído.


Para simplificar o modelo MVP, o presenter responde aos dados de entrada e os retorna à view após a conclusão do processamento. View e Presenter não estão relacionados entre si e interagem apenas por meio da interface.

### Vantagens
- Reutilização de código
- Abordagem orientada a testes
- Design adaptável

### Desvantagens
- Maior complexidade
- Experiência e conhecimento fazem a diferença na implementação correta
- Não é adequado para soluções simples e pequenas

## MVVM (Model-View-ViewModel))
![inhibit list](https://miro.medium.com/v2/resize:fit:750/format:webp/1*B9o2Bwa4iI9p1Vpzft3tRQ.png)

O padrão MVVM dá suporte à vinculação de dados bidirecional entre View e View-Model. Isso permite a propagação automática de alterações, dentro do estado de View-Model para a View. Geralmente, o View-Model utiliza o padrão do observador para informar as mudanças no View-Model para o Model.

### Model

O model utilizado no MVVM é semelhante ao model utilizado no MVC, composto pelos dados básicos necessários para a execução do software.

### View

View é uma interface gráfica entre o usuário e o padrão de projeto, semelhante à do MVC. Exibe a saída dos dados processados.

### View-Model

View-Model é por um lado uma abstração da View e, por outro, fornece um wrapper dos dados do Model a serem vinculados. Ou seja, ele compreende um model que é convertido em uma View, e também contém comandos que a View pode usar para influenciar o Model.

### Vantagens
- A lógica de negócios é dissociada da Ul
- Fácil de manter e testar
- Componentes fáceis de reutilizar
- Você pode escrever unit tests para a camada de view-model e model sem a necessidade de fazer referência à view.

### Desvantagens
- Manutenção de códigos no controller
- Algumas pessoas pensam que para UIs simples a arquitetura MVVM pode ser um exagero.
- Não oferece acoplamento rígido entre a view e o view-model

## Principais pontos de diferença

### Avaliação de desempenho

Quando estamos testando o desempenho da interface do usuário, o MVP acaba sendo aquele com a maior confiabilidade e o menor obstáculo quando se trata de renderização de quadros. A vinculação de dados no MVVM cria uma sobrecarga adicional que pode afetar drasticamente seu desempenho ao executar tarefas complexas.

### Compatibilidade

Ao testar os padrões com base em sua compatibilidade, o MVVM foi o melhor devido à sua vinculação de dados que teve um impacto positivo. O MVP se saiu melhor do que o MVC, que teve sérios problemas de reformulação.

### Referências

No MVC, a View não tem referência ao Controller, enquanto no MVP, a View tem referência ao presenter e no MVVM, a View tem referência ao View-Model.

### Ponto de entrada
Para MVC, o ponto de entrada para a aplicação é o controller, enquanto que, para MVP e MVVM, o ponto de entrada é a view.

## Conclusão

Um bom conhecimento dos padrões MVC, MVP e MVVM pode ajudá-lo a criar aplicativos extensíveis, sustentáveis e reutilizáveis. Este artigo forneceu os fundamentos iniciais sobre os padrões MVC, MVP e MVVM e seus benefícios e desvantagens.