# O básico do Git para sobreviver.
<details>
<summary>
  <strong>🔍 Sumário</strong>
</summary>

>
> *[🚀 > Criando um projeto.](#1)*\
> *[🚀 > Conferindo o status do repositório.](#2)*

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
#### 01. Crie uma página de "Hello, World"

 > Crie um diretório vazio chamado "pasta". Então, crie um arquivo hello.html dentro dele com o conteúdo indicado abaixo.

```sh
mkdir hello
cd hello
touch hello.html
```


#### 02. Crie um repositório

>Então você tem um diretório que tem um arquivo. Execute o comando **git init** para criar um repositório do git a partir desse diretório.

```sh
git init
```

Resultado:
```sh
$ git init
Initialized empty Git repository in /Users/alex/Documents/Presentations/githowto/auto/hello/.git/
```

#### 03. Adicione a página ao repositório

> Agora vamos adicionar a página “Hello, World” ao repositório com **git add**

```sh
git add hello.html
git commit -m "First Commit"
```

Você verá …
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


#### 01. Confira o status do repositório

> Use o comando **git status** para checar o estado atual do repositório. Execute:
```sh
git status
```

Resultado:
```
$ git status
# On branch master
nothing to commit (working directory clean)
```

> O comando confere o status e reporta que não existe nada para fazer um commit, o que quer dizer que o repositório está com o atual estado do diretório de trabalho e não existem modificações a serem gravadas.

>Nós usaremos o **git status** para continuar monitorando os estados de ambos o diretório de trabalho e o repositório.
