# Modelagem e Avaliação de Desempenho - Aula 12

## Coleta de Dados e Seleção de Processos Críticos

### Etapa 3: Coleta de Dados do Consumo de Recursos por Processo

Após identificar os horários de pico do sistema, o próximo passo é realizar uma nova coleta detalhada do consumo de recursos para cada processo executado nesses períodos. O objetivo principal é identificar **processos críticos** para tornar a otimização mais efetiva.

#### Variáveis Consideradas na Coleta

Durante o processo de coleta, devem ser analisadas duas classes de variáveis:

- **Variáveis Qualitativas:**
  - ID do processo e sistema vinculado.
  - Horários de disponibilização e finalização do serviço.
  - Categoria do processo (Batch ou On-line).

- **Variáveis Quantitativas:**
  - Número de execuções do processo.
  - Tempo total e médio gasto na CPU.
  - Consumo médio de memória e nível de paginação.
  - Número de I/O em disco e tempos de acesso.

---

### Relatórios e Análise dos Dados Coletados

A análise dos dados permite identificar quais processos ou classes de processos estão sobrecarregando o sistema.

#### Principais Indicadores de Desempenho

- **Processos com maior número de execuções:** Frequentemente, um pequeno grupo de processos (ex: Subtotal de 52%) representa a maior parte do volume mensal de execuções.
- **Processos com maior número de EXCP (I/O):** Identifica processos que realizam muitas operações de entrada e saída, seja em disco ou fita.
- **Recursos por Classe de Processo:** Agrupar processos em classes (A, B, C, D, E, F) ajuda a visualizar onde o consumo de CPU e EXCP está concentrado.
  > Exemplo: A classe E pode representar 50% dos processos e ser a que mais consome tempo na fila de espera.

---

### Etapa 4: Seleção de Processos Críticos

Para que a otimização seja eficiente, deve-se priorizar os processos e Jobs que possuem o maior impacto no desempenho global do sistema.

#### Critérios de Priorização

A seleção dos processos críticos deve levar em conta a combinação de diversos fatores de consumo. A recomendação é focar em processos que apresentam altos índices em:
- **CPU e Memória:** Processos que exigem muito processamento e espaço.
- **Número de Execuções (#EXEC):** Processos frequentes que, mesmo leves, podem causar gargalos pelo volume.
- **I/O e EXCP:** Processos que dependem intensamente de operações de leitura e escrita.

> **Nota Importante:** Embora a priorização ajude na eficiência, a recomendação técnica é que todos os processos sejam eventualmente analisados e otimizados para garantir a saúde do sistema a longo prazo.

---

### Resumo das Observações de Desempenho

| Indicador | Observação Típica |
| :--- | :--- |
| **Volume** | Poucos processos costumam responder por ~50% das execuções totais. |
| **Gargalos de I/O** | Classes específicas (ex: C, D e E) podem consumir até 90% do EXCP total. |
| **Filas de Espera** | O tempo na fila de entrada é um indicador crítico de saturação de recursos. |
| **Estratégia** | Começar a otimização pelos processos de maior impacto ("Jobs Críticos"). |
