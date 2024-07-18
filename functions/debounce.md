# Debounce

## Conceito de Debounce

Debounce é uma técnica usada para garantir que um determinado tempo passe antes de uma função ser executada. Isso é útil para evitar que uma função seja chamada muitas vezes em um curto período de tempo, o que pode causar problemas de desempenho.

```javascript
function debounce(funcao, tempo) {
    let timeoutId;
    
    return function(...args) {
        clearTimeout(timeoutId);
        
        timeoutId = setTimeout(() => {
            funcao(...args);
        }, tempo);
    };
}
```

- `funcao`: A função que será executada após o tempo especificado.
- `tempo`: O tempo em milissegundos que deve passar antes da função ser executada.
- `timeoutId`: O ID do timeout que será usado para cancelar a execução da função.
- `...args`: Os argumentos que serão passados para a função.
