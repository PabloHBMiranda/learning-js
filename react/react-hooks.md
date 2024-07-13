# Hooks no React

Os Hooks são funcionalidades introduzidas na versão 16.8 do React que permitem a utilização de estado e outros recursos do React em componentes funcionais, sem a necessidade de transformá-los em classes. Eles oferecem uma forma mais direta e menos verbosa de implementar lógicas de estado e efeitos colaterais, entre outros, em componentes.

## `useState`

Este Hook é utilizado para adicionar estado local a um componente funcional. Ele retorna um par de valores: o estado atual e uma função que permite atualizar esse estado. Isso possibilita que o componente reaja a mudanças de dados e atualize a UI de forma declarativa.

```javascript
const [estado, setEstado] = useState(valorInicial);
```

## `useEffect`

Permite que você realize efeitos colaterais em componentes funcionais. Ele é executado após a renderização do componente e sempre que uma ou mais dependências mudam. Isso é útil para lidar com operações assíncronas, eventos, entre outros.

```javascript
useEffect(() => {
    // Efeito colateral
    return () => {
        // Limpeza opcional
    };
}, [dependências]);
```

- `Efeito colateral`: Código que realiza operações secundárias, como chamadas de API, manipulação do DOM, entre outros.
- `dependências`: Array de valores que, quando alterados, fazem com que o efeito seja executado novamente.
- `Limpeza opcional`: Função que é executada quando o componente é desmontado ou quando as dependências mudam.

## `useContext`

Facilita o acesso a dados em contextos, permitindo que componentes funcionais consumam dados de contexto sem a necessidade de utilizar um Consumer explicitamente. Isso simplifica o acesso a dados globais como temas, dados de autenticação, entre outros.

```jsx
const valorDoContexto = useContext(Contexto);
```

- `Contexto`: Objeto de contexto criado com createContext.
- `valorDoContexto`: Valor atual do contexto.

## `useReducer`

É uma alternativa ao `useState` para gerenciar estados complexos em componentes funcionais. Ele aceita um reducer e um estado inicial e retorna o estado atual e uma função de despacho de ações. O reducer é uma função que recebe o estado atual e uma ação e retorna o novo estado.

```jsx
const [estado, dispatch] = useReducer(reducer, estadoInicial);
```

- `reducer`: Função que recebe o estado atual e uma ação e retorna o novo estado.
- `estadoInicial`: Estado inicial do reducer.
- `estado`: Estado atual.
- `dispatch`: Função para despachar ações.

## `useCallback`

Retorna uma versão memoizada de um callback que só muda se uma das dependências tiver mudado. Isso é útil para otimizar o desempenho de componentes filhos que dependem da igualdade de referência para evitar renderizações desnecessárias.

```jsx
const memoizadoCallback = useCallback(() => {
    // Função que faz algo que depende de `deps`
}, [deps]);
```

- `deps`: Dependências que, quando alteradas, fazem com que o callback seja recalculado.
- `memoizadoCallback`: Callback memoizado.

## `useMemo`

Retorna um valor memoizado que só muda quando uma das dependências tiver mudado. Isso é útil para otimizar o desempenho de componentes filhos que dependem da igualdade de referência para evitar renderizações desnecessárias.

```jsx
const memoizadoValor = useMemo(() => calcularValor(dado), [dado]);
```

- `calcularValor`: Função que retorna o valor a ser memoizado.
- `dado`: Dependência que, quando alterada, faz com que o valor seja recalculado.
- `memoizadoValor`: Valor memoizado.
- `Oque é um valor memoizado?`: Um valor que é armazenado em cache e só é recalculado quando necessário.

## `useRef`

Permite acessar diretamente elementos do DOM ou manter uma referência mutável que não causa re-renderização do componente quando atualizada. Útil para armazenar valores que persistem a mesma instância entre renderizações.

```jsx
const meuRef = useRef(valorInicial);
```

- `meuRef.current`: Valor atual do ref.
- `valorInicial`: Valor inicial do ref.

## `useLayoutEffect`

Similar ao `useEffect`, mas é sincronizado com o DOM. Ele é executado após a renderização, mas antes da atualização da tela, sendo útil para medir elementos do DOM ou realizar manipulações que requerem que o DOM esteja pronto.

```jsx
useLayoutEffect(() => {
    // Efeito colateral
    return () => {
        // Limpeza opcional
    };
}, [dependências]);
```

## `useImperativeHandle`

Permite que um componente pai acesse funções de um componente filho. Isso é útil para abstrair a implementação de um componente filho e expor apenas as funções necessárias para o componente pai.

```jsx
useImperativeHandle(ref, () => ({
    funcaoDoFilho
}), [dependências]);
```

## `useDebugValue`

Permite fornecer um nome para um Hook customizado para facilitar a depuração. O nome é exibido na DevTools do React.

```jsx
useDebugValue(valor, () => 'Nome do Hook');
```
