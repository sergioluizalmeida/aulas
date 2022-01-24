### Aula 05 - Objetos Internos do GIT

Quais são os Objetos BÁSICOS do GIT

- BLOBS
- TREES
- COMMITS

Vamos usar a função hash-object

Exemplo de como iremos fazer

1 echo 'conteúdo' | git hash-object --stdin	// O uso do --stdin  é porque essa função do Git (hash-object) espera receber um arquivo;
2 fc31e91b26cf85a55e072476de7f263c89260eb1
3
4 echo -e 'conteúdo' | openssl sha1
5 > 65b0d0dda479cce59528e28961e498155f5c	// Nesse caso vais gerar um outro conjunto de caracteres, porque? Porque das maneira que o Git manipula esse objetos, eles ficam guardados em om objeto chamado Blob (bolha) \0 Olá Mundo e esse objeto contém MetaDados nele

Exemplo no Terminal Git Bash

echo 'conteudo' | git hash-object --stdin
fc31e91b26cf85a55e072476de7f263c89260eb1


 echo -e 'conteudo' | openssl sha1
65b0d0dda479cc03cce59528e28961e498155f5c

Uso do Objeto Blob que contem Meta Dados

1 echo 'conteudo' | git hash-object --stdin
2 fc31e91b26cf85a55e072476de7f263c89260eb1
3
4 echo -e 'blob 9\0conteudo' | openssl sha1
5 > fc31e91b26cf85a55e072476de7f263c89260eb1

No terminal

$ echo 'conteudo' | git hash-object --stdin		Usando o Git passando a string (conteudo) pela git hash-object
fc31e91b26cf85a55e072476de7f263c89260eb1

$ echo -e 'blob 9\0conteudo' | openssl sha1		Passando os Meta Dados do Blob para essa strung (conteudo) seja etxto ou binário etc
(stdin)= fc31e91b26cf85a55e072476de7f263c89260eb1


O Blob contém metadados do Git que são do tipo objeto, o tamanho da string, o tamanho do arquivo entre outros, sendo esse 
oPrimeiro Objeto conhecido por nós até aqui.

O segundo Objeto são as árvores (Trees)

Tree	<tamanho>
\0
blob	sa4d8s	texto.txt

As Trees armazemnam Blobs, o blob sendo o bloco básico de composição, a Tree armazenando e apontando para tipos de Blobs diferentes
e o outro tipo de dados que são s Cimmits que serão vistos mais a frente.
A árvore (Trees) também contém metadados, onde a \0 aponta para um Blob,que por sua vez tem um SHA1, e a arvore (Tree) também guarda
o nome desse arquivo.

Se repararmos o Blob não guardao nome do arquivo, o Blob só guarda o SHA1 daquele arquivo que são os caracteres identificadores dele e só.

A árvore (Trees) será responsável por montar toda a estrtura e onde está localizado os arquivos.
As árvores (TRees) podem apontar tanto para "arquivos" que são Blobs,ou apntar para outras árvores (Trees), e poruq eisso pode acontecer
proque em um sistema Operascional pdem existir Diretórios que contém outros Diretórios (Subdiretórios), e assim faz sentido que 
o GIT use esse Recursivo,por causa dos Diretórios e Subdiretórios existentes nos sistemas Operacionais.
Assim uma árvore(TRee) pode apontar para outra árvore (Tree) assim como um Diretório pode apontar para outro Diretório.
É assi que as árvores (Trees) funcionam e as árvores também tem um SHA1, 

Sendo assim: As bolhas (Blobs) elas possuem o SHA1 de um arquivo, as árvores (TRee) apontam para esses Blobs e tem um SHA1 encriptado ali
os metadados das árvores (Tree).

		Tree
	Readme Rakefile	    Lib
Blob		Blob		Tree
				simplegit.rb
				Blob

Um esta ne dependencia do outro tanto árvores (Tree) quanto Blobs. Se muda algo em um todos são alterados em cadeia.

A Blob é um objeto que encapsula o cmportamento dos diretórios e é usado para apontar para diretórios que contém arquivos,
e por consequênca aponta para arquivos também.

COMMIT

É o objeto mais importante de todos..

O Commit é o objeto que vai juntar tudo o que vai dar sentido para alteração que você está fazendo.

	Commit
	tree		s4a5sq1
	parente		a98acq1
	autor		perkles
	mensagem	"inicia..."
	timestanp

O SHA1 desse commit é o hash de toda a essa informação
 Commit aponta para todos, blob, Tree, Parente, Autor, Mensagem e outro Commit, por isso ele é o mais mportante.

Os arqivos que são representadospelo "Blob" e dentro dessas pastas, representadas pela "Tree" querem dizer que elas significam
uma alteração feita por mim, pr você. Voce pode escrever uma mensagem dentro desse "COMMIT" que vai estar explicando e dando significado
pra esse monte de arquivo, dentro desse mnte de pastas e esse objeto leva também o nome so Autor.

O "Commit" também tem um "Timestamp", que é um carimbo de tempo que lva o Horário e a Data de quando a alteração foi feita, ou seja,
faz uma coleta completa dos dados referentes as alterações dos arquvosw ou objetos.

Os "Commits" também possem um SHA1

Nisso temos um SHA1 para cada Blob, Tree, Commit e isso gera segurança na aterção das informadas.
O "Commit" é único para cada Autor.

PORQUE O GIT É UM SISTEMA DISTRIBUIDO E SEGURO?

Motivos que comprovam essa afirmação:

- O mesmo sistema estão nos Servidores e nos locais de desenvolvimento.