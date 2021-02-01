# O básico do Git para sobreviver.
<details>
<summary>
  <strong>🔍 Sumário</strong>
</summary>

>
> *[🚀 > Criando um projeto.](#1)*\
> *[🚀 > Conferindo o status do repositório.](#2)*\
> *[🚀 > Fazendo modificações.](#3)*\
> *[🚀 > Adicionando modificações ao stage.](#4)*\
> *[🚀 > Colocando em stage e fazendo commits.](#5)*

>
</details>
<hr>

<div id="1"></div>

## 🚀 Criando um projeto


```sh
mkdir hello
cd hello
touch hello.html
```
#### Crie uma página de "Hello, World"

 > Crie um diretório vazio chamado "pasta". Então, crie um arquivo hello.html dentro dele com o conteúdo indicado abaixo.

```sh
mkdir hello
cd hello
touch hello.html
```


#### Crie um repositório

>Então você tem um diretório que tem um arquivo. Execute o comando **git init** para criar um repositório do git a partir desse diretório.

```sh
git init
```

resultado:
```sh
$ git init
Initialized empty Git repository in /Users/alex/Documents/Presentations/githowto/auto/hello/.git/
```

#### Adicione a página ao repositório

> Agora vamos adicionar a página “Hello, World” ao repositório com **git add**

```sh
git add hello.html
git commit -m "First Commit"
```

você verá …
```sh
$ git add hello.html
$ git commit -m "First Commit"
[master (root-commit) 911e8c9] First Commit
 1 files changed, 1 insertions(+), 0 deletions(-)
 create mode 100644 hello.html
```
<hr>

<div id="2"></div>

## 🚀 Conferindo o Status do Repositório


#### Confira o status do repositório

> Use o comando **git status** para checar o estado atual do repositório. Execute:
```sh
git status
```

resultado:
```
$ git status
# On branch master
nothing to commit (working directory clean)
```

> O comando confere o status e reporta que não existe nada para fazer um commit, o que quer dizer que o repositório está com o atual estado do diretório de trabalho e não existem modificações a serem gravadas.

>Nós usaremos o **git status** para continuar monitorando os estados de ambos o diretório de trabalho e o repositório.
<hr>

<div id="3"></div>

## 🚀 Fazendo modificações

#### Modificar a página de “Hello, World”

> Vamos adicionar algumas tags HTML para a nossa saudação. Modifique os conteúdos do arquivo para:

```sh
<h1>Hello, World!</h1>
```

#### Conferindo o status

> Confira o status do diretório de trabalho com **git status**. Execute:

```
git status
```

resultado:
```
$ git status
# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#   modified:   hello.html
#
no changes added to commit (use "git add" and/or "git commit -a")
```

>O primeiro aspecto importante aqui é que o git sabe que o arquivo hello.html foi modificado, mas essas modificações ainda não sofreram commit para o repositório.

>Outro aspecto é que a mensagem de status oferece dicas sobre o que fazer em seguida. Se você quiser adicionar essas modificações para o repositório, use **git add**. Para desfazer as modificações use **git checkout**.
<hr>

<div id="4"></div>

## 🚀 Adicionando modificações ao stage

#### Adicionando modificações

>Agora mande o git adicionar as modificações ao stage com **git add**. Confira o status com **git status**. Execute:
```sh
git add hello.html
git status
```

você verá …
```
$ git add hello.html
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hello.html
#
```

> Modificações no hello.html foram adicionadas ao stage. Isso quer dizer que o git sabe da modificação, mas não é permanente no repositório. O próximo commit incluirá as modificações que estão no stage.

> Se você decidir não fazer commit da modificação, o comando **git status** vai te lembrar que você pode usar o comando **git reset** para remover essas mudanças do stage.
<hr>


<div id="5"></div>

## 🚀 Colocando em stage e fazendo commits

> Adicionar algo ao stage no git permite que você continue fazendo modificações no seu diretório de trabalho e, quando decidir que quer interagir com o controle de versão, permite que guarde as mudanças em pequenos commits.

> Pense que você editou três arquivos (a.html, b.html e c.html). Depois disso você tem que fazer commit de todas as modificações para que as mudanças em a.html e b.html sejam um único commit, enquanto as mudanças em c.html, que não são lógicamente relacionadas com as duas outras mudanças nos outros dois arquivos, sejam enviadas em um commit diferente.

Em teoria, você pode fazer o seguinte:
```sh
git add a.html
git add b.html
git commit -m "Changes for a and b"

git add c.html
git commit -m "Unrelated change to c"
```

> Separando a adição ao stage e o commit, você pode customizar o que vai em cada commit.
<hr>


<div id="6"></div>


## 🚀 Fazendo commit das modificações

#### Fazendo commit das modificações

> Quando você usou o comando **git commit** anteriormente para fazer commit da primeira versão do hello.html para o repositório, você incluiu a flag **-m** que permite um comentário na linha de comando. O comando de commit permite edição interativa de comentários para o commit. Agora, vamos ver como isso funciona.

> Se você omitir a flag -m da linha de comando, o git vai abrir o editor da sua escolha, a partir dessa lista (em ordem de prioridade):

 Variável de ambiente GIT_EDITOR ;</>
 Definição de configuração core.editor ;</br>
 Variável de ambiente VISUAL ;</br>
 Variável de ambiente EDITOR .</br>

Execute:
```sh
git commit
```

Resultado:

```sh
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hello.html
#
```

> Na primeira linha, escreva o comentário: “Added h1 tag”. Salve o arquivo e saia do editor (para fazer isso no editor padrão, pressione ESC e então escreva :wq e aperte Enter). 

Resultado:
```sh
git commit
Waiting for Emacs...
[master 569aa96] Added h1 tag
 1 files changed, 1 insertions(+), 1 deletions(-)
```

> "Waiting for Emacs…" é obtido pelo programa emacsclient estar enviando o arquivo para um programa emacs em execução e esperando para ele ser fechado. O resto das informações é a mensagem padrão de commits.


## Conferindo o status

> No final, vamos conferir o status.

Execute:

```
git status
```

Resultado:

```
$ git status
# On branch master
nothing to commit (working directory clean)
```

> O diretório de trabalho está limpo, você pode continuar trabalhando.