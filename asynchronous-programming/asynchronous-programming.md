# Programação Assíncrona em JavaScript

A programação assíncrona é um paradigma fundamental no desenvolvimento JavaScript, permitindo que operações demoradas, como solicitações de rede, leitura de arquivos ou temporizadores, sejam executadas sem bloquear o thread principal. Isso é crucial para manter as aplicações web responsivas.

## Callbacks

Os callbacks foram a primeira abordagem para lidar com operações assíncronas em JavaScript. Um callback é uma função passada como argumento para outra função, que é então chamada quando a operação assíncrona é concluída.

```javascript
function exemploCallback(url, callback) {
  fetch(url)
    .then(response => response.json())
    .then(data => callback(null, data))
    .catch(error => callback(error, null));
}
```

## Promessas

As Promessas são uma evolução dos callbacks, oferecendo uma maneira mais limpa e compreensível de lidar com a assincronia. Uma Promessa representa um valor que pode estar disponível agora, no futuro ou nunca.

```javascript
function exemploPromessa(url) {
  return fetch(url).then(response => response.json());
}
```

## Async/Await

async e await são uma adição mais recente ao JavaScript, permitindo escrever código assíncrono que parece síncrono. Uma função marcada como async pode usar await para pausar sua execução até que uma Promessa seja resolvida.

```javascript
async function exemploAsync(url) {
  const response = await fetch(url);
  const data = await response.json();
  return data;
}
```
## Tratamento de Erros

O tratamento de erros em operações assíncronas é crucial. Com callbacks, os erros são passados como o primeiro argumento. Promessas usam o método .catch() para capturar erros, e async/await permite o uso de blocos try/catch.

```javascript
async function exemploErro(url) {
  try {
    const response = await fetch(url);
    const data = await response.json();
    return data;
  } catch (error) {
    console.error('Erro:', error);
  }
}
```
