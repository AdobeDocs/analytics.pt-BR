---
title: Tipo de navegador
description: A organização que fez o navegador.
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 84%

---

# Tipo de navegador

A dimensão “Tipo de navegador” lista as organizações que fizeram o navegador que o visitante usa. Essa dimensão é útil quando você deseja ver quais navegadores principais os visitantes usam. Ela fornece valor sobre a dimensão “Navegadores”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. Se você usar uma biblioteca do AppMeasurement (por meio de tags no Adobe Experience Platform), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem organizações que fazem navegadores. Os itens de dimensão comuns incluem `"Google"` (os criadores de [!DNL Chrome]), `"Apple"` (os criadores de [!DNL Safari]), `"Microsoft"` (os criadores de [!DNL Edge]) e `"Mozilla"` (os criadores de [!DNL Firefox]).
