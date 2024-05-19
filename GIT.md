# About-Git

## Git Rebase

Este comando serve essencialmente para puxar alterações de uma branch para outra, usado normalmente para **puxar** informações da **main/master**, para outras branchs para manter a outra branch atualizada, mais ou menos assim:<br>
![Sobre o git rebase](./imgs/git-rebase.png)
Pode-se ver que a branch Feature estava desatualizada em relação a branch main, com o git rebase, podemos colocar a branch Feature, no último commit realizado.

### Comando

`git rebase <base>`<br>
Considerando que estamos na branch main/master, fariamos o seguintes passos:

1. `git checkout Feature`
2. `git rebase main/master`

## Git Checkout

Este comando serve para mudarmos de branch

### Comando

`git checkout outra-branch`<br>

> - Também podemos passar o parâmetro `-b`, desta forma, iremos criar uma nova branch com um novo nome: `git branch -b nova-branch`
> - Outro parâmetro que podemos passar é o `-d` ou `-D`, desta forma, iremos a branch que possuir aquele nome: `git branch -d branch-deletar` ou `git branch -D branch-deletar`

## Git Branch

Este comando serve para listar as branchs que temos no nosso projeto local

### Comando

`git branch`<br>

> Também podemos passar o parâmetro `-a`, para listar todas as branchs do nosso repositório remoto, ficando da seguinte forma: `git branch -a`
