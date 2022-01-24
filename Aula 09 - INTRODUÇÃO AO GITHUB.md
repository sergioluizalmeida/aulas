### Aula 09 - INTRODUÇÃO AO GITHUB

Trabalhando com GitHub

Para utilizar o GitHub de forma Remota 
, é recomendave que as configurações de usuario e email sejam iguais, pois isso facilita a usabilidade.

Para conferir as configurações que estão no GIT na sua máquina apara re-escrever as configurações, abra o GIT e digite o comando:

git config --list <enter>

retorna:

git config --global --unset user.email <enter>	// Neste caso estamos alterando o user name e o email

Para alterar o username digite:

git config --global user.name "nomeusuario" <enter>

git config --global user.email "seuemail@hotmail.com" <enter>


Se eu rodar o coamsando para listar , verificamos que foi alterasdo com sucesso

git config --list <enter>	// Este comando mostra a lista de como esta configurado o meu Git


Para se alterar as informações das configurações se for necessário vamos fazer o seguinte processo:

digite:











PARA EMPURRAR OS NOSSOS ARQUIVOS PARA O GITHUB SERVIDOR NOS NOSSO FREPOSITORIO 

Digite:

git remote add origin https://github.com/sergioluizalmeida/(nome do repositorio).git <enter>

O origin é apenas um Alias para não termos que ficar digitando https://...  poderia ser qualquer nome ali.

*** Esse link nós conseguimo na nossa conta do Github

Após isso para certificar, posso verificar o conteúdo do meu repositorio no Github Remoto, estando no Git Local

digite:

git remote -v <enter>


Depois podemos ver o status da nossa ação:
digite:

git status <enter>

Ele nos retornará a seguinte mensagem:

On branch master
nothing to commit, working tree clean

Isso significa que na nossa branch não tem nada commitado e a nossa árvore esta limpa.

para empurrar um arquivo para o nosso repositório onde Push significa "empurrar"
digite:

git push origin master <enter>

Importante: Ai ele vai pedir as minhas Credenciais (abre uma janela para isso) ou  talvez não apareça devido a configuração de
instalação do repositório no Git Remoto.
Após isso ele envia o nosso código PARA O REPOSITÓRIO REMOTO

*** master é um conceito que é da branch de que nós estamos enviando esse código