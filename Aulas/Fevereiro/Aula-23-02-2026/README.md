# Modelagem e Avaliação de Desempenho - Aula 02

## Métricas de avaliação

**- Avaliação Qualitativa (Corretiva)**

  Ao projetar uma solução computacional é necessário um planejamento adequado para manter o desempenho da aplicação. Nesse contexto,
pensando em termos de mercado de trabalho, a melhor solução é aquela que: atende à demanda, o faz menor custo de manutenção possível,
e que extrai o melhor desempenho possível da aplicação.

**- Análise Quantitativa (Preventiva)**

  Em termos quantitativos, os modelos matemáticos de um sistema computacional são adequados para determinar um ponto "ótimo" que gerencie
da aplicação (SLAs das nuvens). A análise de carga por tempo de requisição é crucial para que não haja custos extras e falhas no sistema.

## Conceitos preliminares e ciclo de vida de um Software

*"Um Software começa com uma necessidade e termina quando se torna obsoleto"*

- Um sistema computacional é um Hardware que se associa com um Software e interage com um usuário por meio de um ambiente.
- O usuário gera uma carga computacional e o Hardware/Software entrega o nível de serviço.
> A carga afeta o desempenho, quando não há usuários o Software "morre".


Em se tratando do mercado de trabalho, os gastos do setor TI vem justamente do mal planejamento de desempenho de uma solução computacional.
Se o diretor de TI não estabelecer um belo planejamento dos SLAs da nuvem, o sistema pode ficar superdimensionado ou subdimensionado, ou seja,
haverá um desequilíbrio entre a carga computacional e o tempo de requisição de uma demanda. 
O objetivo do planejamento é aumentar a vida útil do Software, ou seja, fazer com que os SLAs atendam o sistema de forma adequada em um prazo estimado,
geralmente 3 a 4 anos.

---

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/f24b39c1-3211-42c2-a412-a23fa76dcfa9" />

Os gráfico acima possuem dimensões, respectivamente, *uso* X *carga* / *tempo de requisição médio* X *carga*. Nesse contexto, é possível perceber
algumas características:

  - O uso do sistema é proporcional à carga.
  - O tempo de resposta é exponencial à carga.
  - É imprescindível trabalhar longe do P(x).
  - A nuvem não liga para carga do usuário, caso não haja planejamento, alguém tem que pagar.

### Metodologia essencial para um bom desenvolvimento de solução computacional.

**Planejamento de Capacidade**        

 - Monitorar
 - Coletar
 - Identificar horários críticos
 - Sintetizar
 - Avaliar
 - Otimizar

**Planejamento de Estratégico do SLA**

- Prever
- Modelar
- Configurar
- Negociar


 ---


## Problema Real

A monografia de TCC de um aluno estava sendo sobre desempenho de um servidor. Observou-se que, em horário de pico, 100% da memória estava
sendo usada, 35% de paginação estava sendo aplicada e 5% da CPU em uso, isso para um processador i7 da época. De modo simples, esse servidor
havia um hardware potente que estava consumindo muita memória, porém deixando CPU ociosa, ou seja, um servidor subdimensionado.

Portanto, sendo a carga uma requisição por unidade de tempo, logo o que importa é o nível de serviço que indique o nível de desempenho que
o sistema apresenta para uma carga.





 