# Modelagem e Avaliação de Desempenho - Aula 18

## Modelagem matemática de sistemas computacionais

A modelagem matemática de Sistema Computacionais baseado na teoria das filas é fundamentada no fato de um sistema computacional, ao possuir velocidade finita, produz fila de espera. A modelagem baseado na teoria das filas, pode modelar qualquer sistema em distintos níveis de abstração.

### Níveis de Abstração na Modelagem

A modelagem pode ser aplicada a diferentes componentes e níveis de um sistema:

1.  **Dispositivos Isolados:** Análise de componentes individuais, como a CPU ou o disco, observando a fila de requisições que se forma antes de cada um ser processado.
2.  **Sistemas Computacionais Completos:** Visão mais ampla onde um ambiente de usuários gera requisições que passam por uma fila geral, são processadas pela CPU e, em seguida, podem ser direcionadas para diferentes discos (D1, D2, D3), formando um ciclo contínuo de processamento e retorno ao ambiente de usuários.
3.  **Subsistemas de Hardware/Software:** O sistema pode ser visto como um bloco consolidado (subsistema) que recebe requisições de um conjunto de terminais e, após o processamento, retorna as respostas, formando a fila do sistema como um todo.

### Modelagem de Sistemas Interativos

A modelagem de sistemas interativos foca na relação entre os usuários (terminais) e o sistema computacional central. As principais variáveis envolvidas neste modelo são:

*   **$T_o$:** Tempo de observação (em segundos).
*   **$A_o$:** Requisições que chegam ao sistema durante o tempo $T_o$ (em requisições).
*   **$C_o$:** Requisições atendidas durante o tempo $T_o$ (em requisições).
*   **$Z$:** Tempo de pensar (em segundos), que é o tempo que o usuário leva entre receber uma resposta e enviar a próxima requisição.
*   **$R$:** Tempo médio de resposta (em segundos por requisição), que é o tempo que o sistema leva para processar e devolver a resposta ao usuário.
*   **$M$:** Número de terminais (usuários) ativos no sistema.

A partir dessas variáveis básicas, derivam-se métricas fundamentais para a avaliação de desempenho:

*   **Carga de Trabalho ($\lambda_o$):** Taxa de chegada de requisições, calculada como $\lambda_o = A_o / T_o$ (requisições/segundo).
*   **Taxa de Processamento do Sistema ($X_o$):** Também conhecida como *throughput*, é a taxa com que o sistema atende as requisições, calculada como $X_o = C_o / T_o$ (requisições/segundo).

#### Equacionamento do Sistema

Considerando os tempos médios e assumindo que os tempos de transmissão ($t_x$) e recepção ($r_x$) na rede são próximos de zero ($t_x \approx 0, r_x \approx 0$) quando comparados ao tempo de pensar ($Z$), a relação fundamental do sistema interativo é dada por:

$$Z + R = \frac{M}{X_o}$$

Desta equação, podemos isolar o **Tempo Médio de Resposta ($R$)**:

$$R = \frac{M}{X_o} - Z$$

Esta fórmula demonstra que o tempo de resposta aumenta com o número de terminais ($M$) e diminui com o aumento da taxa de processamento ($X_o$) ou do tempo de pensar ($Z$).

### Melhorando o Desempenho do Sistema

Para diminuir o tempo médio de resposta ($R \downarrow$), a equação $R = \frac{M}{X_o} - Z$ sugere duas abordagens principais:

1.  **Diminuir o número de terminais ($M \downarrow$):** Reduzir a quantidade de usuários simultâneos alivia a carga sobre o sistema, resultando em respostas mais rápidas.
2.  **Aumentar a taxa de processamento ($X_o \uparrow$):** Melhorar a capacidade do sistema de atender requisições (por exemplo, fazendo upgrade de hardware ou otimizando software) reduz o tempo de resposta.

### Análise de Limites e Acordos de Nível de Serviço (SLA)

A modelagem permite avaliar o comportamento do sistema frente a restrições, como um **Tempo de Resposta Limite (LNS - Limite de Nível de Serviço)** ou SLA (Service Level Agreement).

Ao plotar o Tempo Médio de Resposta ($R$) em função do Número de Terminais ($M$), observa-se que:
*   Para um número baixo de terminais, o sistema opera na **região ótima ($L_{otima}$)**, onde o tempo de resposta é mínimo e constante.
*   À medida que $M$ aumenta, o sistema atinge a **capacidade ($L_{cap}$)** e o tempo de resposta começa a crescer.
*   Se $M$ continuar aumentando, o sistema entra em **saturação ($L_{sat}$)**, onde o tempo de resposta cresce exponencialmente.

O LNS define um teto aceitável para $R$. Utilizando as equações do modelo, é possível calcular:
*   O **número máximo de terminais** que o sistema suporta sem violar o SLA.
*   O **número mínimo de terminais** necessários para manter o sistema operando de forma eficiente.
*   A **faixa ideal de terminais** ($M_{min} \le M \le M_{max}$) para garantir o cumprimento do SLA e a utilização adequada dos recursos.
