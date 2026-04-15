# Modelagem e Avaliação de Desempenho - Aula 13

## Otimização do Sistema Computacional

### Etapa 5: Propostas de Soluções para Otimização

Após a identificação dos processos críticos, a próxima fase consiste em propor e implementar soluções para otimizar o desempenho do sistema. As ações variam desde medidas paliativas até mudanças estruturais no escalonamento e no uso de hardware.

#### Principais Ações de Otimização

- **Diminuir portas de acesso:** Considerada uma ação **paliativa**, não sendo uma otimização real do sistema.
- **Re-codificação de programas:** Adequada para processos com alto consumo de CPU, embora o impacto no desempenho global seja frequentemente marginal comparado ao impacto do subsistema de disco.
- **Escalonamento do Sistema:** A ação mais aplicada na prática. Consiste em movimentar **Jobs** (processos não on-line) para horários menos críticos (períodos noturnos/batch).
- **Otimização de Discos:** Focada em reduzir o volume de I/O e os tempos de busca e latência, que são os maiores gargalos em sistemas corporativos.

---

### Escalonamento de Serviços

O escalonamento busca organizar a execução de Jobs ao longo do dia para evitar a sobreposição com o horário de pico do ambiente on-line.

#### Desafios e Implicações

1.  **Mudança Cultural:** Exige alterações nas rotinas administrativas do negócio.
2.  **Identificação de Impacto:** É crucial saber quais Jobs realmente sobrecarregam o sistema antes de movê-los.
3.  **Risco de Novos Picos:** A movimentação impensada pode transformar um horário anteriormente calmo em um novo horário de pico.
4.  **Tecnologias de Apoio:** Em sistemas VM (Virtual Machine), utiliza-se o **JCL (Job Control Language)** para programar horários de início, fim e tolerâncias de execução.

> O escalonamento ajuda a diminuir o "caos" operacional e é o pré-requisito para que se possa modelar o sistema e propor novas configurações de hardware.

---

### Otimização do Subsistema de Disco

O acesso ao disco é um dos componentes mais lentos do sistema devido aos tempos de busca (seek), latência e transferência.

#### Estratégias de Melhoria

- **Otimização do Buffer:**
  - **Segmentação Variável:** Ajustar o tamanho do buffer conforme o tamanho e a frequência de acesso ao arquivo.
  - **Buffers Maiores:** Recomendados para arquivos grandes com alta atividade.
  - **Fator de Bloco (FB):** Cálculo do tamanho ideal do buffer ($FB = \text{Tamanho do Registro} \times \text{Número de Registros no Buffer}$).

- **Redução do Movimento do Braço:**
  - Uso de técnicas como **Agrupamento de Discos (Array de Cilindros)** para minimizar o deslocamento físico das cabeças de leitura/escrita.

- **Redução da Fragmentação:**
  - Gerenciar a disputa de espaço entre arquivos permanentes (frequentes) e arquivos voláteis (baixados de fitas para acesso aleatório).

---

### Resumo das Técnicas de Otimização

| Técnica | Foco Principal | Impacto Esperado |
| :--- | :--- | :--- |
| **Escalonamento** | Organização temporal de Jobs. | Redução da carga no horário de pico. |
| **Ajuste de Buffer** | Eficiência de I/O. | Menor número de acessos físicos ao disco. |
| **Array de Discos** | Hardware/Topologia. | Redução drástica no tempo de acesso aos dados. |
| **Re-codificação** | Lógica do Aplicativo. | Redução do consumo de ciclos de CPU. |

> **Conclusão:** A otimização eficaz combina o conhecimento dos horários de pico com o ajuste fino dos recursos de I/O e o remanejamento inteligente da carga de trabalho (Jobs).
