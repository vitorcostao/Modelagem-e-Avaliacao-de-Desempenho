# Modelagem e Avaliação de Desempenho - Aula 15

## Etapa 8: Modelagem Matemática de Sistemas Computacionais

### Introdução à Modelagem Matemática

A **Modelagem Matemática** permite simular o desempenho de um sistema computacional frente a futuras cargas de trabalho previamente estimadas. Esta etapa é fundamental para o planejamento estratégico, permitindo antecipar como o sistema reagirá a mudanças antes mesmo de sua implementação física.

#### Objetivos e Aplicações
- **Simulação de Cargas:** Prever o comportamento do sistema sob diferentes volumes de demanda.
- **Atualizações de Configuração:** Avaliar o impacto da troca ou acréscimo de dispositivos, como a expansão de *storage*.
- **Estimativa de Vida Útil:** Quando integrada ao modelo de previsão de carga, permite identificar o início da fase de super-utilização do sistema.

---

### Pré-requisitos e Limitações do Modelo

Para que a modelagem seja eficaz e fidedigna, certas condições devem ser observadas durante o processo de análise.

1.  **Maturidade do Escalonamento:** A modelagem deve ser iniciada apenas após o estabelecimento de um correto escalonamento de serviços.
2.  **Complexidade Estrutural:** Os modelos matemáticos possuem tantas equações quanto o número de distintos tipos de processos executados em um horário específico.
3.  **Consistência da Carga:** A validade das previsões depende de a natureza da carga de trabalho permanecer a mesma no futuro.
4.  **Evolução Tecnológica:** O surgimento de novas aplicações e serviços pode descaracterizar o modelo matemático original, exigindo atualizações constantes.

---

### Definição do Modelo de Tempo de Resposta

O modelo matemático baseia-se na soma do tempo gasto em cada componente do sistema (CPU e Discos).

#### Variáveis do Sistema
- **R:** Tempo médio de resposta por requisição (em segundos por requisição).
- **Ui:** Utilização do dispositivo "i".
- **Di:** Tempo médio total gasto por uma requisição no dispositivo "i" (sem considerar espera).
- **Xo:** *Throughput* (vazão) do sistema, calculado como Xo = Co / To.

#### Equação Fundamental do Tempo de Resposta
O cálculo do tempo de resposta total é dado por:
**R = Σ [ Di / (1 - Ui) ]**

---

### Exemplos Práticos de Simulação

Abaixo, apresenta-se o impacto de diferentes cenários no tempo de resposta (R) de um sistema com dispositivos D1, D2 e D3.

| Cenário | Tempo de Resposta (R) | Observação |
| :--- | :--- | :--- |
| **Cenário Base** | **7,75 s/req** | Operação normal com utilizações variadas. |
| **Aumento de 10% na Carga** | **49,76 s/req** | Pequeno aumento na carga gera crescimento exponencial em R próximo à saturação. |
| **Otimização de Código (10%)** | **49,54 s/req** | Impacto marginal quando o gargalo reside no I/O. |
| **Expansão de Storage** | **6,34 s/req** | Redução drástica ao aliviar o dispositivo de maior utilização. |

> **Conclusão:** A modelagem matemática revela que o sistema é extremamente sensível a variações de carga quando opera próximo ao Limite de Nível de Serviço (LNS). Medidas como o aumento de hardware (storage) mostram-se mais eficazes que a re-codificação em ambientes limitados por I/O.
