# Nova versão do Expo SDK

## Diferença entre Expo e o React Native CLI
Desde os primórdios, quando o assunto é começar uma aplicação mobile o conflito entre começar a apliação utilizando o Expo ou com o React Native CLI sem existiu, pois de um lado você tinha o React Native CLI, com a possibilidade de utilizar código nativo e do outro você tinha o Expo, com diversas funcionalidades já prontas para serem usadas, porém sem a possibilidade de utilizar o código nativo.

  > Mas, se o Expo não possui as pastas de iOS e Android contendo o código nativo, como os celulares conseguem executar o código...?

<p align="center">
  <img alt="Expo" src="https://thumbs.gfycat.com/PepperyIllfatedGerbil-size_restricted.gif"/>
</p>

Bom, pra conseguirmos rodar uma aplicação feita com o Expo, nós baixamos o aplicativo do Expo (que está no Google Play e na Apple Store) e no próprio aplicativo do Expo, nós já temos o código nativo. Com isso, o que falta é apenas o JavaScript!

O grande problema do Expo era que, apesar de já entregar funcionalidades como:
 - Geolocalização
 - Push notification
 - Câmera
 - Etc..

Ele se tornava limitado a ser utilizado em projetos que já tinham um escopo bem formado porque se eu tenho um projeto cujo eu não sei até onde ele pode chegar, a probabilidade do Expo acabar me limitando lá na frente é muito grande.

  > E nenhum de nós quer isso, certo?


## Expo Eject
Até a versão 34 da SDK do Expo, nós tinhamos apenas o ExpoKit. Da versão 34 em diante, nós temos a opção do Bare Workflow para realizar o Expo Eject. E, a partir da versão 38 do Expo SDK, o ExpoKit foi descontinuado e temos apenas a opção do Bare Workflow.

  > Okay, entendi tudo, mas... O que é o ExpoKit e o Bare Workflow?

### ExpoKit
- Era uma implementação de todo o código do Android e do iOS e não era parecido com o React Native CLI.

> Então, qual era o cenário que tinhamos: Se estavamos desenvolvendo um projeto em Expo que, por algum acaso, acabou se tornando maior do que a estrutura do Expo é capaz de desenvolver, nós faziamos um `Expo Eject` para conseguirmos desenvolver ele com o React Native CLI, porém, a estrutura gerada (ExpoKit) não se parecia nada com a CLI do RN, fazendo com que o desenvolvedor tivesse que aprender uma nova estrutura do zero.

### Bare Workflow
-  É uma forma de integração de grande parte das funcionalidades do React Native CLI sem toda a "carcaça" do Expo, dentro de um Workflow por meio do UniModules, ou seja, é possível termos todas as funcionalidades que o Expo nos apresenta dentro de um projeto com a mesma estrutura do React Native CLI.

## Relação Expo e React Native CLI:

- Tenho um projeto React Native e quero utilizar o Expo para ter as suas funcionalidades prontas:

  Aqui está a documentação para utilizar o UniModules no seu projeto React Native CLI. Um ponto interessante é que você consegue dizer exatamente quais as funcionalidades que você quer adicionar para ele baixar apenas as dependências utilizadas no seu projeto. Se o seu projeto utiliza geolocalização, porém não utiliza a câmera. Os módulos de câmera não serão baixados.

  [Expo UniModules](https://docs.expo.io/bare/installing-unimodules/)

- Tenho um projeto Expo e quero passar ele para o Bare Workflow, ou seja, quero utilizar ou apenas ter acesso ao código nativo no meu projeto Expo. Realize os seguintes passos:
  - Faça o upgrade para o Expo SDK 38:
    
    Execute no seu terminal:
    ```bash
    expo upgrade
    ```
  - Faça o expo eject


- Quero iniciar um projeto com o Bare Workflow:

  [Bare Workflow](http://github.com)

## Updates no Bare Workflow
- Essa é uma forma de atualizar seus aplicativos sem precisar passar pela Store, o famoso over-the-air updates.

```js
import React, { useEffect } from 'react';
import * as Updates from 'expo-updates';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  useEffect(() => {
    async function updateApp() {
      const { isAvailable } = await Updates.checkForupdateAsync();

      if(isAvailable) {
        await Updates.fetchUpdateAsync();
        await Updates.reloadAsync();
      }
    }

    updateApp();
  }, []);

  return (
    <View style={styles.container}>
      <Text>Texto antigo</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  }
});
```

Para utilizar a funcionalidade do over-the-air updates, sua aplicação não deve eestar rodando em "modo debug" e sim em "modo release", que é o mesmo que a forma como sua aplicação vai para a produção.

É necessário que você já tenha feito o publish de sua aplicação. Se você ainda não fez, fique tranquilo, apenas rode no seu terminal:


```bash
yarn expo publish
```

Execute no seu terminal:
- Android:

```bash
yarn android --configuration Release
```
- iOS:
```bash
yarn ios --configuration Release
```

Faça uma alteração no seu arquivo, como por exemplo o texto e execute novamente o `expo publish`. Isso irá fazer com que as suas alterações sejam passadas para o aplicativo automaticamente.

 > Certo, isso é realmente bem interessante, mas como isso é possível?

Quando fazemos o publish, nossa aplicação fica "hospedada" no servidor do Expo. Então, com esse Update, sempre que nossa aplicação é inicializada no celular do usuário, ela busca nesse servidor se há alguma atualização pra ela, caso tenha, ela faz o download dessa atualização e executa o aplicativo, sem precisar passar pela loja para fazer a atualização.

----
Made with 💜 by Brenda.