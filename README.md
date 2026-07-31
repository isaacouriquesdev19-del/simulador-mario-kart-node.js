Mario Kart.JS

Implementação de uma engine de simulação de corrida baseada nas mecânicas do Mario Kart, desenvolvida em JavaScript. O projeto modela personagens como entidades com atributos numéricos e resolve cada rodada por meio de rolagens de dado combinadas a esses atributos.

Objetivo

Implementar a lógica de simulação de uma corrida entre dois personagens (instâncias), processando 5 rodadas sequenciais em que o tipo de confronto é sorteado dinamicamente, e determinando o vencedor com base no sistema de pontuação.

Modelo de dados — Personagens

Cada personagem é representado por um objeto com três atributos numéricos: velocidade, manobrabilidade e poder.

Personagem	Velocidade	Manobrabilidade	Poder
Mario	4	3	3
Peach	3	4	2
Yoshi	2	4	3
Bowser	5	2	5
Luigi	3	4	4
Donkey Kong	2	2	5

Regras e mecânicas de simulação

Setup:

O sistema recebe dois personagens (instâncias/objetos) para disputar a corrida.
A corrida é executada em um loop de 5 rodadas.

Resolução de rodada:
A cada iteração, um tipo de bloco é sorteado aleatoriamente entre três possibilidades, cada uma acionando uma regra de resolução distinta:

Bloco	Atributo utilizado	Regra de resolução
Reta	Velocidade	Cada jogador rola 1d6 e soma ao atributo. Maior valor final: +1 ponto
Curva	Manobrabilidade	Cada jogador rola 1d6 e soma ao atributo. Maior valor final: +1 ponto
Confronto	Poder	Cada jogador rola 1d6 e soma ao atributo. Menor valor final: -1 ponto

Restrição de estado: a pontuação de nenhum jogador pode assumir valor negativo — o piso é 0.

Condição de vitória

Ao término das 5 rodadas, o personagem com a maior pontuação acumulada é declarado vencedor.
