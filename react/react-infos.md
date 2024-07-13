# Funcionalidades do React

# Funcionalidades do React

React é uma biblioteca JavaScript para construir interfaces de usuário de forma eficiente e interativa. Aqui estão algumas de suas principais funcionalidades:

## JSX

JSX é uma sintaxe que se assemelha a HTML e é usada dentro do código JavaScript. Permite escrever a estrutura dos componentes React de uma maneira mais legível e expressiva.

```jsx
const elemento = <h1>Olá, mundo!</h1>;
```

- `elemento`: Elemento JSX que será renderizado.

## Componentes

Componentes são blocos de construção reutilizáveis que podem ser combinados para criar interfaces de usuário complexas. Eles aceitam entradas chamadas `props` e retornam elementos React.

```jsx
function MeuComponente(props) {
  return <h1>Olá, {props.nome}!</h1>;
}
```

- `MeuComponente`: Função que retorna um elemento React.
- `props`: Objeto que contém as propriedades passadas para o componente.

## Estado e Ciclo de Vida

O estado é um objeto que contém dados que controlam o comportamento de um componente. O ciclo de vida de um componente React é composto por métodos que são chamados em diferentes fases do ciclo de vida do componente.

```jsx
class MeuComponente extends React.Component {
  constructor(props) {
    super(props);
    this.state = { contador: 0 };
  }

  render() {
    return <h1>Contador: {this.state.contador}</h1>;
  }
}
```

- `state`: Objeto que contém os dados do estado do componente.
- `render()`: Método que retorna o elemento React a ser renderizado.
- `constructor()`: Método que inicializa o estado do componente.
- `O que é um ciclo de vida?`: Sequência de fases que um componente passa desde a sua criação até a sua destruição.

## Hooks

Hooks são funções que permitem adicionar funcionalidades de estado e ciclo de vida a componentes funcionais. Eles permitem reutilizar lógica de estado sem precisar de classes.

```jsx
import React, { useState } from 'react';

function Exemplo() {
  const [contagem, setContagem] = useState(0);

  useEffect(() => {
    document.title = `Você clicou ${contagem} vezes`;
  });

  return (
    <div>
      <p>Você clicou {contagem} vezes</p>
      <button onClick={() => setContagem(contagem + 1)}>
        Clique aqui
      </button>
    </div>
  );
}
```

- `useState`: Hook que adiciona estado a um componente funcional.
- `useEffect`: Hook que permite realizar efeitos colaterais em componentes funcionais.
- `contagem`: Variável de estado que armazena a contagem de cliques.
- `setContagem`: Função que atualiza o estado da contagem.

## Contexto

O contexto é uma forma de compartilhar dados entre componentes sem precisar passar props manualmente em cada nível da árvore de componentes. Ele é útil para dados que são considerados "globais" para a aplicação.

```jsx
const TemaContext = React.createContext('claro');

function App() {
  return (
    <TemaContext.Provider value="escuro">
      <Toolbar />
    </TemaContext.Provider>
  );
}

function Toolbar(props) {
  return (
    <div>
      <BotaoTema />
    </div>
  );
}

function BotaoTema() {
  const tema = useContext(TemaContext);
  return <button tema={tema}>Mudar Tema</button>;
}
```

- `createContext`: Função que cria um objeto de contexto.
- `Provider`: Componente que fornece o valor do contexto para os componentes filhos.
- `useContext`: Hook que permite acessar o valor do contexto em componentes funcionais.
