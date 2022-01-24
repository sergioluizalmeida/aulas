### Aula 08 - CICLO DE VIDA DOS ARQUIVOS NO GIT

Passo a passo no ciclo de vida

A psrtir de agora não usaremos mais os nomes: Diretórios ou Pastas e sim REPOSITÓRIO, pois o comando (git init) inicia
nosso Repositório (.git/). Essa é a Terminologia Correta.

Quando usamos o comando (git init) estamos criando um Repositório dentro do Diretório. Vamos atentar para uso dessa Terminologia.

O Conceito de TRACKED e UNTRACKED



				------------------- T R A C K E D ---------------------
	Untracked		Unmodified		Modified		Staged
	
	   |	Adiciona arquivo --------------------------------------------------> |
	
					Edita arquivo----> |
	
								"Stage" o arquivo--> |
	
	   | <--Remove o arquivo
	
				| <-------------------------------------Commit


TRACKED - SÃO ARQUIVOS QUE SÃO RASTREADOS PELO GIT - São divididos em 3 Estágios: "Unmodified, Modified e Stage"

UNTRACKED - SÃO S ARQUIVOS AO QUAL O GIT NÃO TEM CIÊNCIA DELES (não sabe que eles existem, ou  não foram utilizados no git).

UNMODIFIED - É O ARQUIVOS QUE AINDA NÃO FOPI MODIFICADO. (Quando o arquivo é alterado ou modificado, ele passa automaticamente de
UNMODIFIED para MODIFIED.


MODIFIED - É O ARQUIVO QUE JÁ SOFREU MODIFICAÇÃO. 

STAGED - É O CONCEITO CHAVE PARA ENTENDERMOS. É ONDE OS ARQUIVOS QUE ESTÃO SE PREPARANDO PARA PODER FAZER PARTE DE UM OUTRO TIPO DE AGRUPAMENTO.

Vamos explanar melhor (entender melhr o que já fizemos)

Quando usamos o comando "git add" nos fizemos o seguinte processo, nós tinhamos um arquivo UNTRACKED (porque haviamos acabado de criar ele)
ou seja, o Git ainda não sabia da existência desse arquivo. Quando aplicamos o comando "git add", o "git add" moveu o arquivo UNTRACKED, direto para o STAGED (e essa área (staged) é onde o arquivo esta esperando alguma coisa).

Os arquivos UNMODIFIED são arquivos que estão mo Repositório do Git e que ainda não sofreram modificações. quando voce muda esse arquivo que esta UNMODIFIED ele passa automaticamente a ser MODIFIED. E como eles mudam de um estado para o outro, eles compararam os SHA1 dos
arquivos, aí ele descobre que o arquivo teve modificação.

Se a gente rodar o git add novament em um arquivo MODIFIED, esse arquivo irá para STAGED, então esse arquivo também entra nessa área
especial (STAGED) que está aguardando para entrar em ação, onde ele esta aguardando para executar uma ação, para fazer parte de outro grupo.

E se a gente tiver um arquivo UNMODIFIED sem nenhuma alteração e remover esse arquivo, ele vai para UNTRACKED novamente, onde o Git ainda 
não tem ciência desse arquivo.

UNMODIFIED e MODIFIED

Quando movemos esse arquivo para o STAGED, isso quer dizer que o arquivo esta se preparando para fazer parte de um COMMIT.
O Commit é um objeto chave do Git. Ou seja o STAGED depois de preparado passa a ser COMMIT. E depois de ser tido como Commit
o arquivo volata a ser UNMODIFIED para começar novamente todo o ciclo de versionamento das alterações. 
Quando acaba as alterações dos arquivos o Git salva os arquivos e cria um SNAPSHOT, ou seja, el cria uma foto do código (no arquivo)
naquele exato momento. O SNAPSHOT do meu código (arquivo) está salvo dentro do Commit.

tudo isso é im ciclo desses 3 estágios.

** Lembrando: Quando voce digita o comando "git init" voce inicia um Repositório.

VAMOS ENTENDER O QUE OS REPOSITÓRIOS SIGNIFICAM

Gráfico:
							______________________________
							|	Servidor             |
							|	REMOTE REPOSITORY    |
							|____________________________|

     __________________________________________________________________________________
     |	Ambiente de Desenvolvimento						      |
     |										      |
     |	WORKING DIRECTORY		STANGING AREA		LOCAL REPOSITORY      |
     |										      |
     |________________________________________________________________________________|


Nesse momento, nós temos 2 ambientes:

- O Ambiente de Desenvolvimento - (Tudo que está na nossa máquina)
- Servidor

Lembrar que o Git é um sistema distribuido, ou seja, elevai ter a versão deçle no Servidor que no caso é o GitHub, e ele 
tem uma versão que está na Sua Máquina. As alterações que voce faz no código que estão na sua Máquina, ela não é passada (repercute) imediatamente na versão que está no seu Repositório Remoto (Remote Repository). O Repositório Remoto esta guardado no Servidor.

Obs.: O seu Repositório Local, só vai ser composto por Commit. tudo o que estiver no seu Repositório Local deve estar commitado senão ele não será transportado para o seu Repositório Remoto.

Um novo comando: O GIT STATUS
O git status vai ajudar a gente a monitorar exatamente os status dos arquivos, ou seja, ele nos dirá se o arquivo está: 
UNTRACKED, MODIFIED, ou STAGED.

Ex.:

$ git status
On branch master
nothing to commit, working tree clean

Ele vai falar que na BRANCH MASTER (conceito de BRANCH entenderemos mais a frente) não há nada para commitar: WORKING TREE CLEAN, ou seja, a árvore de trabalho está limpa.

Comando novo para usar no Terminal: mv (move arquivos):

ex.: mv estrogonofe.md ./receitas/

vamos aplicar novamente o comando git status

$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    Estrogonofe.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        receitas/

no changes added to commit (use "git add" and/or "git commit -a")

Ele nos informa que não houveram mudanças na branch master para serem commitadas e também esta dizendo que a gente Deletou o arquivo estrogonofe.md, mas ele dix isso porque na verdade voce não deletou mas apenas moveu e o Git ainda não conhece essa nova pasta
no nosso caso RECEITAS, pois ainda noa foi dado (feito) commit e quando o gitnão tem essa informaçã, ele coloca o arquivo no estado UNTRACKED e é isso que o Terminal nos mostra nessa descrição de Status através do git status.
E como o Git é inteligente ele sugere que acessemos a nova pasta onde esta o arquivo e demos o comando git add apar que esse arquivos seja commitado.

Agora vamos colocar arquivos na área sde STAGED  e depois a gente vai COMMITAR  esse arquivos.

Vamos dar sentid a esses arquivos adicionando uma mensagem a ele e criando o SNAP SHOT (foto) da nosso Diretório de Trabalho.

Vamos dar um git add no arquivo estrogonofe.md que esta na pasta receitas sem sair da pasta Workspace
Digite:

git add estrogonofe.md receitas/ <enter>

nos retorna

 git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   estrogonofe.md

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    ../Estrogonofe.md



agora vamos commitar o arquivo estrogonofe.md - colocando uma mensagem

git commit -m "cria pasta receitas, move arquivo para receitas" <enter>

e retorna:

 git commit -m "cria pasta receitas, move arquivo para receitas"
[master 5be260c] cria pasta receitas, move arquivo para receitas
 1 file changed, 16 insertions(+)
 create mode 100644 receitas/estrogonofe.md


Obs.: No master ele mostra a versão resumida do SHA1

Vamos apicar um git status:

git status <enter>

retorna:

$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    ../Estrogonofe.md

no changes added to commit (use "git add" and/or "git commit -a")

Estando no Git, para criar um arquivo na pasta atual digita-se o seguinte comando:

echo > README.md <enter>

Para usar o git add e pegar todos os arquivos usa-se o asterisco (*)

ex.:
git add * <enter>	( ou o ponto(.) que adiciona todas as modificações que fizemos no Repositório Local para STAGING AREA).


retorna

$ git add *
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory

Aplicando um git status 

retorna

$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   README.md

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    Estrogonofe.md


Essa mensagem diz que esxite um arqui em STAGED, ou seja estão prontas para serem commitadas

Agora vamos Commitar

$ git commit -m "Adiciona index"
[master 68da5b2] Adiciona index
 1 file changed, 6 insertions(+)
 create mode 100644 README.md