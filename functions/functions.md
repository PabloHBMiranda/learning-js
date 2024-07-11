# Documentação de Funções JavaScript

## Função Declarativa

Uma função nomeada com a palavra-chave `function`. É elevada (hoisting), o que significa que pode ser chamada antes de ser definida no código.

```javascript
function soma(a, b) {
  return a + b;
}
```

## Função Expressa

Uma função atribuída a uma variável. Não é elevada, então precisa ser definida antes de ser chamada.

```javascript
const subtracao = function(a, b) {
    return a - b;
};
```

## Função Autoinvocável (IIFE - Immediately Invoked Function Expression)

Uma função que é executada imediatamente após ser definida. Útil para criar um escopo privado.

```javascript
(function() {
    console.log('Função autoinvocável executada!');
})();
```

## Função de Seta (Arrow Function)

Uma sintaxe curta para escrever funções expressas.

```javascript
const exemplo = () => 'Olá, mundo!';
```

## Função Assíncrona

Uma função assíncrona é um tipo de função em JavaScript que permite que você execute operações que levam algum tempo para serem concluídas, como buscar dados de uma API na internet, sem bloquear ou esperar que a operação termine.
Para criar uma função assíncrona, você usa a palavra-chave async antes da declaração da função, e dentro dela, você pode usar await para esperar por operações assíncronas.

```javascript
async function buscaDados() {
    const resposta = await fetch('https://api.exemplo.com/dados');
    const dados = await resposta.json();
    return dados;
}
```
