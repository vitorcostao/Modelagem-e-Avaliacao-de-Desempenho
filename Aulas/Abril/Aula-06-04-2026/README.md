# Modelagem e Avaliação de Desempenho - Aula 11

## Identificação do Horário de Pico do Sistema

### Etapa 2: Identificação do Horário de Pico

Para que os esforços de otimização de um sistema computacional sejam eficientes, eles devem ser concentrados nos **horários de pico**. A identificação desses períodos permite que as melhorias tenham o maior impacto possível no desempenho global.

#### Objetivos da Identificação

A coleta de dados deve ser realizada ao longo de **1 ano, 24 horas por dia**, com o intuito de identificar os seguintes pontos críticos:
- **Semestre** mais crítico.
- **Mês** mais crítico.
- **Dia da semana** mais crítico.
- **Período do dia** mais crítico.

> É importante notar que os horários de pico podem sofrer variações significativas dependendo do mês ou do semestre analisado.

---

### Procedimentos para Coleta e Análise

A identificação do pico segue um processo metodológico baseado em amostragem e monitoramento de software.

#### Configuração do Monitoramento

1.  **Definição de Tempos:** Utiliza-se um tempo total de observação ($T_o$) de 365 dias e um tempo de amostragem ($T_s$) padrão de 3 segundos.
2.  **Divisão de Períodos:** O dia é dividido em intervalos (ex: P1, P2, P3, P4) baseados no perfil da empresa ou experiência prévia.
    - *Exemplo:* P1 (08h-10h), P2 (10h-12h), P3 (12h-18h), P4 (18h-08h).

#### Cálculo da Utilização

- Para cada intervalo de 10 minutos, são coletados aproximadamente 200 valores (considerando $T_s = 3s$).
- Calcula-se a **Utilização Média ($U_{10}$)** para esse intervalo de 10 minutos.
- A partir desses valores, calcula-se a **Utilização Média do Período ($U_{px}$)**.

---

### Identificação dos Horários de Pico

A etapa final consiste em cruzar os dados de utilização da CPU com os períodos e meses do ano.

#### Visualização dos Resultados

- **Gráficos de Utilização:** Permitem visualizar as curvas de consumo de CPU ao longo do tempo.
- **Matriz de Períodos vs. Mês:** Ajuda a identificar padrões sazonais e picos recorrentes.

> **Conclusão:** A identificação precisa do horário de pico é o alicerce para as etapas subsequentes de coleta de dados por processo e seleção de Jobs críticos, garantindo que a otimização foque onde o sistema está mais sobrecarregado.

---

### Resumo Metodológico

| Parâmetro | Descrição |
| :--- | :--- |
| **Duração da Coleta** | 1 ano (365 dias), 24 horas por dia. |
| **Frequência ($T_s$)** | Amostragem a cada 3 segundos. |
| **Granularidade** | Médias calculadas a cada 10 minutos ($U_{10}$). |
| **Foco** | Identificar sazonalidade (semestre, mês, dia e hora). |
