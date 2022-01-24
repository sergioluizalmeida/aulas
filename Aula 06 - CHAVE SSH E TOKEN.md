### Aula 06 - CHAVE SSH E TOKEN

12/08/21 O tipo de autenticação não é mais valido : usuario  e senha

No git irá funcionar no GtHub não

Chave SSH - É umaforma de estabelecer uma conexão segura entre duas máquinas
Isso é feito através do uso de duas chaves uma chave pública e uma chave privada.
Vamos imserir a chave pública no servidor do GitHub assim o srvidor GitHub vais conhecer a assinatura da nossa máquina e assim
podemos colocar nossos arquivos nos repositórios do GitHub. Sem a necessiade de colocar usuario e senha

Para gerar a chave SSH temos que usar o CLI para gerar a chave. (Git Bash)
Através do Git Bash é que iremos gerar nssa chave SSH

- Acessar o Git Bash - Menu do Windows - Pesquisar e digitar Git Bash - Clicar no Git Bash.
- ssh-keygen -t ed2999  -C seuemail@hotmail.com
 Consegui criar
 .ssh - representa que esse diretório esta oculto

Estando no Git Bash digitar cd /Users/micro/.ssh/	para abrir o diretório e depois digitar : ls para listar o conteúdo da pasta

Usar o comando a seguir para exibir o conteúdo dos arquivos

$ cat id_ed29999.pub		A chave que iremos colocar no GitHub será a chave Pública, conosco fica a chave privada.
 O comando acima digitado no Git Bash mostra a nossa chave encriptada.

Copiei a chave gerada e coleui no perfil da minha conta na aba ssh

Agora tenho que alterar n CLI

o comando pwd mostra o diretorio atual que voce esta no CLI

Agora é necessário Inicializar o SSH Agent, que é uma entidade que é encarregada de pegar as chaves e lidar com elas (autenticar)
Para isso digite o seguinte comando no CLI -(Git Bash):

eval $(ssh-agent -s) <enter>
Ele me trouxe o resultado: Agent pid 1522


Próximo passo é entregar a chave Privada (não a Pública que já fo informada ao GitHub) para que nesse processo seja feito a criptografia
dos arquivos recebdos para eles serem descriptografados, pela nossa chave Privada que fica no nosso computador

Para isoo digite o comando n CLI (Git Bash):
ssh-add id_ed29999 <enter>	// cmo eu já estu no diretório onde esta a minha chave privada e a publica, 

- em seguida devo informar a senha de acesso 

$ ssh-add id_ed2999
Enter passphrase for id_ed29999:
Identity added: id_ed29999 (seuemail@hotmail.com)


Vamos para a Prática

Quando vamos fazer a clonagem das não pode simplesmente copiar a URL e colar para fazer o uso do repositório, senão fica sendo via https 
e agora mudamos a forma pela segurança e para isso tenho que usar o http com SSH pois já criamos para esse objetivo.



A Segunda forma de Autenticação que o GitHub Oferece é o : TOKEN DE ACESSO PESSOAL

O processo que trá que ser feito é o mesmo que o SSH.

A diferença é que o Token se assemelha ao tipo de autenticação anterior usando Usuário e Senha (nickname)

Depois Gera-se um Token no GitHub
Depois vai guardar nasua máquina

Sempre que voce for fazer um Commit, o GitHub vai pedir a seu usuario e na hora da senha ele vai te pedir a ssnha do Token Pessoal.

Vamos para o processo no GitHub para criação do Token Pessoal:

- Acesse o GitHub
- Procure a categoria : Developer Settings - Personal Access Tokens - Generate New Token
Na tela que se abrirá
- No campo Note  digite um nome para voce identificar seu Token e o Sistema Também (não pode deixar em branco)
- Voce pode configurar  tempo que o Token vai expirar e depois de expirado voce terá que gerar outro , fazendo  mesmo processo.
- Marque a Opção Repo
- Clicar no botão abaixo "Generate Token"

- Depois de Gerado , voce vai copiar esse arquivo e colocar em algum lugar seguro no seu Computador.
Essa copia é feita 1 so vez depois que vc copiar ela desaparecerá de lá e vc terá de regenerar outra.