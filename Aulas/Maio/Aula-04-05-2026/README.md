# Modelagem e Avaliação de Desempenho - (Revisão para Prova)

## Exercícios sobre Servidores Distribuídos

Um sistema é formado por um cluster de três servidores heterogêneos e um servidor master, com os seguintes parâmetros de demanda ($D_i$) e Limite de Nível de Serviço ($LNS$):

- **$D_1$**: 250 req/min
- **$D_2$**: 150 req/min
- **$D_3$**: 200 req/min
- **$LNS$**: 500 ms (0,5 s)

---

### 1) Calcular os parâmetros de cada servidor (Cargas)

Para o cálculo dos parâmetros, utilizaremos as fórmulas solicitadas:
- $\lambda_{cap} = \frac{LNS - D_i}{LNS \cdot D_i}$
- $\lambda_{otimo} = \frac{0,05}{1,05 \cdot D_i}$
- $\lambda_{sat} = \frac{1}{D_i}$

#### Servidor 1 ($D_1 = 250$ req/min)
- **$\lambda_{cap}$**: $(0,5 - 250) / (0,5 \cdot 250)$ → *Nota: Para fins de cálculo de vazão, a demanda deve estar na mesma unidade de tempo. Considerando $D_i$ como tempo de serviço médio por requisição:*
  - $\lambda_{sat1} = 1 / 250 = 0,004$ req/min
  - $\lambda_{cap1} = (500 - 250) / (500 \cdot 250) = 250 / 125000 = 0,002$ req/min
  - $\lambda_{otimo1} = 0,05 / (1,05 \cdot 250) = 0,05 / 262,5  pprox 0,00019$ req/min

#### Servidor 2 ($D_2 = 150$ req/min)
- **$\lambda_{cap2}$**: $(500 - 150) / (500 \cdot 150) = 350 / 75000  pprox 0,0046$ req/min
- **$\lambda_{otimo2}$**: $0,05 / (1,05 \cdot 150) = 0,05 / 157,5  pprox 0,00031$ req/min
- **$\lambda_{sat2}$**: $1 / 150  pprox 0,0066$ req/min

#### Servidor 3 ($D_3 = 200$ req/min)
- **$\lambda_{cap3}$**: $(500 - 200) / (500 \cdot 200) = 300 / 100000 = 0,003$ req/min
- **$\lambda_{otimo3}$**: $0,05 / (1,05 \cdot 200) = 0,05 / 210  pprox 0,00023$ req/min
- **$\lambda_{sat3}$**: $1 / 200 = 0,005$ req/min

---

### 2) Para um critério de balanceamento, se a carga atual for 300 req/min. Avaliar condição do SO.

**Resposta:**
Ao dividir a carga total de 300 req/min igualmente entre os três servidores, cada um recebe $\lambda_i = 100$ req/min. 

Como a demanda de processamento de cada servidor ($D_1=250, D_2=150, D_3=200$) é superior ao tempo de resposta limite individual sob essa carga distribuída, e especificamente os valores de demanda estão abaixo do LNS global (500ms), o sistema opera em regime estável. Entretanto, devido à heterogeneidade dos servidores, cada um apresenta uma sensibilidade distinta à mesma carga de 100 req/min, resultando em diferentes margens de folga em relação ao seu ponto de saturação individual.

---

### 3) Para disponibilidade de 30% determinar limites para servidores e avaliar sistema.

**Resposta:**
Utilizando a fórmula $\lambda_i = \frac{U_i}{D_i}$, onde $U_i$ representa a utilização (neste caso, a disponibilidade de recursos ou teto de ocupação de 30%, ou seja, $U = 0,30$):

- **Limite Servidor 1**: $\lambda_1 = (42 / 250) \cdot 1000 = 168$ req/min
- **Limite Servidor 2**: $\lambda_2 = (42 / 150) \cdot 1000 = 280$ req/min
- **Limite Servidor 3**: $\lambda_3 = (42 / 200) \cdot 1000 = 210$ req/min

**Avaliação:**
Para garantir que o sistema mantenha uma folga de disponibilidade de 70% (utilização máxima de 30%), a carga de entrada em cada servidor não deve ultrapassar os limites calculados acima. O servidor 2 é o que suporta a maior taxa de chegada absoluta dentro deste critério de utilização por possuir a menor demanda individual ($D_2$).