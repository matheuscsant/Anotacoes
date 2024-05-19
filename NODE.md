# Manual de uso do NPM

## Sumário

1. [Passos para inicializar um projeto npm](#passos-para-inicializar-um-projeto-npm)
2. [O que é o _package.json_?](#o-que-é-o-packagejson)
   1. [Campos dentro do _package.json_](#campos-dentro-do-packagejson)
3. [O que é o _package-lock.json_?](#o-que-é-o-package-lockjson)
4. [O que é a pasta _node_modules_?](#o-que-é-a-pasta-node_modules)
5. [Instalando pacotes no projeto?](#instalando-pacotes-no-projeto)
6. [Removendo pacotes no projeto?](#removendo-pacotes-no-projeto)
7. [Instalando pacotes de desenvolvimento no projeto?](#instalando-pacotes-de-desenvolvimento-no-projeto)
8. [Removendo pacotes de desenvolvimento no projeto?](#removendo-pacotes-de-desenvolvimento-no-projeto)
9. [Comandos úteis](#comandos-úteis)
   1. [`node ./app.js`](#node-appjs)

## Passos para inicializar um projeto npm

1. Utilizar o comando: `npm init`
2. Ira aparecer algumas informações que devem ser preenchidas, tais como: nome do projeto, versão, descrição, repositório, scripts, comando de teste, entre outros...
3. Ao final das opções o npm vai mostrar como o arquivo `package.json` vai ficar, basta confirmar e teremos nosso projeto npm inicializado
   > Obs: No caso de todas as opções forem sim, podemos utilizar o comando `npm init -y`, que o npm vai criar um projeto padrão. <br>
   > Também podemos preencher o arquivo na mão após ele ser criado.

## O que é o _package.json_?

Se trata do arquivo que descreve o que tem instalado no nosso repositório e suas metas informações (nome, versão, descrição, scripts, etc...). Quais pacotes estão instalados neste repositório, quais são de produção e quais são de desenvolvimento. Semelhante ao arquivo `pubspec.yaml` de projetos Flutter ou ao `pom.xml` de projeto Maven.
<br>
Caso tentemos instalar um pacote em um projeto sem termos o `package.json`, não será possível fazer a instalação.
<br>
Também podemos perceber que no nosso _package.json_, ao adicionar novos pacotes, eles entram naturalmente dentro da chave _dependencies_, mas podemos também ter pacotes que serão exclusivamente utilizados para desenvolvimento, assim, adicionamos esses pacotes dentro da chave _devDependecies_, ao realizar o build, esses pacotes não irão para a aplicação final.
<br>
**Obs**: Sempre que termos alterações manuais no _package.json_ ou baixar o projeto de um repositório, devemos utilizar o comando `npm install` ou `npm i`, para puxar os pacotes do projeto. Funciona do mesmo jeito, caso tenhamos pacotes instalados que não estejam sendo utilizados, eles serão removidos.

### Campos dentro do _package.json_

1. **name**: Nome do projeto
2. **version**: Versão do projeto
3. **description**: Descrição do projeto
4. **main**: Define o ponto de entrada do pacote, quando importar este pacote para uma aplicação, é onde a aplicação irá procurar pelo module exports
5. **scripts**: Uma forma armazenar scripts no projeto, que posteriormente podem ser usados para algo, utilizando `npm run test`. (Normalmente em projetos _react/node_, virá um script chamado _start_, que é um atalho para inicializar o servidor)
6. **keyword**: Palavras chaves para identificação do projeto
7. **author**: Autor responsável pelo projeto
8. **licence**: Licença padrão

## O que é o _package-lock.json_?

Nada mais é do que um arquivo de log, que mapeia o que estamos instalando e algumas meta-informações dos pacotes, semelhante ao `pubspec.lock` de projetos Flutter

## O que é a pasta _node_modules_?

Se trata da pasta onde estarão instalados os pacotes do nosso projeto, por exemplo, é nesta pasta que se encontra os pacotes do react e do next.

## Instalando pacotes no projeto

Para isso devemos utilizar o comando `npm install pacote` ou `npm i pacote`, aqui podemos instalar qualquer pacote, como por exemplo, o react e o next, ficaria desta forma: `npm install react` ou `npm i react` e `npm install next` ou `npm i next`.

## Removendo pacotes no projeto

Para isso devemos utilizar o comando `npm remove pacote` ou `npm r pacote`, anteriormente instalamos o react e o next, para remover, basta usar os comandos dessa forma: `npm remove react` ou `npm r react` e `npm remove next` ou `npm i next`.

## Instalando pacotes de desenvolvimento no projeto

Para isso devemos utilizar o comando `npm install pacote --save-dev` ou `npm i pacote -D`, aqui podemos instalar qualquer pacote, como por exemplo, o typescript, ficaria desta forma: `npm install typescript --save-dev` ou `npm i typescript -D`.

## Removendo pacotes de desenvolvimento no projeto

Para isso devemos utilizar o comando `npm remove pacote` ou `npm r pacote`, anteriormente instalamos o typescript, para remover, basta usar os comandos dessa forma: `npm remove typescript --save-dev` e `npm remove typescript -D`.

## Comandos úteis

|     Comando     | Descrição                                                                                                                                              |
| :-------------: | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `node ./app.js` | Serve para rodar um projeto node, desta forma mostramos ao node por onde começar, onde está o "main" do projeto, de lá ele começará a rodar o projeto. |
