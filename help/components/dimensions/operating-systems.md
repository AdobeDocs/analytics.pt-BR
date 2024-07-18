---
title: Sistema operacional
description: O sistema operacional do visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 42%

---

# Sistema operacional

A [dimensão](overview.md) de &#39;Sistema operacional&#39; mostra o sistema operacional e a versão que o visitante usou. Se você tiver recursos em sua propriedade da Web que sejam específicos do SO, essa dimensão o ajudará a entender quais sistemas operacionais são mais comuns.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. O Adobe faz parceria com o [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente de usuário e o sistema operacional.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do SDK da Web, habilite a [!UICONTROL Pesquisa de Dispositivo] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens de dimensão incluem sistemas operacionais que os visitantes usam. Os exemplos incluem `"Windows 10"`, `"OS X 10.15.7"` e `"Android 9"`.

## Rastreamento de versões precisas do sistema operacional

À medida que o setor avança em direção às dicas do cliente, algumas versões de sistemas operacionais são potencialmente conflitantes. Por exemplo, &quot;Windows 10&quot; e &quot;Windows 11&quot; podem ser agrupados em &quot;Windows 10&quot; se você não coletar dicas de cliente de alta entropia. Consulte [Client hints](/help/technotes/client-hints.md) no guia de Technotes para obter detalhes.
