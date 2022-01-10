---
slug: porque-redux-ainda-e-mais-relevante-do-que-nunca
title: Porque Redux ainda é mais Relevante do que Nunca
authors: [jwandekoken]
tags: [react, redux, traduções]
image: https://miro.medium.com/max/700/0*GAG4mQOmR60q9RzS
---

Será que de fato o Redux está morto?

<!--truncate-->

Recentemente eu encontrei diversas opiniões sugerindo que o ecossistema do React está recomendando que não mais seja utilizado o Redux em novos projetos, em favor de um movimento no sentido de um "React mais moderno", usando a Context API.

Alguns episódios do [React Podcast](https://reactpodcast.simplecast.com/) fizeram alusão a este movimento ("você já migrou o seu Redux para o Context?"), assim como tiveram vários artigos publicados subscrevendo a esta opinião. Ouvi de estudantes de Bootcamps que seus instrutores apressaram o conteúdo sobre Redux do currículo, porque era "muito complicado" e "as pessoas não utilizam mais, de qualquer forma". Inclusive, cheguei a ouvir de um desenvolvedor auto-didata novo que estava começando em um novo projeto em nossa empresa:

> "Eu achei que as pessoas estavam deixando de usar Redux para usar a Context API..."
>
> — <cite>Desenvolvedor auto-didata anônimo</cite>

Eu mesmo cheguei a sugerir que talvez o Thunks, uma ferramenta para realizar chamadas asíncronas, estavam se tornando algo obsoleto — opinião que não mais subscrevo, graças ao [Redux Toolkit](https://redux-toolkit.js.org/) e alguns inconvenientes que tive quando usando apenas hooks customizados em alguns projetos. Honestamente, acho que todos nós ficamos excitados com as novas features do React e pensamos "Esse é o futuro!". Certamente as features são legais, e elas nos permitem realizar várias coisas interessantes, no entanto, dispensar o Redux não é uma delas.

Talvez esse sentimento tenha surgido com um punhado de chamadas e títulos de artigos sem uma análise aprofundada sobre o tema, mas não, Redux não está morto. Claro, eu não pretendo aqui colocar uma pedra em cima do assunto. Inclusive, o Redux pode até não funcionar para todos os projetos. De fato, [Dan Abramov](https://overreacted.io/), o criador do Redux, sugeriu que talvez você não precise do Redux em seu projeto, em um artigo que data de 2016. Mas, para os meus projetos, eu encontrei diversas razões para continuar usar o Redux. Talvez, novos desenvolvedores React também considerarão essas razões, em vez de simplesmente descartarem a possibilidade, indo de encontro com o sentimento da manada sobre a Context API.

A natureza de meu trabalho me permite desenvolver diversas aplicações, nas quais tenho toda a liberdade para escolher as tecnologias, sem estar amarrado por escolhas passadas ou tecnologias legado, e essas aplicações possuem as os mais diversos níveis de complexidade. Isso me da, talvez, uma perspectiva única em relação ao o que é útil e o que não é. Eu aproveitei essa oportunidade quando nós tivemos diversos projetos "enfileirando nossa esteira" para testar diversas implementações de gerenciamento de estado, para nos ajudar a determinar onde nós estávamos gastando um tempo excessivo de forma desnecessária, e o que era realmente útil para identificarmos bugs e construirmos soluções confiavelmente bem arquitetadas. Essas variações incluíram apps com:

- Apenas usar useState hooks (tentando arquitetar de maneira a evitar o máximo de prop-drilling possível).
- Uma implementação vanilla, do zero, do Redux.
- Apenas a Context API.
- Uma implementação com o [Redux Toolkit](https://redux-toolkit.js.org/).

O que eu descobri foi que, mesmo em aplicações que deveriam ser pequenas, o escopo e os requerimentos acabam aumentando, de maneira que a aplicação se torna maior e mais complexa. Um dos melhores argumentos no sentido de substituir Redux pela Context API, é de que a Context API é mais simples, e faz mais sentido em aplicações menores. Mas, de acordo com minha experiência, eu argumentaria no sentido de que não existe o mítico "app pequeno". Se a aplicação vai para produção e gera valor para as pessoas, eventualmente irá crescer.

Adicionalmente, desenvolvedores no meu time que pegaram a Context API pela primeira vez começaram a se deparar com bugs relacionados a uma implementação com variáveis mutáveis. A refatoração do código para fazer a implementação usar variáveis imutáveis levou, basicamente, a uma re-implementação da API do Redux (através de funções reducers), mas sem o benefício da incrível Redux Dev Tools. Sério, a Redux Dev Tools é tão boa que eu nunca preciso usar um breakpoint ou um console.log quando estou debugando o estado do Redux. A habilidade de mapear cada ação que foi enviada, fazer um envio (dispatch) manual de novas ações em um app rodando, mapear exatamente de onde a ação foi enviada no código, e ver o estado total, assim como a mudança (state diff) realizada pela ação que foi enviada, abrir mão de todo esse poder de debug e visualização pela "simplicidade" da Context API, simplesmente não vale a pena.

Ainda no ponto da simplicidade — A razão principal em que a Context API é tida como mais simples do que o Redux é pela redução do código de boilerplate. No entanto, uma implementação **segura** da Context API, que leva em consideração imutabilidade, não tem muito menos código boiplerplate do que o Redux. Além disso, nos dias de hoje, o [Redux Toolkit](https://redux-toolkit.js.org/) significativamente reduziu o código boilerplate necessário. O Redux Toolkit é um grande divisor de águas neste debate. Eu provavelmente o descobri um pouco mais tarde do que deveria, mas sua relativa simplicidade, comparando com uma implementação do zero do Redux, basicamente derruba todo o argumento da Context API.

## Resumindo

1. Não vale a pena abrir mão do Redux Dev Tools por uma redução marginal de código boilerplate.
2. O [Redux Toolkit](https://redux-toolkit.js.org/) reduz a complexidade de implementação, comparando com a complexidade de implementar de forma segura a Context API.

## Conclusão

Redux, em minha opinião, não apenas não está morto — mas é mais relevante do que nunca. Com a adição do Redux Toolkit, as capacidades de gerenciamento de estado do Redux se tornaram melhores do que nunca. Novas features introduzidas no Redux Toolkit, como a [RTK Query](https://redux-toolkit.js.org/rtk-query/overview) parecem bem incríveis (não testei ainda, mas estou doido para fazê-lo). As pessoas contribuindo com o Redux Toolkit fizeram um trabalho tão incrível que minha organização prestará atenção na lib pelo próximo futuro, pois certamente os vemos como pioneiros.

Artigo original escrito por [Jason Lee Hodges](https://medium.com/@jasonleehodges). Você pode ler o artigo em seu formato original [aqui](https://betterprogramming.pub/why-redux-is-more-relevant-than-ever-today-6654f38df539).

Encontrou algum erro no artigo? Faça um fork e mande um PR [aqui](https://github.com/jwandekoken/codefanatics/tree/main/blog/2022-01-08-porque-redux-ainda-e-relevante)! 😃
