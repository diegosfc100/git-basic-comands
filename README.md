# O básico do Git para sobreviver.
<details>
<summary>
  <strong>🔍 Sumário</strong>
</summary>

>
> *[🚀 Criando um projeto.](#1)*\
> *[🚀 Criando um projeto.](#1)*

>
</details>
<hr>

<div id="1"></div>

## 🚀 Criando um projeto?


```sh
mkdir hello
cd hello
touch hello.html
```
### 01. Crie uma página de "Hello, World"

 > Crie um diretório vazio chamado "pasta". Então, crie um arquivo hello.html dentro dele com o conteúdo indicado abaixo. Execute:

```sh
mkdir hello
cd hello
touch hello.html
```


### 02. Crie um repositório

>Então você tem um diretório que tem um arquivo. Execute o comando **git init** para criar um repositório do git a partir desse diretório.
Execute:
```sh
git init
```

Resultado:
```sh
$ git init
Initialized empty Git repository in /Users/alex/Documents/Presentations/githowto/auto/hello/.git/
```

### 03. Adicione a página ao repositório

> Agora vamos adicionar a página “Hello, World” ao repositório com **git add**

Execute:
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




