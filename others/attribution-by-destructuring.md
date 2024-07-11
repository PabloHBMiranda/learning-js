# Atribuição por Desestruturação em JavaScript

A atribuição por desestruturação é uma expressão JavaScript que torna possível a extração de dados de arrays, objetos e mapas em variáveis distintas. Isso pode ser feito de uma maneira que seja mais legível e expressiva, tornando o código mais limpo e fácil de entender.

## Desestruturação de Objetos

A desestruturação de objetos permite que você extraia propriedades de um objeto e as atribua a variáveis em uma única linha.

```javascript
const objeto = { nome: 'João', idade: 30 };

const { nome, idade } = objeto;

console.log(nome); // João
console.log(idade); // 30
```

## Desestruturação de Arrays

A desestruturação de arrays permite que você extraia elementos de um array e os atribua a variáveis em uma única linha.

```javascript
const array = ['Maçã', 'Banana', 'Cereja'];

const [primeiro, segundo, terceiro] = array;

console.log(primeiro); // Maçã
console.log(segundo); // Banana
console.log(terceiro); // Cereja
```

## Desestruturação de Parâmetros de Função

A desestruturação também pode ser usada nos parâmetros de uma função. Isso é útil quando a função recebe um objeto ou array como argumento.

```javascript
function apresentaPessoa({ nome, idade }) {
  console.log(`Meu nome é ${nome} e eu tenho ${idade} anos.`);
}

const pessoa = { nome: 'João', idade: 30 };

apresentaPessoa(pessoa); // Meu nome é João e eu tenho 30 anos.
```
