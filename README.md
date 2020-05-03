# Git Flow   :computer::gem:

O git flow é uma extensão de alto nível do git que tem como objetivo abstrair alguns comandos.

## Instalação

### Windows (Cygwin):

> $ wget -q -O - --no-check-certificate https://raw.github.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh install stable | bash

### macOS

### Homebrew:

> $ brew install git-flow-avh 

### Macports:

> $ port install git-flow-avh

### Linux:

> $ apt-get install git-flow 

## Inicialização

Para começar usando o git flow, vá até o repositório que você deseja usar e faça `git flow init`. Esse repositório pode também ser um existente, se ele já existir ele não vai modificar o diretório .git antigo. :thumbsup:

O git flow vai fazer algumas perguntas sobre o repositório. Primeiro, se deseja modificar as branches base: *master* e *develop*. Simplesmente deixe essas opções padrão apertando *ENTER*. Em seguida ele vai perguntar se você deseja modificar as branches auxiliares. Sendo elas:

Nome da branch | Função
-------------- | -------------
*bugfix* | Consertar erros em geral
*feature* | Adicionar funcionalidades
*support* | Tarefas não relacionadas a desenvolvimento
*hotfix* | Consertar erros ou fazer ajustes rápidos em código de produção. Ex.: Documentação
*release* | Criar versões para cada vez que o sistema for para produção

## Criando uma funcionalidade

+ Para criar uma funcionalidade, o desenvolvedor precisa fazer o comando `git flow feature start NOMEFEATURE`. Onde *NOMEFEATURE* deve ser substituído pelo número da tarefa no Redmine. Usar o número da tarefa, obriga ao desenvolvedor ficar sempre atualizando o Redmine. Então as branches sempre seriam números. Caso o desenvolvedor não saiba qual branch se trata, ele se vê obrigado a ir até o Redmine. :sparkles:
+ Assim que criar uma branch o ideal é que ela seja publicada logo em seguida no repositório. O comando `git flow feature publish NOMEFEATURE` resolve o problema.
+ As *branches* de *features* são criadas a partir da *branch* *develop*.
+ Assim que você finalizar 100% uma *feature* faça `git flow feature finish NOMEFEATURE`
    + Esse comando então vai fazer o *merge* da branch especificada para a develop
    + Remove a *branch* local e remotamente
    + Muda para a *branch* *develop*
+ Finalizada a tarefa, sua branch *develop* estará atualizada com sua *feature*, então o que você precisa fazer agora é mandar as alterações para o repositório remoto
+ Antes de mandar, baixe do repositório remoto as alterações, ou seja, faça `git pull upstream develop` para poder atualizar a sua branch develop local com
qualquer coisa que os outros desenvolvedores possam ter mandado.
+ Tendo atualizado, agora você pode enviar as alterações com o comando `git push -u upstream develop`.





