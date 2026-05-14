# Modelagem e Avaliação de Desempenho - Aula 17

## Planejamento de Capacidade para Cloud Computing 

**Cloud Computing (Computação na Nuvem)** é uma modalidade de computação caracterizada pela **disponibilidade de recursos sob demanda** em uma estrutura dinâmica e escalável. O termo "recurso" pode se referir a infraestrutura, plataforma, software, serviços ou armazenamento. O provedor de nuvem é responsável por disponibilizar esses recursos de forma eficiente, garantindo que as necessidades dos usuários sejam atendidas dentro de um determinado Nível de Qualidade de Serviço (QoS).

### Vantagens do Cloud Computing:

1.  **Pague pelo uso:** As empresas evitam gastos de capital, utilizando recursos conforme a necessidade. Isso contrasta com a abordagem proprietária, que envolve altos custos iniciais de investimento, custos operacionais (manutenção, pessoal, energia) e atualizações de sistema.
2.  **Não há necessidade de provisionar para picos:** A responsabilidade de suportar cargas de pico, mantendo os níveis de serviço acordados (SLA), é do provedor de nuvem.
3.  **Tempo para Comercializar:** Usuários de nuvem não precisam adquirir, instalar e testar infraestruturas, middleware e aplicativos, acelerando o lançamento de produtos e serviços.
4.  **Desempenho e disponibilidade consistentes:** Provedores de nuvem garantem SLAs rígidos em tempo de resposta e disponibilidade, gerenciando autonomamente os recursos para acompanhar cargas de trabalho variáveis e imprevisíveis.

### Desvantagens do Cloud Computing:

1.  **Privacidade e segurança:** Preocupações com dados confidenciais armazenados em plataformas compartilhadas e a exposição de dados privados ao provedor. Questões regulatórias (ex: LGPD) podem não ser facilmente delegadas a terceiros.
2.  **Dependência externa para aplicativos de missão crítica:** A confiança em terceiros para gerenciar aplicativos essenciais, mesmo com SLAs rígidos e multas por não conformidade, pode ser uma preocupação.
3.  **Recuperação de desastres:** Necessidade de garantias de que o provedor possui planos adequados de backup e recuperação para evitar interrupções.
4.  **Monitoramento e aplicação de SLAs:** Negociar, monitorar e aplicar SLAs pode ser desafiador devido ao compartilhamento de recursos e ao pouco controle do provedor sobre a intensidade da carga de trabalho dos aplicativos dos usuários.

## 2. Tipos de Estruturas e Serviços de Cloud Computing

### Tipos de Estruturas:

*   **Nuvem Pública (Public Cloud Computing):** Disponibilizada via Internet pública por provedores como Amazon Web Services e Microsoft Azure. Oferece menor custo e escalabilidade automática, mas com menos controle sobre a plataforma.
*   **Nuvem Privada (Private Cloud Computing):** Serviços oferecidos via Internet ou rede interna privada, proporcionando completo controle da infraestrutura e isolamento de dados (ex: via VLANs). No entanto, os custos tendem a ser mais altos, pois a empresa é responsável por manutenção, gestão e atualização.
*   **Nuvem Híbrida (Hybrid Cloud Computing):** Combina modelos público e privado. Dados sigilosos são mantidos no ambiente privado, enquanto outros serviços de TI são armazenados na nuvem pública para redução de custos operacionais.

### Tipos de Serviços:

*   **Infraestrutura como Serviço (IaaS):** Permite o provisionamento fácil e acessível de recursos como servidores, conexões, armazenamento e ferramentas relacionadas. Desenvolvedores podem criar ambientes de aplicativos do zero de forma rápida e econômica, aumentando ou diminuindo recursos conforme a demanda.
*   **Plataforma como Serviço (PaaS):** Integra infraestrutura com uma plataforma de desenvolvimento comercial para criar e lançar aplicativos ou serviços. Trabalha em conjunto com IaaS, simplificando a implantação e escalabilidade, com custos previsíveis.
*   **Software como Serviço (SaaS):** Refere-se a software em nível de aplicativo usado pelos usuários da nuvem (ex: software de escritório, financeiro). O Cloud Computing revitalizou o modelo SaaS, reduzindo o custo de produção e servindo como ponte na evolução do gerenciamento e alocação de recursos.

## 3. Planejamento de Capacidade para Cloud Computing

O planejamento de capacidade em nuvem deve considerar dois pontos de vista: o do usuário dos serviços e o do provedor. Quando os serviços são executados sob demanda, a responsabilidade do planejamento de capacidade recai sobre o provedor. No entanto, os usuários devem ser capazes de negociar SLAs com os provedores.

Para otimizar a negociação de SLAs, os usuários podem utilizar a noção de **função de utilidade** para determinar a utilidade combinada dos serviços de nuvem em função de vários SLAs. Exemplos de SLAs incluem:

*   `SLAr`: SLA sobre o tempo médio de resposta por transação (em segundos).
*   `SLAx`: SLA sobre o throughput da transação (em transações por segundo - tps).
*   `SLAa`: SLA de disponibilidade na nuvem.

Cada SLA possui um custo associado (ex: `Cr(SLAr)`, `Cx(SLAx)`, `Ca(SLAa)`). A função de utilidade (`U`) é uma combinação ponderada das utilidades individuais de cada SLA, onde a soma dos pesos (`Wr + Wx + Wa`) é igual a 1, e `U` varia entre 0 e 1.

O problema do usuário é selecionar os valores ideais dos SLAs que maximizam a função de utilidade, sujeitos a restrições de SLA (valores mínimos e máximos que o provedor pode oferecer) e uma restrição de custo máximo (`Cmax`). Isso é expresso como um problema de otimização de restrição não linear.

## Referências

- MENASCÉ, Daniel A.; ALMEIDA, Virgilio A. F. Planejamento de capacidade de sistemas de
computação: analise operacional como ferramenta. Rio de Janeiro: Campus, c1985. 83p.
ISBN 8570012462 (broch.)

