# Git e Versionamento

## O que é Git?
Git é um sistema de controle de versão distribuído (versionamento), criado por Linus Torvalds em 2005. Ele é utilizado para rastrear mudanças no código fonte durante o desenvolvimento de software.

**Documentação oficial:** [https://git-scm.com/doc](https://git-scm.com/doc) (todo esse módulo foi baseado na documentação oficial do Git)

## Instalando e configurando o Git
Para instalar o Git, acesse o site oficial [https://git-scm.com/](https://git-scm.om/) e faça o download da versão compatível com o seu sistema operacional.
> A aula mostrou como instalar o Git, GitHub Desktop e extensões para o VS Code 


## Repositórios do Git
O Git armazena as informações em repositórios. Existem dois tipos de repositórios: locais e remotos.
> A aula mostrou como criar um repositório local e remoto no GitHub e como clonar um repositório remoto para o local.

`git clone <url>` - Clona um repositório remoto para o repositório local.

`git init` - Inicializa um repositório local.


## Gravando mudanças no repositório
Para gravar as mudanças no repositório, é necessário adicionar os arquivos modificados ao stage e depois fazer o commit.
> A aula mostrou como adicionar arquivos ao stage e fazer commit. **Os estágios são: untracked, modified, staged e committed.**

`git status` - Mostra o status dos arquivos no repositório.

`git add <arquivo>` - Adiciona o arquivo ao stage.

## Git diff e commit
O comando `git diff` é utilizado para visualizar as mudanças feitas nos arquivos. O comando `git commit` é utilizado para gravar as mudanças no repositório.
> A aula mostrou como usar o comando `git diff` e `git commit`.

`git diff` - Mostra as mudanças feitas nos arquivos.

`git commit -m "mensagem"` - Grava as mudanças no repositório.

## Git log e restore

O comando `git log` é utilizado para visualizar o histórico de commits. O comando `git restore` é utilizado para restaurar arquivos.

`git log` - Mostra o histórico de commits.

`git restore --staged <arquivo>` - Remove o arquivo do stage e volta para o estado de modified.

`git restore <arquivo>` - Restaura o arquivo para o estado do último commit.

## Repositórios remotos

Os repositórios remotos são utilizados para compartilhar o código com outras pessoas. O GitHub é uma plataforma que permite hospedar repositórios remotos.

`git remote add origin <url>` - Adiciona um repositório remoto.

`git push origin <branch>` - Envia as mudanças para o repositório remoto.

`git fetch origin <branch>` - Busca as mudanças do repositório remoto. As mudanças não são aplicadas no repositório local. As mudanças são aplicadas com o comando `git merge` e `git pull`.

`git pull origin <branch>` - Atualiza o repositório local com as mudanças do repositório remoto.


## GitHub

O GitHub é uma plataforma que permite hospedar repositórios remotos. Ele é utilizado por desenvolvedores para compartilhar código e colaborar em projetos.
> A aula foi muito rasa sobre o GitHub. Apenas apresentou a plataforma e mostrou como criar um repositório remoto.

## Git branch

O HEAD é um ponteiro que aponta para o commit atual. O branch é um ponteiro que aponta para um commit. O branch **master** é o branch principal do repositório.

`git branch` - Mostra os branches do repositório.

`git branch <branch>` - Cria um novo branch.

`git checkout <branch>` - Muda para o branch especificado.

`git branch -d <branch>` - Deleta o branch especificado.


## Merging branches

O comando `git merge` é utilizado para unir os branches.

`git merge <branch>` - Une o branch especificado ao branch atual. 

O comando merge pode gerar conflitos. Para resolver os conflitos, é necessário editar os arquivos manualmente e depois fazer o commit.