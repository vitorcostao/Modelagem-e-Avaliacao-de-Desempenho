# Modelagem e Avaliação de Desempenho - Aula 10

## Diagnóstico inicial de performance

### 1) Quais variáveis monitorar?

---

#### $\lambda$ (Carga)

Trata-se de uma variável extremamente importante, principalmente quando se tem a curva de desempenho
(carga × tempo), pois a partir da curva é possível identificar como a derivada se comporta, ou seja,
em qual momento da vida útil o sistema se encontra.

---

#### Tempo de resposta médio

Necessário para avaliar a curva de desempenho em termos de carga de trabalho.

---

#### Utilização e Durabilidade do sistema

Através da carga é possível determinar a utilização e a disponibilidade do sistema — uma baixa
disponibilidade indica um alto nível de utilização.

---

#### Memória e Paginação

O uso de memória e os processos de paginação afetam de forma direta no tempo de resposta de uma
requisição.

---

#### Processador (CPU)

O processador é um dos principais pontos de contenção em sistemas sob alta carga. Seu monitoramento
permite identificar saturação, disputas por tempo de execução e desequilíbrios entre
processos de usuário e chamadas de sistema.

Métricas relevantes:

- **Utilização (%)** — percentual de tempo em que a CPU está ocupada; valores sustentados acima de
  80–90% indicam saturação.
- **User time vs. System time** — distingue o tempo gasto em código de aplicação do tempo em
  chamadas de kernel.
---

#### Disco (I/O)

O subsistema de armazenamento é frequentemente o gargalo em leitura/escrita.
Latências elevadas de disco propagam-se diretamente para o tempo de resposta da aplicação,
especialmente em cenários com paginação intensa ou acesso a banco de dados.

Métricas relevantes:

- **Throughput (MB/s)** — volume de dados transferidos por unidade de tempo.
- **IOPS** — número de operações de leitura/escrita por segundo; crítico para cargas aleatórias.
- **Await time** — latência média por operação de I/O concluída.
- **%util** — percentual do tempo em que o dispositivo está processando requisições; próximo de 100%
  indica saturação.
- **Queue depth** — profundidade da fila de I/O; filas persistentemente longas sinalizam que o
  dispositivo não acompanha a demanda.