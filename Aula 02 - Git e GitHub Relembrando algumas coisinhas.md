### Aula 02 - Git e GitHub: Relembrando algumas coisinhas



-Criamos umnovo Repositório
-Deixamos esse repositório como Público para que outras pessoas possam ver e compartilhar info
-Podemos acrescentar um arquivo README que funcionará como noss página inicial do Repositório, onde nós pódemos colocar algumas informações adicionais, comomlinks úteis, detalhes importantes sobre o projeto e algo mais ou seja o que representa esse Repositório para a gentes,
onde podemos colocar tudo o que acharmos relevante ao projeto.

Podemos também habilitar o GItignore que é uma área que quando trabalhamos em um projeto de uma determinada Tecnologia para que o Git ignore alguns arquivos de Build que não necessáriamente essenciais para que voê versione (realize o versionamento).

Choose a license - relativo as licenças necessárias se for aplicável...

Algumas dicas do GitHub para algumas ações:

crie um novo repositório na linha de comando:

echo "# dio-desafio-github-primeiro-repositorio" >> README.md 
git init 
git add README.md 
git commit -m "first commit" 
git branch -M main 
git remote add origin https://github.com/ sergioluizalmeida/dio-desafio-github-primeiro-repositorio.git
 git push -u origin main

*****

envie um repositório existente a partir da linha de comando:

git remote add origin https://github.com/sergioluizalmeida/dio-desafio-github-primeiro-repositorio.git
 git branch -M main 
git push -u origin main

******

No botão "Code" temos todas as opções para poder CLONAR esse repositório na nossa máquina (Git Local): Ex. Info de HTTPS, SH, GitHub CLI
Essa área nos permite realizar ações para trazer informações do Git Remoto para o noss Git Local.

Na minha área do Github podemos usar o GitHub para editar nosso arquivos diretamente sem estar usando nosso git Local, apenas clicando o 
lapizinho (Lápis) de edição com o arquivo que desejamos editar selecionado.

Interessante observar é que esse arquivo README.md tem a extensão .md  ou seja diz que esse arquivo é do tipo Mardown que é a linguagem
de formatação ou marcação que a gente utilizapara confeccionar os arquivos para versionamento.

Para saber mais sobre Markdown acesse: markdownguide.org/basic-syntax

No Markdown colocando a informação conforme segue abaixo quando colocamos uma referência entre conchetes, estamos
indicando que o que vem após será um link como o exemplo que segue abaixo:

# Desafio de Projeto sobre Git/GitHub da DIO
Repositório criado para Desafio de Projeto


## Links Úteis:
[Sintaxe Básica do Markdown](https://www.markdown.org/basic-syntax)

Para Salvar ou efetivar essas alterações devemos clicar no Botão: COMMIT CHANGES, para que a inclusão das informações seja efetivadas
na branch principal (mais branch).

AGORA COMO FAZEMOS PARA BAIXAR ESSE REPOSITÓRIO NA MINHA MÁQUINA (GIT LOCAL)

Para isso cliqie no Botão CODE e clona o caminho HTTPS do Repositório Remoto

Depois fe copiar a URL devemos abrir a pasta on de deverá ser clonado o Repositótio e ativar o Git Bash (clicando com botão direito do mouse
dentro da pasta e depois clicar em GIT BASH HERE depois de aberto o Git Bash para iniciar o Clone digite:

git clone https://github.com/sergioluizalmeida/dio-desafio-github-primeiro-repositorio.git <enter>

Após isso ele vai falar que esta clonando o repositório remoto e mostrar a enumeração dos objetos, contagem de objetos, compressão dos objetos, Total do conteúdo dos objetos e por fim diz que 100% dos objetos doram recebidos ex.: 6/6

Após isso se voce for na pasta que foi indicado para receber o clone, voce poderá verificar que foi criada uma pasta .GIT

Para enviar as alterações feitas no repositório local para o remoto devemos:
Primeiro digite:

git add (.) ou (*) ou (-A) para selecionar todos os arquivos

Digite :

git add . <enter>

git status <enter>

trems como retorno:

$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   "Introdu\303\247\303\243o ao Git e ao GitHub/Anota\303\247\303\265es.txt"

Isso acontece pois adicionamos informações ou pastas ao nosso repositório, e nos mostra que eles estão prontos para serrem commitados
e o Git informa também que ele entendeu que as alterações feitas estarão habilitadas para fazerem parte do nosso controle de versão.
Lembrando que essas alterações estão atualmente em nosso repositório local (na nossa máquina) devemos empurrar os arquivos para o Repositório Remoto.

Agora devemos fazer o seguinte no Git Local:

git commit -m "Introdução das anotações do curos Git/GitHub" <enter>

Lembrando que colocar as informações (que estão entre aspas ("") é muito importante onde devem ser colocados comentários coerentes de acordo
com o conteúdo das alteraçoes incluidas no arquivo para versionamento).

Retornando:

[main 9bb4fb2] Inclusão das anotações do curso Git / GitHub
 1 file changed, 3 insertions(+)
 create mode 100644 "Introdu\303\247\303\243o ao Git e ao GitHub/Anota\303\247\303\265es.txt"

O retorno acima diz que foi commitado com sucesso; para verificar dê um git status comoa seguir:

git status <enter>

retorna:

On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

O status acima diz que ele informa que tem 1 arquivo aqui já commitado e se voce quiser empurrar ele para o Repositório Remoto voce precisa aplicar o mando PUSH

Para empurrar o arquivo digite: 

git push origin main <enter>

retorna:

Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 472 bytes | 472.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/sergioluizalmeida/dio-desafio-github-primeiro-repositorio.git
   ec2d1de..9bb4fb2  main -> main

A informação acima diz que foram enviados todos os arquivos que estão commitados para a nuvem

Para verificar no Repositório Remoto:

Vá para o Repositório Remoto e dê um F5 para atualizar e verifique que o arquivo e a pasta que criamos no nosso Repositório Local
já foram atualizados no Repositório Remoto.