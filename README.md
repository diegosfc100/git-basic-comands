# GIT Commands to Live By.

<details>
<summary>
  <strong>🔍 Sumário</strong>
</summary>

>
> *[🚀 Como inicializar um repositório](#1)*\
> *[🚀 Como adicionar as mudanças realizadas para commit?](#2)*\
> *[🚀 Como remover as mudanças recém-adicionadas?](#3)*\
> *[🚀 Mas e agora? Como faço o commit?](#4)*\
> *[🚀 Mas perai, como eu sei o estado dos arquivos?](#5)*\
> *[🚀 Como conectar seu repositório local ao remoto?](#6)*\
> *[🚀 Conflitos entre local e remoto.](#7)*\
> *[🚀 Contribuindo com repositórios de terceiros](#8)*
>
</details>
<hr>

<div id="1"></div>

### 🚀 Como inicializar um repositório?

Entre na pasta do projeto no terminal e digite:
```sh
$ cd meu-projeto/ # lorem ipsum
$ git init
```


$ git init 
> Iniciliza o repositório na sua máquina.

$ git status
> Exibe informações sobre os estados dos arquivos.

$ git add 
> Adiciona os arquivos e/ou alterações realizadas nos arquivos.

$ git commit -m
> Envia o commit. 
> A flag -m indica que sera passado uma msg.

$ git commit -am
> Possibilita que vc adicione e commit ao msm tempo.

$ git log
> Exibe as informaçõe sobre todas os commits enviados, como autor, hora, hash do commit e etc...

$ git log --graph
> Exibe um grafico dos de alterações.

$ git shortlog
> Mostra o nome dos autores seus respectivos commits.

$ git shortlog -sn
> Mostra quantos commits cada autor realizou.

$ git show *HASH*
> Exibe as informações sobre um determinado commit, exibindo o que foi adcionado.

$ git diff
> Exibe as alterações realizadas nos arquivos antes de serem versionadas.

$  git diff < branch origem > < branch destino > 
> Pré-visualizar alterações antes de fazer o merge.

$ git checkout "Nome do arquivo"
> Desfaz as alterações antes que o arquivo seja adicionado.

$ git reset HEAD "Name do arquivo"
> Esse comando serve para remover um arquivo da fila de staged... ou seja, ele volta para o estado em que o arquivo ainda nao foi adcionado.

$ git reset --soft
> Mata o commit e volta para a fila de staged... ou seja, o commit vai ser apagado, mas o arquivo ira continiar pronto para ser commitado com as alteraçõe feitas. Obs: Nessa parte o aquivo ja foi adicionado mas não commitado.

$ git reset --mixed
> Deleta o commit r volta para a estado antes do staged... entao nesse caso o arquico ainda materá as alterações, mas sera preciso realizar os comando git add e git commit -m.

$ git reset --hard
> Este é o reset mais hardcore, pois ele exclui o commit e as alterações realizadas no arquivo por esse commit.

>> OBS: Para cada um dos commando reset é necessário informar o HASH da versão que vc deseja voltar, lembrando que as alteraçõe e exclusões serão realizadas em todos os commits feitos depois do commit informado.$

$ git branch
> Exibe todos os branch que vc possue naquele projeto, e coloca um * na branch que vc esta no momento.

$ git checkout -b "Name"
> Cria uma branch e muda para ela automaticamente.

$ git checkout master
> Retorna para a branch master.

$ git checkout "Name"
> Muda de branch

$ git branch -d "Name"
> Deleta uma branch

$ git merge "Name_branch"
> Junta(mescla) duas Branchs.

$ git push origin < nome da nova branch >
> Um branch não está disponível a outros a menos que você envie o branch para seu repositório remoto.

$ git pull
> Atualizar seu repositório local com a mais nova versão. 

$ git push
> O comando git push é usado para enviar conteúdo do repositório local(sua máquina) para um repositório remoto. "Push" é como os commits do repositório local são enviados a um repositório remoto. É a contraparte para git fetch: buscar (fetch) baixa commits para ramificações locais, e push envia commits para ramificações remotas.

$ git tag
> é recomendado criar rótulos para releases de software. Este é um conhecido conceito, que também existe no SVN. Você pode criar um novo rótulo chamado 1.0.0 executando o comando git tag 1.0.0 0123456789, essa sequencia de nuúmeors representa os 10 primeiros caracteres do id de commit que você quer referenciar com seu rótulo. Você pode obter o id de commit com git log.

$ git checkout -- < arquivo >
> No caso de você ter feito algo errado você pode sobrescrever as alterações locais, isto substitui as alterações na sua árvore de trabalho com o conteúdo maisrecente no HEAD. Alterações já adicionadas ao index, bem como novos arquivos serão mantidos. 

$ git fetch origin
$ git reset --hard origin/master 
> Se ao invés disso você deseja remover todas as alterações e commits locais, recupere o histórico mais recente do servidor e aponte para seu branch master local desta forma.

$ gitk
> Interface gráfica padrão.

$ git config color.ui true
> Usar saídas do git coloridas.

$ git config format.pretty oneline
> Exibir log em apenas uma linha por commit.

$ git add -i
> Fazer inclusões interativas.

