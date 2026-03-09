# Modelagem e Avaliação de Desempenho - Aula 06

## Curva teórica de desempenho de sistemas computacionais

### Teórica vs Experimental

<img width="1600" height="700" alt="image" src="https://github.com/user-attachments/assets/e4f8fb49-982b-489c-9f5d-7d511ff9a743" />

A imagem acima representa duas curvas de desempenho em um sistema sendo a primeira um modelo idealizado teórico e a segunda uma 
versão mais alinhada com a realidade, cujo o gráfico se encontra entre duas curvas teóricas.

Desse modo, é importante entender definições preliminares:

1) **Carga de trabalho**: Requisições que chegam ao sistema
2) **Parâmetros de controle**: Variável utilizada para mensurar o desempenho (Tempo de resposta e uso do processador)
3) **Nível de serviço**: Par ordenado entre valor da variável de controle e valor de carga
4) **Limite do nível de serviço**: É um valor subjetivo da variável de controle relacionada com nível de satisfação do usuário.

     > A vida útil do sistema se encerra quando a aplicação trabalha de modo permanente acima do limite do nível de serviço. 

5) **Ponto crítico**: É a interseção entre a curva de desempenho e o limite do nível de serviço.

---

### Regiões importantes

<img width="1600" height="615" alt="image" src="https://github.com/user-attachments/assets/68c95e10-fe35-4511-9570-66f364ccf5d2" />

Existem três regiões importantes, a primeira (R1) possui um comportamento constante em relação ao tempo e à carga, a segunda (R2) 
possui um comportamento proporcional entre as dimensões, a terceira (R3) e última possui um comportamento não-linear dito como 
exponencial em que a relação entre as dimensões tende ao infinito.

---

### Modelos matemáticos

<img width="808" height="248" alt="image" src="https://github.com/user-attachments/assets/b779be1c-1d1f-4b10-9296-f4c9a4447fb0" />

Sendo esse um modelo representativo do sistema, tem-se a equação formulada para determinar os modelos matemáticos de desempenho:

$$R = \frac{D_i}{1 - U_i}$$

Em que:

- R: Tempo médio de resposta
- $$U_i$$: Utilização do sistema
- $$D_i$$: Tempo médio total gasto por requisição sem contar tempo de espera



Nesse contexto, em um gráfico de utilização por carga, $$U_i$$ representa o produto da tangente pela carga Lâmbda. Além disso, a tangente
é igual ao valor de $$D_i$$, o que gera implicações ao tentar determinar curvas de desempenho para determinados modelos matemáticos. 



