# 5 Momentos em que você deveria usar o Node.js

  <p align="center">
    <img alt="Node" src="https://isitics.com/wp-content/uploads/2019/06/2400%D1%851260-rw-blog-node-js-1024x538.png" width="400"/>
  </p>

Somos programadores e, como bons programadores, estamos sempre buscando problemas para serem resolvidos por nós da melhor forma possível. Visto isso, no momento de começar um novo projeto e tomar a decisão de quais tecnologias serão usadas, é importante ter imparcialidade em relação à essas escolhas. 

  > Não importa o quanto você gosta de C, amigão. Se o seu problema for melhor resolvido em JavaScript, não importa o quanto isso irá doer em você, essa aplicação deve ser feita em JavaScript.

E é exatamente sobre isso que eu irei falar hoje: 5 problemas que poderiam ser resolvidos de forma mais fácil utilizando o Node.js. Queria dizer que esses não são os casos EXCLUSIVOS do Node.js, você pode resolver outros problemas com o Node.js também, estou apenas linkando 5 momentos em que o Node.js deveria ser priorizado no momento da decisão de quais tecnologias serão utilizadas no seu projeto por conta do seu propósito e facilidade de lidar com seu ecossistema.

  >Então pega a sua água, o seu chá ou o seu café e vamos lá!

## Primeiramente, o que é o Node.js?

O criador o Node, Ryan Dahl, um programador PHP estava construindo uma feature de barra de progresso. E enquanto ele fazia isso, ele percebeu que o navegador não sabia o quanto do arquivo foi carregado e, consequentemente, o browser estava fazendo muitas requisições para o back-end e isso estava consumindo muita memória.

Então ao contrário do que muita gente pensa, o Node.js não foi criado porque os amantes do JavaScript queriam levar ele para o back-end, muito além disso: o Node.js foi criado para *resolver um problema*. E esse problema era a forma como as linguagens lidavam com I/O (Input/Output -> Entradas/Saídas).

E, naquele momento, Ryan Dahl se perguntou: Qual linguagem tem a capacidade de fazer I/O não bloqueante? A resposta era simples: o JavaScript.

  > I/O não bloqueante é a capacidade de lidar com entradas e saídas de forma assíncrona. Iremos falar mais sobre isso um pouco mais pra frente, mas guarde a informação de que: o back-end consegue receber mais uma entrada por vez e entregar as saídas conforme elas são processadas.

E com isso surge o Node.js, que podemos dizer basicamente que é um ambiente de desenvolvimento JavaScript para o back-end e ele foi implementado baseado no V8 que é Engine do Google Chrome.


## 5 Momentos em que o Node.js é uma opção a ser priorizada no seu projeto:

### 1- Quando você é um dev Front-end e precisa fazer o back-end da sua aplicação sozinho
A versatilidade é uma das melhores qualidades de um desenvolvedor e, se você tem a capacidade de desenvolver o front-end e o back-end de uma aplicação, suas oportunidades aumentam consideravelmente. E é o que eu quero levar em consideração nesse tópico, se você acabar se encontrando em uma situação em que você é o responsável pelo desenvolvimento de uma aplicação do começo ao fim sozinho, o Node é uma ótima escolha, pois você poderá desenvolver toda a aplicação com uma única sintaxe, uma única linguagem e um único ecossistema.

Desenvolver toda a sua aplicação numa única linguagem vai tornar o processo mais prático e rápido, pois você não precisará "virar a chave" do seu cérebro para que ele "pense em outra linguagem".

### 2- Quando a sua aplicação recebe muitas entradas simultâneas:
Lembra que pedi para guardar a informação sobre I/O não bloqueante? Bom, ela será extremamente importante nesse momento.

Uma das melhores qualidades do Node.js é a sua capacidade de lidar com várias entradas simultâneas sem consumir muito espaço de memória. Isso se deve á sua arquitetura que é baseada em eventos e é formada por três partes:
  - Callback: que é a responsável por empilhar as chamadas de funções.
  - Callback Queue: que é responsável por empilhar os callbacks
  - Eventloop: responsável por monitorar se algum evento assíncrono foi disparado para assim executar sua respectível Callback.

  <p align="center">
    <img alt="Node" src="https://i.stack.imgur.com/02udF.jpg" width="400"/>
  </p>

Um exemplo prático de como funciona esse I/O não bloqueante é o seguinte: imagine um garçom em um restaurante. Ele vai até uma mesa para fazer o pedido e, depois disso, leva para a cozinha para que o pedido seja preparado. Enquanto esse pedido é feito, ele vai recolhendo o pedido de outras mesas e os levando para a cozinha. Ao decorrer que os pedidos são ficando prontos, o garçom os leva para sua respectiva mesa.

