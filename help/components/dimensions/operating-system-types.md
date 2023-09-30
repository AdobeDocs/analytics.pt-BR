---
title: Tipos de sistema operacional
description: O sistema operacional independentemente da versão.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 55%

---

# Tipos de sistema operacional

Os &#39;Tipos de sistema operacional&#39; [dimension](overview.md) mostra o SO abrangente que o visitante usou, independentemente de versões específicas. Essa dimensão é útil para entender não apenas qual sistema operacional e versão específicos são mais comuns, mas qual plataforma de SO típica os visitantes usam.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. parceiros Adobe com [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente do usuário e o tipo de sistema operacional.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do SDK da Web, habilite [!UICONTROL Pesquisa de dispositivo] quando [configurar um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens de Dimension incluem o tipo de sistema operacional usado. Os exemplos incluem `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` e `"Apple iOS"`.
