# FlappyBird-IA
 
Nesse projeto foi recriado o jogo Flappy Bird, utilizando a linguagem Python, para aprender e jogar o game está sendo utilizado a inteligência artificial [NEAT](https://neat-python.readthedocs.io/en/latest/). Tendo como base o projeto Flappy Bird do canal [Hashtag Programação](https://www.youtube.com/@HashtagProgramacao)

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

A tomada de decisão da rede neural é uma conta metemática, o NEAT é responsável por fazer todos esses cálculos. Além das multiplicações realizadas, existe o BIAS, sendo um valor aléatório que irá somar om o Output. Para que o valor final varie dentro de um intervalo, condensando os números entre -1 e 1, também vamos utilizar uma função conhecida como tangente hiperbólica. Se ao final de todos os cálculos o valor for maior que 0.5, o pássaro irá pular, caso contrário, não irá pular. O valor do BIAS e os pesos são decididos aleatóriamente pela IA na criação do pássaro, o agente gera 100 pássaros de uma vez, criando 100 valores diferentes para cada pássaro, assim cada pássaro irá ter seus próprios valores, por isso vemos pássaros voando muito alto, outros muito baixos, percebemos também que alguns pássaros conseguem uma pontuação maior, assim selecionamos esses melhores e realizamos uma clonagem e recriamos eles 98 vezes, assim gerando 100 pássaros "inteligentes", para que esses pássaros não realizem as mesmas atividades, fazemos uma pequena mudança neles, para assim gerar uma evolução, podendo assim gerar um pássaro um pouco melhor ou um pouco pior. Essa modificação é feita nos valores do peso, BIAS ou até uma camada a mais, introduzindo um novo cálculo. Assim criamos a segunda geração de pássaros, sendo os melhores da primeira geração com uma pequena modificação, repetindo assim o ciclo, os melhores são selecionados, clonados, modificados e colocados para jogar, isso é repedito até chegar no pássaro que chegue ao fim do jogo.

Para realizar tudo isso vamos ter 3 passos, primeiro precisamos recriar o jogo Flappy Bird, após é necessário passar todos os parâmetros para configurar a IA, a rede neural possui diversos parâmetros necessários para o funcionamento, que foram definidos pelo criador do NEAT, após passar a lista de parâmetros obrigatórias vamos implementar a Inteligência Artificial dentro do jogo, modificando assim o jogo para que a IA jogue e naturalmente realize esse processo repetitivo de gerar os pássaros e selecionar os melhores.

[Clique aqui](https://neat-python.readthedocs.io/en/latest/) para acessar o site oficial da biblioteca que está sendo utilizada. Buscando por [Configuration file description](https://neat-python.readthedocs.io/en/latest/config_file.html) podemos encontrar a explicação para todos os parâmetros necessários para o arquivo config.txt.

Figura 1 - Demonstração da primeira geração de pássaros

![exemplo_geracao_1](https://user-images.githubusercontent.com/78378199/219223194-4272a791-570d-47ba-868b-0b15f242ad78.png)

Fonte: Captura própria

Figura 2 - Demonstração da segunda geração de pássaros

![exemplo_geracao_2](https://user-images.githubusercontent.com/78378199/219223197-06fdab37-f908-4a5c-a8ca-a40822db67cd.png)

Fonte: Captura própria

Podemos concluir que apenas com a segunda geração de pássaros já é possivel "zerar" o jogo, pois conseguiu alcançar grandes pontuações com mais de 1 pássaro jogando ao mesmo tempo.
