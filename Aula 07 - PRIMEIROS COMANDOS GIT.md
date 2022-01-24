### Aula 07 - PRIMEIROS COMANDOS GIT

Iniciando o GIT e criando um commit

- Iniciar oGIT
- Iniciar o versionamento
- Criar um commit

Os comandos que iremos utilizar seguindo a descrição acima o primeiro comando para iniciar o GIT:
- git init
O comando para iniciar o versionamento:
- git add
O comando para criar um commit:
- git commit

Quando estamos lidando com Terminal, sempre colocamos o nome do programa na frente.
todo comando do GIT leva a palavra "git" na frente logo após, exemplo: "git init", "git add", "git commit".

Obs.: Estando no Git para mudar de Unidade por ex.: e: estando no Git deve-se digitar:
/e <enter>

Criando um Repositório
Vamos rodar git init

digite:

git init <enter>

A partir daí ele vai inicilizar o repositório e dizer que esta vazio mas se repararmos na expressão depois de digitado o comando
vamos perceber que foi criado uma pasta .git ex: 
$ git init <enter> e retorna a mensagem abaixo, en final vemos que ele criou uma pasta /.git/
Initialized empty Git repository in E:/workspace/livro-receitas/.git/

Esta asta criada pelo Git ".git", ela não apárece porque ela é uma pstas oculta (de gerenciamento), onde o Git versiona s objetos
que estaremos versionando.

Para ver esta pasta pelo comando "ls" de listagem, devemos usar a flag (-a) após o comando "ls" ex.:
ls -a <enter>
retorna:
./  ../  .git/

A flag (-a), mostra arquivos ocultos.

Se eu abrir essa pasta (.git) ex.: cd .git/, ele vai mostrar os arquivs ou pastas dentro dela.
ex:
vou abrir a psta .git: 
cd .git/ ,enter>

vou aplicar um comando ls:
$ ls
HEAD  config  description  hooks/  info/  objects/  refs/

Para voltar um nível de diretório ou pasta digite:
cd .. <enter>

Agora vamos criar um arquivo, mas antes de criar temos que fazer uma cobfiguração inicial que segue, poisé a primeira vez que
o Git esta sendo usado.
Ele vai pedir pra voce um: nickname, apelido ou um email, isso para identificar um Autor para fazr parte da descrição de quem fez 
esse trabalho (orienta o versionamento).
Para isso vou digitar o seguinte comando para que fique de uma forma de identificação Global:

git config --global user.email "seuemail@hotmail.com" <enter>

Agora vou configurar o meu user name, para isso digite:
git config --global user.name nomeusuario <enter>

Pronto , assim terminanmos a configuração inicial do Git para nos reconhecer como autores. 

ADICONANDO UM ARQUIVO

Poderiamos usar um arquivo .TXT, mas vamos usar um arquivo "Markdown" que é a forma mais humana de se escrever um arquivo HTML.

Para  representar um arquivo Markdown, vamos observar a forma de escrita desse tipo de arquivo em relção ao HTML.

	MARKDOWN				HTML
	
	1 # Título nível 1			1 <h1>Título nível 1</n1>
	2 ## Título nível 1			2 <h2>Título nível 2</n2>
	3 #### Título nível 1			3 <h3>Título nível 3</n3>
	4 ##### Título nível 1			4 <h4>Título nível 4</n4>
	5 ###### Título nível 1			5 <h5>Título nível 5</n5>
	6 ####### Título nível 1		6 <h6>Título nível 6</n6>

A exstensão do Markdown é (.md)

Vamos criar nosso primeiro arquivo .md

Defini como programa apadrão para abrir meus arquivos Markdown (.md) o Bloco de Notas do Windows. (ele usou o Typora)

Baixei o Typora e preciso usa roa Ajuda do Typora em Ajuda, Typora Rference

Agora vamos commitar o arquivo

Vamos para o Git

vamos versionar ou seja adicionar o arquivo no Gitdigite:

git add * <enter>

depois disso vamos commitar, o (-m)adiciona os metadados, textos e autor etc.. digite:

git commit -m "commit inicia" <enter>

e vai retornar:

[master (root-commit) edb75c1] commit inicia
 1 file changed, 16 insertions(+)
 create mode 100644 Estrogonofe.md

Assim geramos nosso primeiro Commit - Parabéns

- Perceba que os números que estão acima, depois do (root-commit) são as iniciais do SHA1 desse Objeto, ou seja
isso mostra que esse arquivo foi encriptado junto com seus textos e seus objetos.

com isso nós aprendemos a:

- Criar um Repositório
- Iniciar o Git (para que ele comecde de fato versionar o código)
- tivemos nosso primeiro contato com Markdown
- Fizemos o commit inicial do nosso projeto.

Na proxima aula nós vamos aprender os estados desses arquivos, como ele nos diz o que foi alterado, ou como o Git identifica como o arquivo não foi alterado e como a gente manipula de umaforma completa esses arquivos.