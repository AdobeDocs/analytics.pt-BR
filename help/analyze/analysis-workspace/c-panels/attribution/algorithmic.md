---
title: Atribuição algorítmica
description: Detalhes sobre o modelo de atribuição algorítmica no Adobe Analytics.
translation-type: tm+mt
source-git-commit: 143cbed5f2159b7faab387e10896af836d0780f7

---


# Atribuição algorítmica

O modelo [de](attribution.md) atribuição Algorítmico na Analysis Workspace difere de outros modelos, pois usa técnicas estatísticas para alocar crédito entre os valores de dimensão no relatório ou tabela de forma livre. Como todos os outros modelos de atribuição na Analysis Workspace, ele pode ser usado em qualquer dimensão ou métrica e oferece suporte a segmentação ilimitada e detalhamentos e distribui 100% de conversões para a(s) dimensão(ões) na tabela (também conhecida como atribuição &quot;fracional&quot;).

O algoritmo usado para atribuição é baseado no Harsanyi Dividend da teoria dos jogos cooperativos. O dividendo de Harsanyi é uma generalização da solução de valor de Shapley (batizada de Lloyd Shapley, economista vencedor do Nobel) para distribuir crédito entre os jogadores num jogo com contribuições desiguais para o resultado.

Em um nível alto, o cálculo de atribuição do crédito de conversão para cada ponto de contato considera cada um dos pontos de contato de marketing dentro de uma janela de pesquisa como uma coligação de jogadores para os quais um excedente deve ser distribuído de forma equitativa. A distribuição excedente de cada coalizão é determinada de acordo com o excedente anteriormente criado por cada subcoalizão (ou valores de dimensão anteriormente participantes) de forma recursiva. Para obter mais detalhes, consulte os documentos originais de John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. &quot;Um valor para jogos pessoais.&quot; *Contribuições para a Teoria dos Jogos 2.28*, 1953, pp. 307-317.
* Harsanyi, John C. &quot;Um modelo de negociação simplificado para o jogo cooperativo n-pessoalmente.&quot; *International Economic Review 4.2*, 1963, pp. 194-220.

> [!NOTE] O resultado da atribuição algorítmica só difere de outros modelos quando existem vários pontos de contato dentro da janela de pesquisa. As conversões com um único ponto de contato recebem 100% de crédito independentemente do modelo de atribuição.
