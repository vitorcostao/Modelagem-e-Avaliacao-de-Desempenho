# Modelagem e Avaliação de Desempenho - Aula 16

### Etapa 9: Previsão do Início da Fase de Super-Utilização

A fase de **Super-utilização** é caracterizada pelo alcance da saturação do sistema (100% de utilização do processador) de forma permanente [cite: MAD10.pdf]. O conceito de "permanente" é relativo à finalidade do sistema [cite: MAD10.pdf]:
- **E-commerce:** Saturação acima de 10% do horário de pico (> 6 min) [cite: MAD10.pdf].
- **Gestão Acadêmica:** Saturação acima de 60% do horário de pico (> 36 min) [cite: MAD10.pdf].

#### Cálculo do Tempo para Saturação
Utiliza-se o modelo de carga de trabalho $L(t) = a + b \cdot t$ e a carga de saturação $L_{sat} = 1 / D_i$ [cite: MAD10.pdf].
- **Fórmula:** $t_{sat} = (L_{sat} - a) / b$ [cite: MAD10.pdf].
- **Previsão Real:** O tempo restante é a diferença entre $t_{sat}$ e o histórico de meses já decorrido [cite: MAD10.pdf].

---

### Etapa 10: Proposta de Nova Configuração

Nesta etapa, busca-se ajustar uma configuração que atenda aos requisitos de **Vida Útil**, **Ociosidade** e limites de **SLA (Service Level Agreement)** [cite: MAD10.pdf].

#### Parâmetros de Decisão
- **Vida Útil:** Calculada através do $t_{cap}$, que indica quando a carga atingirá a capacidade máxima do novo SLA ($L_{cap}$) [cite: MAD10.pdf].
- **Ociosidade:** Definida pela fórmula $1 - U_{cap}$, garantindo uma margem de segurança (disponibilidade) para o sistema [cite: MAD10.pdf].

---

### Etapa 11: Negociação com Diretoria e Fornecedores

A viabilização da troca de hardware exige habilidades de convencimento baseadas em dados técnicos sólidos [cite: MAD10.pdf]. Devem ser preparados relatórios detalhados contendo [cite: MAD10.pdf]:
1. Estimativas de crescimento da carga de trabalho.
2. Consumo médio e valores de pico do processador.
3. Frequência de utilização máxima durante o horário de pico.
4. Histórico detalhado dos últimos 3 meses.

---

### Ciclo de Vida do Sistema e Situações Operacionais

O planejamento de capacidade percorre um ciclo entre quatro fases principais: **Conceitual**, **Aquisição**, **Operacional** e **Super-utilização** [cite: MAD10.pdf].

| Situação | Características |
| :--- | :--- |
| **Primeira Configuração** | Fase inicial (Conceitual/Aquisição). |
| **Atualizações Constantes** | Melhorias pontuais sem um *upgrade* completo do sistema. |
| **Crítica** | O sistema opera simultaneamente nas quatro fases, exigindo intervenção imediata. |

> **Conclusão:** A transição para uma nova configuração deve ser antecipada idealmente com 1 ano de antecedência [cite: MAD10.pdf]. A precisão matemática nos cálculos de $t_{sat}$ e $t_{cap}$ é a principal ferramenta para garantir a continuidade dos serviços de TI