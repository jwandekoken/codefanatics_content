---
slug: ponto-de-exclamacao-typescript
title: Ponto de Exclamação no TypeScript (Non-Null Assertion Operator)
authors: [jwandekoken]
tags: [TypeScript]
image: ./2022-01-23-ponto-de-exclamacao-typescript.jpg
---

"const value = data!" - Que diabos é esse "!"?

<!-- truncate -->

Artigo original escrito por [Volodymyr Hudyma](https://vhudyma-blog.eu/exclamation-mark-operator-in-typescript/).

Se você usa TypeScript, certamente pode ter se deparado com o operador ponto de exclamação (!), que aparentemente realiza alguma mágica, fazendo o compilador do TypeScript ignorar possíveis erros.

Vamos aprender qual é o propósito desse operador, os riscos de sua utilização, e como podemos usa-lo de maneira útil em nossos projetos.

## Non-Null Assertion Operator

O operador "ponto de exclamação" é chamado de **Non-Null Assertion Operator**, e sua utilização faz o compilador ignorar tipos **undefined** e **null**.

Considere o exemplo abaixo:

```ts
const prepareValue = (value?: string) => {
  // ...
  parseValue(value);
};

const parseValue = (value: string) => {
  // ...
};
```

O código acima levará ao seguinte erro:

**Argument of type 'string | undefined' is not assignable to parameter of type 'string'.
Type 'undefined' is not assignable to type 'string'.**

Em tradução livre, algo como: "Argumento do tipo 'string | undefined' não é assinalável ao parâmetro do tipo 'string'. Tipo 'undefined' não é assinalável ao tipo 'string'."

Está certo, pois nós esperamos que `value` na função `prepareValue` seja `undefined` ou `string`, mas, quando passamos o `value` para a função `parseValue`, estamos esperando apenas `string`.

No entanto, em alguns casos, nós podemos ter certeza de que `value` não será `undefined`, e esse é o caso de uso em que podemos precisar do **Non-Null Assertion Operator**.

```ts
const prepareValue = (value?: string) => {
  // ...
  parseValue(value!);
};

const parseValue = (value: string) => {
  // ...
};
```

O código acima funciona normalmente.

No entanto, devemos ter muito cuidado ao usar este operador, pois seu uso indiscriminado pode levar a comportamentos inesperados, caso `value` seja de fato `undefined`.

## Quando ele é útil?

Agora que sabemos o que é o **Non-Null Assertion Operator**, precisamos conhecer alguns casos de uso reais.

### Buscando por um item que existe em uma Lista

Em alguns casos, você tem certeza de que um elemento está presente em uma lista, e você pode querer realizar uma busca por ele:

```ts
interface Config {
  id: number;
  path: string;
}

const configs: Config[] = [
  {
    id: 1,
    path: "path/to/config/1",
  },
  {
    id: 2,
    path: "path/to/config/2",
  },
];

const getConfig = (id: number) => {
  return configs.find((config) => config.id === id);
};

// Type is "Config | undefined"
const config = getConfig(1);
```

Nós temos uma lista de configs e queremos obter o config object baseado em um id.

O código acima funciona, mas, se nós olharmos para o tipo da variável `config`, seria `Config | undefined`.

Nós podemos usar o **Non-Null Assertion Operator** para dizer para o TypeScript que `config` deve existir, e não precisamos assumir que ele pode ter valor `undefined`:

```ts
// ...

const getConfig = (id: number) => {
  // Non-Null Assertion Operator is added at the end of this line
  return configs.find((config) => config.id === id)!;
};

// Type is "Config"
const config = getConfig(1);
```

Voilà, se quisermos obter alguma propriedade do `config` object, não mais precisamos checar se ele existe antes.

### Lidando com Refs no React

[Refs] no React nos oferecem uma maneira de acessarmos nodes do DOM ou elementos React:

```ts
// ...

const App = () => {
  const ref = useRef<HTMLDivElement>(null);

  const handleClick = () => {
    if (ref.current) {
      console.log(ref.current.getBoundingClientRect());
    }
  };

  return (
    <div className="App" ref={ref}>
      {/* ... */}
      <button onClick={handleClick}>Click Me</button>
    </div>
  );
};
```

No exemplo acima, nós criamos um componente simples, que tem acesso ao DOM node da `div` com a classe `App`.

Nós temos também um botão que, quando clicado, mostra o tamanho de um elemento, e sua posição na viewport.

Nesse exemplo simples, nós temos certeza de que o elemento que está sendo acessado está mounted depois do clique no botão, logo, nós podemos adicionar nosso o **Non-Null Assertion Operator**:

```ts
// ...

const App = () => {
  // ..

  const handleClick = () => {
    console.log(ref.current!.getBoundingClientRect());
  };

  // ..
};
```

## Quando não é útil?

Basicamente, ao usar este operador, nós estamos dizendo para o TypeScriopt: **"eu sei mais que você neste caso, e irei me responsabilizar caso dê merd#"**, então, você agora tem muito mais responsabilidade pelo seu código.

Se, por algum motivo, a sua asserção não for verdadeira, um runtime error irá ocorrer.

Por isso, em 99% das ocasiões, é melhor não utiliza-lo.

É muito mais seguro lidar com esses casos adicionando checagens adicionais.

## Sumário

O **Non-Null Assertion Operator** força o compilador do TypeScript ignorar tipos `undefined` e `null`.

Desenvolvedores devem ter cuidado extremo ao utilizá-lo, pois o mal uso irá resultar em runtime errors, os quais poderiam ser prevenidos pelo TypeScript.

No entanto, em alguns casos especiais, ele pode fazer seu código ficar mais sucinto, e te permite pular checagens extras.

Encontrou algum erro no artigo? [Faça um PR aqui]()!
