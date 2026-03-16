# Modelagem e Avaliação de Desempenho - Aula 08

## Exercício 01

Um sistema computacional processa uma carga de trabalho homogênea cujo o tempo médio de
consumo de recurso é de 200 ms/req. Responder as seguintes perguntas:

1. Determinar a capacidade se o LNS = 800 ms
2. Determinar a carga de trabalho para disponibilidade de 20%
3. O Departamento de Estatística fez uma previsão de aumento de carga para 250 req/min. Determine o tempo de resposta médio e a disponibilidade do sistema
4. Desejando atender LNS = 800, carga de trabalho de 250 req/min e uma disponibilidade de 30%. Avaliar a factibilidade de atender às demandas.

---

### Resolução 01

Utilizando a fórmula para a capacidade $\lambda_c = \frac{LNS * D_i}{LNS - D_i}$ e tendo LNS igual a 800 e tempo médio de 200, basta substituir na fórmula.
Ao final o resultado será 225 requisições por minuto.

---

### Resolução 02

Utilizando a fórmula para a saturação $\lambda_s = \frac{1}{D_i}$ e tendo o tempo médio de 200, basta substituir na fórmula.
Ao final o resultado será 240 requisições por minuto.

---

### Resolução 03

Utilizando a fórmula de utilização $\U = D_i * \lambda_i$ e tendo o tempo médio de 200 e a carga sendo 250, basta substituir na fórmula.
Ao substituir na fórmula, é só utilizar $R = \frac{0,2}{1 - 0,83}$ (já convertido para unidade de medida em segundos) que ao final resulta em
1,17 de tempo de resposta média. Logo, a disponibilidade é de 17%.

---

### Resolução 04

É impossível atender todas as demandas, na nuvem seria possível, todavia para cada alteração existe um par de valores e sendo assim não tem como
atender todas elas. Matematicamente, $\frac{250}{60}$ resulta em 4,17 e $\frac{0,7}{0,2}$ resulta em 3,5 o que representa cargas distintas.



