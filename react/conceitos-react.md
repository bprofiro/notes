# Conceitos React
## O que é React?
-> É uma biblioteca para construção de interfaces que permite, por meio do SPA
(Single-Page Aplications), a integração com um backend e a integração com um
backend e a criação de interfaces de forma performática.

> Com o SPA:
> Antes: para cada rota acessada, o backend retornava um código HTML.
> Agora: o backend retorna apenas JSON e o front-end controla as rotas e como a
> aplicação vai export as informações.

## Benefícios:
-> Organização do código por meio da componentização. Os componentes são partes
da aplicação cujo o isolamento não interfirá no restante do funcionamento. Sua
estrutura é formada por HTML e a estilização por CSS.

## Divisão de responsabilidades:
Com isso, o backend armazena as regras de negócio e o frontend com a interface.
Com essa divisão, é possível ter uma única API para múltiplos clientes.

## JSX:
-> Escrever HTML dentro do JavaScript;
-> Com o React, conseguimos criar os nossos próprios componentes (utilizando JSX);

## Programação Imperativa X Programação Declarativa
#### Imperativa ❌
-> É preciso escrever todos os passos que a aplicação deve fazer, com todos os `if`

#### Declarativa ✔
-> Não comparamos com o estado anterior, apenas dizemos a condição em que esse
evento deve ocorrer

#### Webpack
-> Ele cria o bundle que é o arquivo com todo o código da aplicação, ele também
ensina o JS a importar arquivos CSS, imagens e etc.
 > -> Com ele também temos a funcionalidade de Live Reload, utilizando o
 > Webpack Dev Server.