### Aula 08 - DESVIOS CONDICIONAIS E COMENTÁRIOS NO PORTUGOL

Objetivos da Aula

1 - Aprender a utilizar os desvios condicionais (estruturas de decisão) no Portugol.

2 - Boas Práticas de Programação - Comentários


DESVIO CONDICIONAL - SE

Qual é a utilização do comando SE ?

"É utilizada a palavra reservada SE, a condição a ser testada entr parenteses e as instruções que devem ser executadas
entre chaves caso o desvio seja VERDADEIRO".

eX.: se (MEDIA > 7) se esta opção for VERDADEIRA o que vem depois deve estar entre {} CHAVES.

ex.:

	se (media>=7){
		escreva("Parabéns !! Você foi APROVADO!!")
	}


Obs.: Para fazer quebra de linha deve-se usar: \n	Ex: escreva("\n" "Parabéns!! Você foi Aprovado..")

No caso se a condição SE for Falsa deveremos usar o SENÃO

SE - SENÃO

Agora vamos imaginar que se a condição for FALSA um outro conjunto de comandos deve ser executado.
Quando iremos encontrar esta situação?


Ex.:

se (media>=7) {
	escreva("Parabéns!! Você foi Aprovado!!")
}

senao {
	escreva("Infelizmente você foi  Reprovado")
}


Obs.: Voce pode colocar Comentários no inicio do programa usando o //. toda vez que eu uso // é para colocar um comentário.


UTILIZANDO UM DESVIO CONDICIONAL - CASO

Quando será utilizado o comando CASO

Este comando é similar aos comandos SE e SENAO, e reduz a complexidade na escolha de diversas opções.
Apesar de suas similaridades como SE, ele possui algumas diferenças. Neste comando não é possível o uso de
operadores lógicos, ele apenas trabalha com vaores definidos.

Exemplo de utilização do comando CASO

interiro valor=0
escolha(valor)
{
caso 1:	//testa se o vsalor é igual a 1
escreva("OK! Abrir Netflix!!")
pare
caso 2:	//testa se o valor é iagual a 2
escreva("OK! Abrir amazon Prime!!")
pare
caso 3:	//testa se o valor é iagual a 3
escreva("OK! HBO GO!!")
pare
caso contrario:
escreva("Você deve escolher as opções 1, 2 ou 3")
}