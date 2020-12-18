# GIT E GITHUB

Guia Prático para iniciantes -como eu.

# SCENES

 - [x] Você deseja criar pontos na história da produção do seu projeto.
 - [x] Você deseja verificar mudanças feitas no seu projeto.
 - [x] Você começa uma nova funcionalidade no seu projeto, sem estragar o q já foi feito.
 - [x] Você adiciona as novas funcionalidades ao seu projeto em produção.
 - [x] Você quer deletar a branch da nova funcionalidade, depois de aplicar em seu projeto. 
 - [x] Colocar o projeto na nuvem.
   
 - `git init` // inicia a linha do tempo.
 - `git add` // adiciona ou atualiza mudanças p irem para a linha do tempo
 - `git commit` // adiciona um ponto na linha do tempo.
 - `git log` // visualiza os pontos na linha do tempo / commit.
 - `git status` // informa o estado das alterações do projeto.
 - `git show` // apresenta determinado ponto na historia.
 - `git push` // para enviar suas alterações ao seu repositório remoto.
 - `BRANCH` // Branches ("ramos") são utilizados para desenvolver funcionalidades isoladas umas das outras. O branch master é o branch "padrão" quando você cria um repositório. Use outros branches para desenvolver e mescle-os (merge) ao branch master após a conclusão. 
 - `git checkout` // crie um novo branch chamado "funcionalidade_x" e selecione-o usando
git checkout -b funcionalidade_x. Retorne para o master usando git checkout master, e remova o branch da seguinte forma git branch -d funcionalidade_x. Um branch não está disponível a outros a menos que você envie o branch para seu repositório remoto
git push origin < funcionalidade_x >
 