Em outras linguagens, que não possuem I/O não bloqueante, o que acontece é que o garçom pega o pedido de uma mesa, leva até a cozinha e fica parado esperando esse pedido ser feito para só então ele levar até a mesa. Um pedido por vez, uma única entrada e saída por vez.


### 3- Quando você irá utilizar um banco de dados NoSQL:

As bases de dados NoSQL são baseadas em JSON (JavaScript Object Notation), portanto a sua comunicação com o Node.js é muito intuitiva. Com isso você não precisará converter esses modelos de dados, pois os mesmos objetos JavaScript armazenados no seu banco de dados podem ser enviados para o front-end da sua aplicação sem nenhum tratamento ou conversão.

  >Um pequeno exemplo de um objeto JavaScript 
  ```json 
    { 
      name: Brenda, 
      sobrenome: Profiro 
    }
  ```

### 4- Quando você não pode utilizar muitos recursos
Como já explicado anteriormente, o Node.js consegue lidar com muitas entradas, ao contrário de outras linguagens. Isso ocorre por conta do seu conceito de single-thread, ou seja, apenas uma thread irá cuidar de todos os Inputs e Outputs da sua aplicação, ao contrário das outras linguagens que abrem uma nova thread cada vez que elas recebem uma nova requisição, o que consome muito mais armazenamento e capacidade de sua CPU.

Como no exemplo a seguir:

  <p align="center">
    <img alt="Node" src="https://www.opus-software.com.br/wp-content/uploads/2019/04/Captura-de-Tela-2019-04-22-a%CC%80s-15.26.05-768x842.png" width="400"/>
  </p>

Um exemplo de caso bastante interessantes sobre essa escalabilidade do Node utilizando poucos recursos é o do Paypal. Inicialmente, o Palpay decidiu reformular a tela de resumo da conta (que é uma das mais visitadas do site). Pra testar de forma segura, eles desenvolveram a plataforma em Node.js e em Java. O time que desenvolveu o node.js realizou a tarefa duas vezes mais rápido, com menos pessoas, 33% menos linhas de código e 40% menos arquivos. Em relação à performance da aplicação, a versão com Node.js conseguiu atender o dobro de usuários por segundo do que o Java, com uma média de 35% mais velocidade na entrega das requisições.

### 5- Quando você vai desenvolver aplicações Web:

O Node.js realmente brilha na criação de aplicativos escaláveis e rápidos. Se você quer isso na sua aplicação Web, aconselho a escolher o Node.js. Além do JavaScript ser a linguagem mais utilizada no front-end, principalmente em aplicações Web, utilizar um novo recurso oferecido pelo Node é algo bem avaliado.

O recurso em questão é o SSR (Server Side Rendering) com o Next.js. O Next.js é um framework que permite o desenvolvimento de interfaces (utilizando a biblioteca React) dentro do lado do back-end.

  > Mas a questão é: Por que eu escolheria fazer a renderização da minha aplicação no meu back-end?

A resposta é simples: performance. Utilizando o SSR, você garante maior velocidade e fluidez no momento de carregamento da página, oferencendo uma melhor experiência ao usuário final de sua aplicação.

Trazendo mais um exemplo de caso para você, nós temos a página inicial do iFood que é construída utilizando o Next.js. Essa decisão foi tomada levando em conta que a marca queria proporcionar a melhor experiência possível, nessa página, pois ela é a primeira noção que um usuário terá da empresa. Se por algum motivo ela não é performática o suficiente ou acaba travando, o usuário não tem uma boa experiência, consequentemente não terá uma boa opinião sobre a marca, o que é muito ruim por si só.

### Bônus: Aplicações em que o Node.js não é uma boa opção:

Nem só de vitórias vive um campeão. Apesar dos exemplos com o Node irem muito além desses citados, eu queria abrir um parêntese para uma situação em que o Node.js não seria a melhor opção.

Se a sua aplicação possuir uma computação intensiva da CPU, então o Node não é a melhor pra você. Isso se deve ao fato de que qualquer aplicação desse tipo bloqueará a capacidade de resposta dele.



Por hoje é isso que eu gostaria de passar para vocês, se pensarem em outras ocasiões em que o Node seria perfeito, por favor, abra uma Issue para conversarmos mais sobre, eu adoraria conhecer outros casos.


Made with 💜 by Brenda.