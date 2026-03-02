# Modelagem e Avaliação de Desempenho - Aula 04

## Ciclo de vida de um sistema computacional

### 1) Fase conceitual

A fase conceitual tem como objetivo definir a configuração inicial do sistema e propor futuras atualizações. Ela é dividida em duas partes: **Proposta inicial** e **Proposta de atualização**.

#### Proposta inicial

Na proposta inicial, são utilizadas diferentes abordagens para estimar o desempenho de um sistema:

1. **Eu acho**: Estimativa baseada na experiência de diretores de TI.
2. **Benchmark**: Avaliação de desempenho utilizando testes padronizados, bom para artefatos isolados.
3. **Kernel**: Avaliação aplicada a algoritmos específicos em processadores que ainda não possuem o sistema completo.
4. **Programa sintético com características de Assembly**: Utilização de programas que simulam cargas de trabalho típicas para medir desempenho.

#### Proposta de atualização

Nesta etapa, a ideia é melhorar a previsão do desempenho utilizando modelos mais sofisticados:

1. **Modelos matemáticos**: Representações formais do sistema que permitem prever o comportamento sob diferentes cenários e cargas de trabalho.

---

### 2) Fase de aquisição

A fase de aquisição tem como objetivo justificar a troca ou atualização do hardware do sistema. Essa decisão geralmente ocorre quando o sistema já passou por anos de otimização e a capacidade atual não atende mais às demandas previstas.

- **Base da decisão**: Previsão de carga futura do sistema.
- **Observações sobre relatórios de desempenho**:
  - Relatórios de CPU podem não ser a melhor forma de convencer gestores sobre a necessidade de atualização.
  - Relatórios baseados em **frequência e períodos de utilização de picos** são mais eficazes, pois mostram claramente os momentos em que o sistema atinge limites críticos.