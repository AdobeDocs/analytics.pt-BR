---
title: Sistema operacional
description: O sistema operacional do visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 178
ht-degree: 45%

---

# Sistema operacional

A [dimensão](overview.md) de &#39;Sistema operacional&#39; mostra o sistema operacional e a versão que o visitante usou. Se você tiver recursos em sua propriedade da Web que sejam específicos do SO, essa dimensão o ajudará a entender quais sistemas operacionais são mais comuns.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. A Adobe faz parceria com o [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente de usuário e o sistema operacional.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do Web SDK, habilite a [!UICONTROL Pesquisa de Dispositivo] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens de dimensão incluem sistemas operacionais que os visitantes usam. Os exemplos incluem `"Windows 10"`, `"OS X 10.15.7"` e `"Android 9"`.

## Rastreamento de versões precisas do sistema operacional

À medida que o setor avança em direção às dicas do cliente, algumas versões de sistemas operacionais são potencialmente conflitantes. Por exemplo, &quot;Windows 10&quot; e &quot;Windows 11&quot; podem ser agrupados em &quot;Windows 10&quot; se você não coletar dicas de cliente de alta entropia. Consulte [Client hints](/help/technotes/client-hints.md) no guia de Technotes para obter detalhes.
