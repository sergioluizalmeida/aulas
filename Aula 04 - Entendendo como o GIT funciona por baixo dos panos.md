### Aula 04 - Entendendo como o GIT funciona por baixo dos panos

Tópicos fundamentais para entender o funcionamento do GIT

- SHA1
- Objetos Fundamentais
- Sistema Distribuido
- Segurança

O que é SHA1 ?

A sigla SHA significa Secure Hash Algorithm (algoritmo de Hash Seguro), é um conjunto de funções hash
criptográficas projetadas pela NSA (Agência de Segurança Nacional do EUA).
É um arquivo de Encriptação - Ele vai pegar um arquivo de qualquer tipo e vai embaralhar de uma maniera muito específica
garantindo assim a segurança do arquivos ora encriptado.

A encriptação gera conjunto de caracteres identifcadores de 40 dígitos. Esses conjuntos de caracteres são Únicos e servem como identificação.
O GIT faz uso desse método de segurança

O SHA1 é uma forma curta dsde representar um arquivo.

Exemplo aplicação do SHA1 na string "Ola Mundo" e seu arquivo encriptado resultante.
1 echo "ola mundo" ! openssl sha1
2 > (stdin)= f9fc856e559b950175f2b7cd7dad61facbe58e7b

Sempre que a gente roda esse arquivo ele vai gerar uma chave diferentre do arquivo para a gente. Por isso é Seguro.

Fazendo uso do Terminal do GIT

Para chamar o GIT Bash, posicione na área de trabalho, clique com notão direito do mouse, clique em Git Bash Here

Agora na linha de comando do Terminal Git Bash $ digite: openssl sha1 teste.txt (nome do arquivos que será aplicada a encriptação).

Após feito isso será gerado no GitBash (Terminal) uma encriptação. Se no conteúdo do arquivo for feita uma alteração e novamente
for aplicado openssl sha1 no arquivo alterado, será gerada uma nova encriptação. Se retornarmos a alteração feita no 1 vez e for
novamente aplicado o openssl sha1 no mesmo arquivo, retornará a chave de encriptação gerada inicialmente.

comando aplicado no Terminal Git Bash: openssl sha1 teste.txt <enter>
Ex.: chaves de 40 caracteres geradas
ce216692c466fd8167278e36e844217d18ed6b62	- arquivo teste.txt conteúdo original
3606c06a083eb80155f67c767d45b14018fd2e68	- arquivo teste.txt conteúdo alterado
ce216692c466fd8167278e36e844217d18ed6b62	- arquivo teste.txt retornado ao conteúdo original


Esse resultado da aplicação do SHA1 não funciona apenas em arquivos mas também em Objetos, como veremos a seguir.