---
title: Atribuição algorítmica
description: Detalhes sobre o modelo de atribuição algorítmica.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 79%

---


# Atribuição algorítmica

The Algorithmic [attribution model](models.md) in Analysis Workspace differs from other models in that it uses statistical techniques to allocate credit across the dimension items in your report or freeform table. Como todos os outros modelos de atribuição no Analysis Workspace, ele pode ser usado em qualquer dimensão ou métrica e aceita segmentação ilimitada e detalhamentos e distribui 100% das conversões para a(s) dimensão(ões) na tabela (também conhecida como atribuição &quot;fracional&quot;).

O algoritmo usado para atribuição é baseado no Harsanyi Dividend da teoria dos jogos cooperativos. O dividendo de Harsanyi é uma generalização da solução de valor de Shapley (batizada de Lloyd Shapley, economista vencedor do Nobel) para distribuir crédito entre os jogadores em um jogo com contribuições desiguais para o resultado.

Em um nível alto, o cálculo de atribuição do crédito de conversão para cada ponto de contato considera cada um dos pontos de contato de marketing dentro de uma janela de pesquisa como uma coligação de jogadores para os quais um excedente deve ser distribuído de forma equitativa. A distribuição excedente de cada coalizão é determinada de acordo com o excedente anteriormente criado por cada subcoalizão (ou itens de dimensão anteriormente participantes) de forma recursiva. Para obter mais detalhes, consulte os documentos originais de John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). Um valor para jogos em pessoa. *Contribuições para a Teoria dos Jogos, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Um modelo de negociação simplificado para o jogo cooperativo entre pessoas. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>O resultado da atribuição algorítmica só difere de outros modelos quando existem vários pontos de contato dentro da janela de pesquisa. As conversões com um único ponto de contato recebem 100% de crédito independentemente do modelo de atribuição.
