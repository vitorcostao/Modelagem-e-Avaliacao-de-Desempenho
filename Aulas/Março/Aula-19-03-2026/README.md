# Modelagem e Avaliação de Desempenho - Aula 09

## Exercício 

Para responder as questões como: Tempo de vida útil e tempo antes da saturação, é necessário contar com o modelo de carga de trabalho.
Uma proposta é utilizar modelos de regressão linear (Dados históricos da carga variam linearmente).
Considerando que o modelo para carga seja $$\lambda = 5*t + 10$$ e o erro médio da regrassão seja de cinco:

1) Determine o tempo de vida útil que restam ao sistema considerando um histórico de oito meses.
2) Determine o tempo que resta antes da saturação.

> Considerar LNS = 800 e do $D_i = 800$ 


---

## Resolução 01

Para o tópico número um, basta encontrar $\lambda_{cap}$, jogar a carga no modelo para obter o tempo e tirar a diferença do erro, pois
já que deseja-se saber o tempo de vida útil que resta, é melhor pensar no pior caso, que é quando o sistema chega mais rápido no fim da vida útil.

Desse modo, sendo:

$$\lambda_{cap} = \frac{LNS - D_i}{LNS * D_i} = \frac{800 - 200}{800 * 200} = 225 \text{req / min}$$

Ao tirar a diferença do erro se tem como carga 220, que ao jogar no modelo resulta em 42. Por fim, basta subtrair pelos meses de histórico sendo 42 - 8 resultando em 34 meses.

---

## Resolução 02

Para o tópico número dois, basta encontrar $\lambda_{sat}$, jogar a carga no modelo para obter o tempo e tirar a diferença do erro, pois
já que deseja-se saber o tempo que resta antes da saturação, é melhor pensar no pior caso.

Desse modo, sendo:

$$\lambda_{cap} = \frac{1}{D_i} = \frac{1}{200} = 300 \text{req / min}$$

Ao tirar a diferença do erro se tem como carga 295, que ao jogar no modelo resulta em 57. Por fim, basta subtrair pelos meses de histórico sendo 57 - 8 resultando em 49 meses.