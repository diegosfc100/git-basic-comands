<h1 align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/1280px-Git-logo.svg.png" alt="Logo-Netflix" width="30%"/><br>
    O básico do GIT para sobreviver.
</h1>

<details>
<summary>
  <strong>🔍 Sumário</strong>
</summary>

>
> *[🚀 > Criando um projeto.](#1)*\
> *[🚀 > Conferindo o status do repositório.](#2)*\
> *[🚀 > Fazendo modificações.](#3)*\
> *[🚀 > Adicionando modificações ao stage.](#4)*\
> *[🚀 > Colocando em stage e fazendo commits.](#5)*\
> *[🚀 > Fazendo commit das modificações.](#6)*\
> *[🚀 > Modificações, não arquivos.](#7)*\
> *[🚀 > Histórico.](#8)*

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

```html
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

> Quando você usou o comando **git commit** anteriormente para fazer commit da primeira versão do hello.html para o repositório, você incluiu a flag **-m** que permite um comentário na linha de comando. O comando de commit permite edição interativa de comentários para o commit. Agora, vamos ver como isso funciona.

> Se você omitir a flag -m da linha de comando, o git vai abrir o editor da sua escolha, a partir dessa lista (em ordem de prioridade):

 Variável de ambiente GIT_EDITOR ;</br>
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


#### Conferindo o status

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
<hr>

<div id="7"></div>

## 🚀 Modificações, não arquivos

> Entender que o git trabalha com as modificações, não com os arquivos. A maioria dos sistemas de controle de versão trabalham com arquivos. Você adiciona o arquivo no controle de código e o sistema acompanha as mudanças a partir daquele momento. O Git se concentra nas mudanças de um arquivo, não no arquivo em si. Um comando git add file não fala para o git adicionar o arquivo no repositório, mas para perceber o atual estado do arquivo para que ele seja parte de um commit depois.


#### Primeira mudança: Adicionando tags padrão de páginas

> Mude a página “Hello, World” de maneira que ela passe a ter as tags padrão < html > e < body >.

```html
<html>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

#### Adicione essa modificação

> Agora adicione essa modificação para o stage do git.

```sh
git add hello.html
```

#### Segunda mudança: Adicione os headers do HTML

> Agora adicione os headers (< head > section) na página “Hello, World”.

```html
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

#### Confira o status atual

```sh
git status
```
Você verá …

```sh
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hello.html
#
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#   modified:   hello.html
#
```
> Note que o arquivo hello.html está listado duas vezes no status. A primeira mudança (a adição das tags padrão) está no stage e pronta para um commit. A segunda mudança (adição dos headers) não está no stage. Se você fizesse um commit agora, os headers não teriam sido salvos no repositório.

#### Commit

> Faça um commit das mudanças que estão no stage (as tags padrão) e então confira novamente o status.

```sh
git commit -m "Added standard HTML page tags"
git status
```

Você verá …

```sh

$ git commit -m "Added standard HTML page tags"
[master 8c32287] Added standard HTML page tags
 1 files changed, 3 insertions(+), 1 deletions(-)
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

> O comando status diz que o arquivo hello.html tem modificações não gravadas, mas não está mais em buffer.

#### Adicionando a segunda modificação

> Adicione a segunda modificação ao stage, depois execute o comando git status.

```sh
git add .
git status 
```

> Nota: O diretório atual (‘.’) vai ser nosso arquivo a adicionar. Essa é a maneira mais conveniente de adicionar todas as mudanças dos arquivos do diretório atual e suas pastas. Mas como ele adiciona tudo, é uma boa ideia conferir o status antes de fazer um add ., para ter certeza que você não adicione nenhum arquivo que não deveria ser adicionado.

> Eu queria que você visse o truque do “add .”, mas nós vamos continuar adicionando os arquivos explicitamente no futuro, por via das dúvidas.

Você verá …

```sh
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hello.html
#
```

> A segunda modificação está no stage e pronta para um commit.

#### Faça um commit da segunda mudança

```sh
git commit -m "Added HTML header"
```
<hr>

<div id="8"></div>

## 🚀 Histórico

> Conseguir uma lista das modificações feitas é uma função do comando **git log**.

```sh
git log
```

Você verá...

```sh
$ git log
commit fa3c1411aa09441695a9e645d4371e8d749da1dc
Author: Alexander Shvets <alex@githowto.com>
Date:   Wed Mar 9 10:27:54 2011 -0500

    Added HTML header

commit 8c3228730ed03116815a5cc682e8105e7d981928
Author: Alexander Shvets <alex@githowto.com>
Date:   Wed Mar 9 10:27:54 2011 -0500

    Added standard HTML page tags

commit 43628f779cb333dd30d78186499f93638107f70b
Author: Alexander Shvets <alex@githowto.com>
Date:   Wed Mar 9 10:27:54 2011 -0500

    Added h1 tag

commit 911e8c91caeab8d30ad16d56746cbd6eef72dc4c
Author: Alexander Shvets <alex@githowto.com>
Date:   Wed Mar 9 10:27:54 2011 -0500

    First Commit
```

> Aqui está uma lista de todos os quatro commits do repositório, que nós fizemos até agora.


#### Histórico em uma linha

> Você controla completamente o que o log mostra. Eu gosto do formato de linha única.

```sh
git log --pretty=oneline
```

Você verá …

```sh
$ git log --pretty=oneline
fa3c1411aa09441695a9e645d4371e8d749da1dc Added HTML header
8c3228730ed03116815a5cc682e8105e7d981928 Added standard HTML page tags
43628f779cb333dd30d78186499f93638107f70b Added h1 tag
911e8c91caeab8d30ad16d56746cbd6eef72dc4c First Commit
```

#### Controlando a exibição de entradas

> Existem muitas opções para escolher quais entradas aparecem no log. Brinque um pouco com os parâmetros a seguir:

```sh
git log --pretty=oneline --max-count=2
git log --pretty=oneline --since='5 minutes ago'
git log --pretty=oneline --until='5 minutes ago'
git log --pretty=oneline --author=<your name>
git log --pretty=oneline --all
```

> Detalhes são fornecidos nas instruções do git-log.

#### Ficando chique

> Isso é como eu faço para rever as modificações feitas na última semana. Eu adiciono --author=alex se eu quero ver apenas as modificações que eu fiz.

```sh
git log --all --pretty=format:"%h %cd %s (%an)" --since='7 days ago'
```

#### O melhor formato do log

> Com o tempo, eu descobri que o seguinte formato é o mais adequado.

```sh
git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
```

Ele fica assim:

```sh
$ git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
* fa3c141 2011-03-09 | Added HTML header (HEAD, master) [Alexander Shvets]
* 8c32287 2011-03-09 | Added standard HTML page tags [Alexander Shvets]
* 43628f7 2011-03-09 | Added h1 tag [Alexander Shvets]
* 911e8c9 2011-03-09 | First Commit [Alexander Shvets]
```

> Vamos olhar os detalhes:

  - --pretty="..." define o formato da saída
  - %h é o hash abreviado do commit
  -  %d mostra decorações do commit (ex.: head de branches ou tags)
  -  %ad é a data do commit
  -  %s é o comentário
  -  %an é o nome do autor =
  -  --graph fala para o git mostrar a árvore de commits no formato de um gráfico de ASCII
  -  --date=short mantém o formato de data pequeno e simples

> Então, toda vez que você quiser ver um log, você terá que digitar muito. Felizmente, nós aprenderemos sobre aliases na próxima lição.

#### Outras ferramentas

> Ambos gitx (para Mac) e gitk (para qualquer plataforma) ajudam a explorar o histórico.

