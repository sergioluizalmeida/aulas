### Aula 10 - RESOLVENDO CONFLITOS

Git Clone é pegar o código que esta no repossitoprio por outra pessoa ou voce mesmo e baixar para sua máquina

Enquanto o arquvo clonada nao for modificado.. eles estarão ainda sincronizados..(esquemas de versionamento de códigos distribuido)

imagine que o código que eu alterei na minha da minha maquina é na mesma linha da pessoa que clonou meu arquivo acontece. É nessa
hora que acontece o CONFLITO (PROBLEMA), Isso é chamado de  CONFLITO DE MERGE. ai voce tera que baixar o arquivo que foi clonado
e fazer a alteração e depois commitar.

Quando eu faço uima alteração em um arquivo e peço um (git status) ele me mostrará que não existe nenhum arquivo para ser commitado, pois ele se encontra após essa alteração num estado STAGED para isso precisamos aplicar o comando (GIT ADD) e depois
aplicar o comando (git status) novamente e ai vai aparecer como o arquivo foi modificado( MODIFIED) e aparece que o arquivo
esta pronto para ser commitado.

Para empurrar o arquivo para o Repositório digite:


git push origin master <enter>



O git pull faz o efeito inverso. ao invés de empurrar para o reposiotorio o comando pull vai puxar o arquivos do repositorio remoto e vai trazer para nossa maquina local (repositorio local)
 e o Git vai tentar juntar essas duas versões.


o comando deve ser aplicado assim:
digite:

git pull origin master <enter>



Relembrando 

git add * <enter>	// habilita o todos (*) arquivos para a árfea de STAGED


git commit -m " resolve conflitos" <enter>



git push origin master <enter> 	// empurra a versão alterada para o repositorio remoto, origin é a nossa Alias (apelido do https://..)



comando para clonar o conteúdo de um Repositório Remoto para nossa máquina Local

Copie a url do repositorio que sera clonado depois:
digite:

git clone https://github.com/python/cpython.git <enter>
cloning into 'cpython'...

Obs.: No git o comando ls -a - mostra diretorios ocultos. É necessário conhecer esse comando pois quando clonamos um repositorio
ele nos traz os arquivos e os diretorios visiveis e ocultos..


Para mostrar para onde esta apontado os arquivos quando são enviados ou clonados digite:

git remote -v <enter>		// dentro do diretoprio que foi clonado ..ou qualquer outro.


Ok Concluído com 80% - Certificado