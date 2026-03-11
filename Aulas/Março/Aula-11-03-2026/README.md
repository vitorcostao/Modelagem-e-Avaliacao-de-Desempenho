# Modelagem e Avaliação de Desempenho - Aula 07

## Exercício 01

Deseja-se analisar um sistema computacional que executa serviços (requisições) de naturezas
distintas porém muito semelhantes. A partir de testes de execução forma obtidos os seguintes
tempos computacionais: 200, 180, 175, 190, 210 (ms).

Determine os principais valores referência para:

  1. Carga de Saturação:
  2. Capacidade do sistema para LNS = 800:
  3. Carga ótima para o qual não há fila de espera:

### Resolução

O tempo médio $$D_i$$ pode ser calulado pela médias dos tempos no teste, que resulta em 191 ms. A partir disso,
tem-se as fórmulas para os problemas.

$L_s = \frac{1}{D_i} = \frac{1}{191} = 0,0052 = 314,136 \text{ R/min}$

$L_c = \frac{LNS - D_i}{LNS * D_i} = 0,003985 = 239,13 \text{ R/min}$

$L_o = \frac{0,05}{1,05 * 191} = 0,002453 = 14,958 \text{ R/min}$

---

## Exercício 02

Considerando que a carga não é homogênea e o que foi observado pelos valores de $D_i$ medido. Determine as cargas de
saturação extremais. Qual valor da carga de saturação deve ser evitada?

### Resolução

Dado os tempos de execução dos testes, basta realizar o cálculo de $L_i$ para o maior e o menor tempo. Ambos resultados são,
respectivamente; 285,71 e 342,85 sendo a unidade de medida requisições por minuto.

---

## Exercício 03

Determine os valores de $D_i$ correspondente a 95% da probabilidade de ocorrer. Determine a carga de saturação para os valores
$D_\text{min}$ e $D_\text{max}$.

### Resolução

Pensando em uma distribuição gaussiana observada a partir de um histograma, ao integrar o gráfico, é possível obter a probabilidade
de determinados valores para o $D_i$ serem concretizados. De modo geral, 95% corresponde ao intervalo, no gráfico de histograma, 
que se inicia na diferença entre a média dos tempos por duas vezes o desvio padrão e que finaliza na média dos tempos mais duas vezes
o desvio padrão. Desse modo, tem-se:

- Desvio-padrão: 14,317 (ao multiplicar por dois resulta em 28,635)
- Média dos tempos: 191
- Início do intervalo: 162, 364
- Fim do intervalo: 219,635






