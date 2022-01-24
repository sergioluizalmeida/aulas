Aula 09 - LAÇOS DE REPETIÇÃO - PORTUGOL

Objetivo da Aula

1 - Aprender a utilizar os LAÇOS DE REPETIÇÃO no Portugol

Definição:

Dentro da lógica de programação é uma estrutura que permite executar mais de uma vez o mesmo comando ou conjunto de comandos
de acordo com uma condição ou com um CONTADOR.

eX.: FAÇA ENQUANTO MENOR QUE 10 -- FAÇA ENQUANTO MAIOR QUE 5 etc...

Exemplo:

funcao inicio()
{
	inteiro contador, limite, resultado
	contador=0
	limite=10
	faca
	{
		resultado = 9 * contador
		escreva("9 x " + contador + " = " + resultado + "\n")
		contador++
	} enquanto(contador <= limite)
}

Exercicio Concluido