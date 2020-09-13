# Populando a sua base de dados utilizando o Knex

Há alguns dias atrás um colega me pediu ajuda com uma aplicação que ele estava fazendo e eu me propus a ajudar ele com isso.

Na ocasião a biblioteca Knex havia sido a escolhida para fazer a parte do banco de dados de da API e um dos requisitos dela era consumir a API pública do Pokemons.

  >Caso seja de seu interesse, você pode conferir essa API do Pokemon bem aqui: https://pokeapi.co/api/v2/

E com isso surgiu uma dúvida: Como nós poderíamos popular o nosso banco de dados com os dados da API do Pokemon?

Não me levem a mal, em casos normais, não haveria necessidade de pegar uns dados de uma API e colocar na minha, não é performático e muito menos algo "sensato". É um retrabalho que não precisamos ter, certo?

  > Certo, mas não era o que queríamos, queríamos esses dados nas NOSSAS mãos.

Então, eu me lembrei de quando eu estava estudando o query builder Knex (em algum outro momento eu posso comentar sobre as diferenças entre query builders como o Knex e ORMs como Sequelize ou TypeORM) e que havia uma interessantes que poderíamos fazer com ele: criar dados na nossa base de dados de forma automática utilizando o **seeds**

Claro que o seeds não foi criado só pra você popular a sua base de dados com os dados de outras APIs, mas em casos quem que você trabalha em um projeto com outros devs cujo o banco de dados não está na núvem ainda, criar os dados toda vez que o projeto mudar de máquina se torna algo cansativo. Colocar dados fakes na sua base de dados apenas para o desenvolvimento da aplicação é um dos casos para o uso de seeds. 