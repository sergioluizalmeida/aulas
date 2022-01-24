### Aula 02 - Navegação via Command Line Interface e instalação

COMANDOS BÁSICOS PARA UM BOM DESEMPENHO DO TERMINAL

A maioria dos softwares são GUI x CLI ou seja tm ambientes gráficos

O Git é um CLI, ou seja sua tecnologia foi concebida para ser usado em Linha de Comando
Vamos usar (interagir de forma Linha de comando

O que Vamos aprender:

-Mudar de pastas
- Listar as pastas
- Criar pastas / arquivos
- Deletar pastas / arquivos

As diferenciações:

	WINDOWS				UNIX
	- cd				- cd
	- dir				- Ls
	- makdir			- mkdir
	- del / rmdir			- rm-rf

Obs.: Os Sistemas Operacionais Linux e da Apple usam a base Unix

O Terminal do Windows é derivado do Shell
O Terminal do Linux é derivado do Bash
 Por esse mtivo os comandos são diferentes

Uma coisa interessante que o Wondoes 10 tem é o "Windows Subsystem for Linux", ou seja um sistema  Linux rodando dentro do Windows.
é chamado também de WSL - Pode ser instalado wsl -install

- Para se  listar o conteúdo de uma pasta: (W) Windows 	(L) Linux
W - dir
L - ls

- Para se navegar entre diretórios (abrir e fechar diretórios)
W - cd /
L - cd /

- Para abri a pstas Windws
W - cd windows
L - cd etc

- Para fechar pastas
W - CD..
L - cd..

- Para limpar a tela
W - cls
L - clear u ctrl + L

- O uso do TAB (autocompletar)
W - cd W (e apertar TAB ele completa a frase Windows)
L - 

- Para criar uma pasta
W - mkdir workspace	(recomendação é criar essa pasta pos ela será usada os exercicios)
L - sudo su		(Para pegar a permisssão pois esta usando o subsistema do windows, pede senha de acesso)
	mkdir workspace

- Para criar arquivos
W - echo hello 		(Printa na tela o que foi digitado)
	echo hello > hello.txt		(Esse comando cria e joga para dentro do oarquivo hello.txt a conteúdo hello que foi digitado)
	copy con hello.txt <enter> depois digita o conteúdo e finaliza com ctrl C	(tambem cria o arquivo hallo.txt)
L - echo hello > hello.txt

- Para Deletar Arquivos
W - Delete nome do arquivo.ext (Se eu estiver na raiz e digitar Delete Workspace, ele vai deletar o conteúdo do diretório enão o Diretório.
L -

- Para Deletar Diretórios e seus conteúdos (Repositórios)
W - rmdir Workspace	ou 	rmdir Workspace /s /q (deleta tambem subdiretorios)
L - rm -rf Workspace		(-r representa que se~rao deletados todas subdiretprios do diretorio workspace e o f (force) não confirma.