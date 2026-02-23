# Modelagem e Avaliação de Desempenho - Aula 01

## O que é necessário se pensar em termos de planejamento de Software?

Atualmente, em termos de desenvolvimento de aplicações, os algoritmos eficientes são uma das primeiras soluções para melhoria de desempenho do sistema. No entanto, existem outros fatores que são tão importantes quanto o algoritmos para otimizar uma aplicação. Nesse contexto, um planejamento de Hardware é extremamente necessário para que um sistema funcione de forma adequada.

## Porque o Hardware é tão importante?

O hardware é o alicerce físico que sustenta toda a camada lógica de um sistema. Enquanto o software define as instruções, o hardware é o responsável por armazenar dados e executar serviços por meio do processamento e da transmissão de fluxos de bytes. Sem uma infraestrutura física adequada **(CPU, memória, armazenamento e rede)**, até o algoritmo mais eficiente do mundo encontrará gargalos técnicos, resultando em latência e falhas de disponibilidade.

## A Relação entre Carga e Falha do Sistema

O dimensionamento do hardware é um jogo de equilíbrio. Quando falamos em muitos usuários acessando o sistema simultaneamente, estamos injetando uma carga que consome recursos finitos **(ciclos de CPU, espaço em RAM e largura de banda)**.

Quando essa carga ultrapassa a capacidade máxima que o hardware pode processar, ocorre o que chamamos de Saturação de Recursos. O impacto direto disso segue geralmente esta progressão:

 - Degradação de Desempenho: O sistema começa a enfileirar requisições. O usuário percebe lentidão (aumento de latência). Isso é expresso em gráfico exponencial de carga por tempo médio de requisição.

 - Esgotamento: A memória **RAM** fica cheia ou a **CPU** atinge 100% de uso constante.

 - Falha Crítica (Crash): O hardware não suporta a demanda, os serviços param de responder às novas solicitações e, em casos extremos, o servidor pode travar ou reiniciar. Em suma, o sistema cai.


## Tipos de Hardware adotados por empresas

- **Nuvem:** Trata-se de grandes data centers que oferecem serviços e armazenamento de dados para empresas, baseado no slogan "Pay as you go", as nuvens tem se tornado um dos pilares de tecnologia atualemente.

- **Hibrídos:** Trata-se de empresas que armazenam dados sensíveis em seu próprio Hardware, porém utiliza alguns serviços disponibilizados na nuvem.

- **On-Premises (Local):** Servidores, armazenamento e redes instalados dentro da própria empresa, garantindo controle total, segurança física, mas exigindo alto investimento em manutenção.

## O uso da nuvem é a melhor solução de Hardware para um sistema?

Durante a construção de um sistema, muitas empresas optam pelo uso da nuvem para realização de serviços e para armazenamento de dados. Além disso, é necessário que o uso dos recursos dos data centers seja planejado sendo que tais condições são estabelecidas por meio de contratos entre o cliente e a nuvem. 

Desse modo, na maioria dos casos, as empresas optam pela nuvem devido ao custo para se obter um hardware adequado para armazenar dados. A relação de custo por tempo é expressa em um gráfico linear, ou seja, a longo prazo, o custo é gigantesco.

Portanto, o uso da nuvem pode ser uma solução boa para um sistema, desde que seja bem planejado em termos de aproveitamento dos recursos dos data centers. Do outro lado, optar por um Hardware próprio é custoso, porém garante autonomia da empresa. Por fim, o modelo híbrido é ideal para manter dados críticos em ambiente local e usar a nuvem para aplicações que demandam alta elasticidade.


## Metodologia para planejamento de capacitadade (12 Etapas)

A metodologia é baseada na otimização do sistema sem gastar com hardware, por meio da distribuição de carga.

### Exemplo prático (Sistema bancário)

Em meio a muitas transações gerando carga alta e queda do servidor, algumas soluções são interessantes para estabilizar o sistema fazendo com que ele volte a funcionar.

1) Reabrir sistema em horário de pico é uma opção, porém pode causar euforia (o que aumenta a carga) e perda de lucro devido às horas de inatividade

2) Dividir a carga nos servidores por meio de características, por exemplo, autorizar que determinadas pessoas nascidas a partir de uma determinada data voltem a usar o sistema (Como se fosse a rotatividade dos carros de São Paulo). 

