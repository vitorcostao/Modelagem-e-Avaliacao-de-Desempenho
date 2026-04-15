# Modelagem e Avaliação de Desempenho - Aula 14

## Otimização e Previsão do Sistema Computacional

### Etapa 5 e 6: Propostas de Soluções e Meta-Otimização

Após a identificação dos processos críticos, a próxima fase consiste em propor e implementar soluções para otimizar o desempenho do sistema. As ações variam desde medidas paliativas até mudanças estruturais no escalonamento e no uso de hardware. A **Meta-Otimização** surge como uma estratégia para lidar com o alto volume de processos (300 a 600 em horários de pico), sugerindo a replicação de ações bem-sucedidas em processos similares para alcançar uma otimização global de forma rápida.

#### Principais Ações de Otimização

- **Diminuir portas de acesso:** Considerada uma ação **paliativa**, não sendo uma otimização real do sistema.
- **Re-codificação de programas:** Adequada para processos com alto consumo de CPU, embora o impacto no desempenho global seja frequentemente marginal comparado ao impacto do subsistema de disco.
- **Escalonamento do Sistema:** A ação mais aplicada na prática. Consiste em movimentar **Jobs** (processos não on-line) para horários menos críticos (períodos noturnos/batch).
- **Otimização de Discos:** Focada em reduzir o volume de I/O e os tempos de busca e latência, que são os maiores gargalos em sistemas corporativos.
- **Meta-Otimização por Clusterização:** Utiliza técnicas como **K-Means** (variáveis numéricas) ou **K-Modes** (variáveis categóricas) para agrupar processos com comportamentos similares (consumo de CPU, memória, I/O) e aplicar soluções em lote.

---

### Escalonamento de Serviços e Curvas de Desempenho

O escalonamento busca organizar a execução de Jobs ao longo do dia para evitar a sobreposição com o horário de pico do ambiente on-line. É importante notar que **toda otimização altera as curvas de desempenho** do sistema, mudando o ponto de operação para baixo do Limite de Nível de Serviço (LNS).

#### Desafios e Implicações

1.  **Mudança Cultural:** Exige alterações nas rotinas administrativas do negócio.
2.  **Identificação de Impacto:** É crucial saber quais Jobs realmente sobrecarregam o sistema antes de movê-los.
3.  **Risco de Novos Picos:** A movimentação impensada pode transformar um horário anteriormente calmo em um novo horário de pico.
4.  **Tecnologias de Apoio:** Em sistemas VM (Virtual Machine), utiliza-se o **JCL (Job Control Language)** para programar horários de início, fim e tolerâncias de execução.

---

### Etapa 7: Previsão da Carga de Trabalho Futura

A partir da Etapa 7, a metodologia transita de ações exclusivamente corretivas para **ações preventivas**. O objetivo é prever a demanda futura para garantir que o sistema suporte o crescimento sem degradação do serviço.

#### Modelagem Estatística para Previsão

- **Regressão Linear:** Utilizada para prever a carga média ($\lambda$) baseada no histórico temporal. O modelo segue a fórmula $L = a + b \cdot t$, onde 'a' é o intercepto e 'b' é a taxa de crescimento.
- **Análise de Correlação de Pearson ($r$):** Essencial para validar a confiabilidade do modelo de regressão.
    - $0.9$ a $1.0$: Correlação muito forte.
    - $0.7$ a $0.9$: Correlação forte.
    - Abaixo de $0.3$: Correlação desprezível (modelo não confiável).
- **Distribuição de Poisson:** Aplicada para modelar eventos periódicos discretos, como o número de consultas a uma página Web ou chamadas em um intervalo de tempo.

---

### Resumo das Técnicas de Otimização e Previsão

| Técnica | Foco Principal | Impacto Esperado |
| :--- | :--- | :--- |
| **Escalonamento** | Organização temporal de Jobs. | Redução da carga no horário de pico. |
| **Ajuste de Buffer** | Eficiência de I/O. | Menor número de acessos físicos ao disco. |
| **Clusterização** | Meta-otimização global. | Eficiência na aplicação de soluções em larga escala. |
| **Regressão Linear** | Previsão de carga futura. | Planejamento preventivo de hardware e recursos. |
| **Re-codificação** | Lógica do Aplicativo. | Redução do consumo de ciclos de CPU. |

> **Conclusão:** A otimização eficaz combina o conhecimento dos horários de pico com o ajuste fino dos recursos de I/O e o remanejamento inteligente da carga de trabalho. A transição para a fase preventiva, através de modelos de previsão como a Regressão Linear e Poisson, é o que garante a sustentabilidade do sistema a longo prazo.
