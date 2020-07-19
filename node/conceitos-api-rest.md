# Conceitos de API Rest:
## Como funciona?
Possui um fluxo de requisição e resposta. A requisição é feita por um cliente e a
resposta é retornada através de uma estrutura de dados, com isso o cliente recebe
os dados e processa o resultado.

## Benefícios:
Múltiplos clientes com o mesmo backend por meio de um protocolo de comunicação
padronizado, utilizando a mesma estrutura(JSON) para web/mobile/API pública.

## Métodos HTTP:
As  rotas utilizadam métodos HTTP como GET, POST, PUT, DELETE. Não são os únicos,
mas são os mais usados.
 - GET - Utilizado para listar dados;
 - POST - Utilizado para criar dados;
 - PUT - Utilizado para atualizar dados;
 - DELETE - Utilizado para deletar dados;

## HTTP Code:
Toda resposta que o nosso backend retorna tem um possui HTTP Code. É um código
de 3 dígitos que sinaliza o tipo de resposta que foi retornado.

| Code     | Significado   | Exemplo                            |
| ---------|:--------------| :----------------------------------|
| 1xx      | Informacional |                                    |
| 2xx      | Sucess        | 200: Sucess, 201: Created          |
| 3xx      | Redirection   | 301: Moved Permanently, 302: Moved |
| 4xx      | Client Error  | 400: Bad Request, 404: Not Found   |
| 5xx      | Server Error  | 500: Internal Server Error         |

## Parâmetros:
- Query Params: filtros e paginação;
- Request Body: conteúdo na hora de criar ou editar um recurso (JSON);
- Route Params: identificar recursos;
> Mais utilizado quando queremos selecionar um dado para atualiza-lo ou deleta-lo.

## Middleware:
Interceptador de requisições que interrompe totalmente a requisição ou altera
dados da requisição.
  - Todo o express é baseado em middleware.

 - Exemplo de Middleware:
```js
/*
* Esse middleware recebe um id da rota e faz uma verificação se ele é um id
* válido, caso ele seja um id válido, ele executa a função next(), continuando
* o fluxo normal da aplicação. Caso ele não seja, ele já retorna o erro.
*/

function validadeProjectId(request, response, next){
  // Recebe o id da rota:
  const { id } = request.params;

  // Faz a verificação se o id é válido:
  if(!isUuid(id)) {
    // Retorna o erro caso não seja um id válido:
    return (response.status(400).json({ error: 'Invalid ID. (Middleware)' }));
  }

  // Chama a função next() continuando o fluxo da aplicação.
  return next();

}
```

Chamando um middleware na sua API:
```js
app.use('/projects/:id', validadeProjectId);
```

