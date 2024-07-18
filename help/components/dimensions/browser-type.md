---
title: Tipo de navegador
description: A organização que fez o navegador.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 67%

---

# Tipo de navegador

A [dimensão](overview.md) &#39;Tipo de navegador&#39; lista as organizações que fizeram o navegador que o visitante usa. Essa dimensão é útil quando você deseja ver quais navegadores principais os visitantes usam. Ela fornece valor sobre a dimensão “Navegadores”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. O Adobe faz parceria com o [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente de usuário e o navegador.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do SDK da Web, habilite a [!UICONTROL Pesquisa de Dispositivo] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens de dimensão incluem organizações que fazem navegadores. Os itens de dimensão comuns incluem `"Google"` (os criadores de [!DNL Chrome]), `"Apple"` (os criadores de [!DNL Safari]), `"Microsoft"` (os criadores de [!DNL Edge]) e `"Mozilla"` (os criadores de [!DNL Firefox]).
