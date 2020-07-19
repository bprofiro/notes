# Conceitos React Native?
## O que é o React Native?
É uma versão do React para o desenvolvimento mobile. Ele é multiplataforma,
podendo rodar em Android e iOS.
  > Uma das funcionalidades do React Native é a possibilidade de manipular
  > cada plataforma de forma diferente.

## Arquitetura
O JavaScript como conhecemos é transpilado para o Metro Bundler (equivalente ao
Webpack), depois passado para o Bundle que vai ler o nosso código e, ao passar
pela "bridge", os componentes de interface que precisam ser transpilado para
código nativo, são transpilados.

## Sintaxe
A sintaxe é igual a web, com a diferença de que não utilizamos HTML e sim os
components próprios do RN. Os estilos são aplicados sem classes e ID's e não
erança de estilos.

## Código Nativo
Como não utilizamos "web", como no Ionic e sim recursos nativos, o código nativo
do Android e iOS precisa estar presente na nossa aplicação.

## Expo
SDK com um conjunto de funcionalidades prontas para usar, com ele não há a
necessidade de configurar um emulador.
 #### - Problemas:
   - O Expo tem uma limitação do controle de código nativo, então sempre que
   vamos mexer com código nativo, o Expo não poderá ser usado. Várias bibliotecas
   não têm suporte para o Expo, mas o Expo liberou suas funcionalidades para serem
   utilizadas em aplicações sem ele.

## Conexão com API  pelo axios
  - iOS com emulador: localhost
  - iOS com físico: IP da máquina
  - Android com emulador: `adb reverse tcp:3333 tcp:3333`
  > Rodar no terminal
  > Com isso, a aplicação consegue usar o localhost ou o IP
  - Android com dispositivo físico: IP da máquina.