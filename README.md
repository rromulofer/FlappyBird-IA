# FlappyBird-IA
 
Nesse projeto está sendo recriado o jogo Flappy Bird utilizando a linguagem Python. Para aprender e jogar o game foi utilizado uma inteligência artificial chamada NEAT. 

N - Neural 	<br>
E - Evolution 	<br>
A - Augmenting 	<br>
T - Topology 	<br>

Cada pássaro no jogo é uma rede neural, precisando assim de Inputs para retornar Outputs.

**Inputs:** Informações necessárias para o pássaro tomar decisões.

__Outputs:__ Decisões que o pássaro pode tomar.

**Inputs e seus respectivos pesos:**				<br>
 	1- Posição Y do pássaro	- 0,5				<br>
	2- Distância do pássaro para o cano de baixo - 2	<br>
	3- Distância do pássaro para o cano de cima - 1,3	<br>
	
**O Output tem como resultado a multiplicação e soma dos valores de cada Input com seu respectivo peso**

Ex: 30 * 0.5 + 4 * 2 + (-7) *1,3 = 13,9

**Output:** 13,9

A tomada de decisão da rede neural é uma conta metemática, o NEAT é responsável por fazer todos esses cálculos.
