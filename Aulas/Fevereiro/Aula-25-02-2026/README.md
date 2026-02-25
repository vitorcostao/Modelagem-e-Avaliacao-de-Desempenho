# Modelagem e Avaliação de Desempenho - Aula 03

## Aplicações e estudos de casos

A modelagem e avaliação de desempenho é crucial em muitas situações no mercado de trabalho.

### Diagnósticos de Servidores EAD

Com a pandemia em 2020 provocada pelo Covid-19, houve um aumento do uso da tecnologia para conectar pessoas e serviços. Desse modo,
o sistema EAD obteve um papel extremamente importante do ensino, todavia a necessidade deste modelo tornava bem provável um colapso
dos servidores pelo excesso de uso mal planejado.

#### Caso Real

1) O servidor suportará o aumento de cursos EAD? (Modelagem matemática)
2) O sistema trabalhava com 80 requisições (80 equações para serem analisadas)
   - Eliminar processor obsoletos.
   - Redução de processos similares.
   - Chegaram ao modelo resultante com 5 equações

Para cada requisição existe um tempo médio de resposta (Carga x Tempo), a ideia é reduzir as cargas desnecessárias e projetar o sistema
para que funcione corretamente.

---

### Planejamento de sistemas computacionais em Leasing

O leasing é um modelo que se paga parte de um hardware como aluguel para possuí-lo. Todavia, diferentemente da nuvem, que reserva espaço para uso (pay as you go),
no leasing, o hardware se torna seu, o que torna melhorias futuras extremamente caras para instituições. Aqui a IBM promove aumento do pagamento em troca de melhorias.

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/aef8b78d-15be-41b1-b7ee-4d4b474f3ceb" />

---

### Balanceamento de carga nos servidores

Os servidores podem possuir clusters homogêneos, que oferecem um balanceamento de carga aleatório, ou podem possuir clusters heterogêneos, que promovem um balanceamento
criterioso. Em suma, esses clusters são caracterizado pelos SLAs de cada aplicação que está sendo armazenada, ou seja, se as aplicações possuem SLAs parecidos, logo tem-se
um cluster homogêneo, caso contrário é um cluster heterogêneo.

Em servidores homogêneos é mais simples de realizar o balanceamento, porém quando se tem servidores heterogêneos, realizar o ajuste dos gráficos de tempo de requisição por
carga aplicada para cada sistema se torna algo complexo.
