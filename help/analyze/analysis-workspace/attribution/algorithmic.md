---
title: Atribuição algorítmica
description: Entenda os detalhes do modelo de atribuição algorítmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
TQID: 'https://experienceleague.adobe.com/jPLoQcRU8bpCGjKJ37mioUdZOFDUwNehmyBhdx7lj8c'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 38%

---

# Atribuição algorítmica

O [modelo de atribuição](models.md) algorítmica no Analysis Workspace difere de outros modelos na medida em que usa técnicas estatísticas para alocar crédito entre os itens de dimensão em seu relatório ou tabela de forma livre. Como todos os outros modelos de atribuição no Analysis Workspace, a atribuição algorítmica pode ser usada em qualquer dimensão ou métrica. A atribuição algorítmica suporta segmentação ilimitada e detalhamentos e distribui 100% das conversões para uma ou mais dimensões na tabela (também conhecida como atribuição &quot;fracional&quot;).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Atribuição algorítmica](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


O algoritmo usado para atribuição é baseado no Harsanyi Dividend da teoria dos jogos cooperativos. O dividendo de Harsanyi é uma generalização da solução de valor de Shapley (batizada de Lloyd Shapley, economista vencedor do Nobel) para distribuir crédito entre os jogadores em um jogo com contribuições desiguais para o resultado.

Em um nível alto, o cálculo de atribuição do crédito de conversão para cada ponto de contato considera cada um dos pontos de contato de marketing em uma janela de pesquisa como uma coalizão de jogadores. Para essa coalizão de jogadores, um superávit deve ser distribuído de forma equitativa. A distribuição excedente de cada coalizão é determinada a partir do excedente que cada subcoalizão criou recursivamente anteriormente.

Para obter mais detalhes, consulte os documentos originais de John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). Um valor para jogos em pessoa. *Contribuições para a Teoria dos Jogos, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Um modelo de negociação simplificado para o jogo cooperativo entre pessoas. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>O resultado da atribuição algorítmica só difere de outros modelos quando existem vários pontos de contato dentro da janela de pesquisa. As conversões com um único ponto de contato recebem 100% de crédito independentemente do modelo de atribuição.
