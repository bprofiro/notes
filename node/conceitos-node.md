# Conceitos NodeJS

## O que é?
O Node é um ambiente de desenvolvimento JavaScript no Backend. Ele foi construído
em cima da V8, por isso é possível desenvolver na parte do
servidor com o JS.

> ##### - V8:
> Enginee do Google Chrome, é um interpretador JavaScript, também chamado de 
> máquina virtual JS.

## O que é NPM/Yarn?
Gerenciadores de pacotes que permitem a instalação de bibliotecas de terceiros
ou o fornecimento de bibliotecas para terceiros.

## Características do Node.JS
- Possui Arquitetura Event loop e uma arquitetura baseada em eventos e *Call Stack*.
> Last in, first out: executa as funções em pilha e em loop.

- Non-blocking I/O: Não perde a conexão com o frontend após retornar uma função.

## Frameworks
- ExpressJS como base:
 - É um framework *sem opinão*, ou seja, não possui uma estrutura fechada 
 de pastas. Além de também ser ótimo para micro-serviços.

 > Frameworks com opinião:
  > - AdonisJS
  > - NestJS

## Package.json
- Todo projeto JavaScripr tem esse arquivo e ele serve para armazenar as 
informações de dependências do projeto, sua versão, nome do projeto e descrição.