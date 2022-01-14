---
slug: a-falacia-da-madeira-verde
title: A Falacia da Madeira Verde na Engenharia de Software
authors: [jwandekoken]
tags: [engenharia de software, traduções]
image: https://images.unsplash.com/photo-1567080586917-e6ab6aa0df85?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80
---

Há uma falácia da madeira verde na Engenharia de Software...

<!--truncate-->

Artigo original escrito por [Chris Behan](https://www.chrisbehan.ca/posts/green-lumber-fallacy-in-software).

"Madeira Verde" é um termo usado para descrever madeira que foi cortada recentemente. Um dos mais bem-sucedidos vendedores de madeira verde, Joe Siegel, erroneamente achou que a madeira verde que vendia era madeira que havia sido pintada de verde. Joe fez uma fortuna negociando madeira verde, sem saber o que era. Outros comerciantes de commodities, mais bem versados na teoria do comércio de commodities, zombavam de Joe, pois achavam que ele carecia daquilo que acreditavam ser “conhecimento essencial”. Mas enquanto esses comerciantes, com um estilo mais acadêmico (muitos dos quais foram à falência), estavam obcecados com semântica e teorias sobre o que fazia com que o preço da madeira mudasse, Joe fez aquilo que fazia de melhor: comercializar a madeira. Parece que saber a origem do termo “madeira verde” é irrelevante para se tornar um comerciante de madeira verde bem-sucedido, não importa o quanto os teóricos queiram acreditar no contrário.

Nassim Nicholas Taleb cunhou o termo “Falácia da Madeira Verde” para descrever cenários em que um grupo de pessoas em um domínio confunde conhecimento irrelevante com conhecimento essencial. Há uma falácia da madeira verde na Engenharia de Software. Particularmente, durante o processo de entrevista, onde se espera que os candidatos resolvam quebra-cabeças de programação que requem reconhecimento de estruturas de dados e algoritmos (DSA). Estas entrevistas tipo teste confundem as árvores (estruturas de dados e algoritmos) com a floresta (construir software).

Certamente uma compreensão geral das estruturas de dados e algoritmos ajuda a construir software, mas o desenvolvimento de software não se trata de estruturas de dados e algoritmos. Estruturas de dados e algoritmos são variáveis (x1, x2) que contribuem para a função de desenvolvimento de software (f(x1..xn)), que depende de diversas outras variáveis como a capacidade de pensamento verbal e crítico. Pessoalmente, eu preferiria trabalhar com alguém que seja ótimo em nomear funções e variáveis do que alguém que possa resolver uma solução para [o problema da mochila](https://en.wikipedia.org/wiki/Knapsack_problem#).

Max Howell, autor do mais popular gerenciador de pacotes do MacOS, foi rejeitado pelo Google por ter falhado na parte técnica de sua entrevista. Apesar de ter um histórico comprovado de criação de software de sucesso (provavelmente usado por milhares de engenheiros do Google), Max não conseguiu inverter uma árvore binária em um quadro branco. Isso é como cortar Shaquille O'Neil de seu time de basquete porque ele não acertou lances livres suficientes no try-out. Todos sabemos que o jogo de basquete é mais que isso.

Todas as empresas MAANG utilizam como métrica principal para a contratação de candidatos as questões de algoritmos e system design style. A justificativa interna para fazê-lo é provavelmente uma combinação de “isto é o que todos fazem” e “é uma maneira rápida de avaliar a habilidade de alguém”. Ao primeiro ponto, eu digo: “todos os outros estão fazendo isso errado” e para o segundo ponto digo: “sim, é uma maneira rápida de avaliar suas habilidades competitivas de programação”. Nunca ouvi falar de um ex-competidor do [ICPC](https://icpc.global/) que construiu um ótimo software, amplamente utilizado, mas tenho certeza de que todo ex-competidor do ICPC teria um desempenho superior ao dos melhores criadores de software, em questões de estilo entrevista. É quase como se seus conjuntos de habilidades fossem totalmente diferentes.

Também é provável que você decepcione os candidatos (particularmente os juniors) que, após passar por um processo de entrevista tecnicamente rigoroso, descobrem que o trabalho real é desprovido de tal estimulação mental. Em vez de resolver problemas difíceis em um cronograma apertado, como é feito durante o processo de entrevista, o trabalho real consiste principalmente em escrever documentos, ler código e conectar um monte de serviços AWS juntos como lego para adultos. O seguinte meme faz um ótimo trabalho para ilustrar este ponto:

![interview-meme](./interview_meme.jpg)

A solução para a falácia da madeira verde no processo de contratação de software de engenharia é reconhecer que a solução de problemas de Estrutura de dados e algoritmos e o processo de construção de software são duas coisas diferentes. Quanto mais próximo o processo de entrevista estiver do trabalho real, mais precisamente você será capaz de avaliar a capacidade de um candidato em realizar esse trabalho. A inclusão de tarefas para levar para casa e a programação de pares no processo de entrevista são passos na direção certa, mas a melhor solução é ter períodos de trabalho experimental.

Não há melhor maneira de ver como alguém se desempenha no trabalho do que tê-lo de fato trabalhando. Os críticos desta sugestão são geralmente rápidos em refutar com "os candidatos nunca concordariam com isso" e "isso não escala". Eu pessoalmente adoraria um processo experimental que me desse uma visão de como o dia-a-dia realmente é, como é a verdadeira cultura da empresa e como são meus colegas de equipe. E eu conheço muitos engenheiros que compartilham este sentimento. Concordo que períodos de trabalho experimental podem não escalar, mas você sabe o que também não escala? Contratar um monte de pessoas que não possuem as habilidades necessárias para o trabalho, tais como comunicação e ética de trabalho, que são necessárias para a construção de software de qualidade.

Encontrou algum erro no artigo? [Mande um PR aqui!](https://github.com/jwandekoken/codefanatics-content/tree/main/blog/2022-01-13-a-falacia-da-madeira-verde)
