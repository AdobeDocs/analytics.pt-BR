---
title: Variáveis de configuração
description: Use variáveis de configuração para ajudar a determinar como os dados são coletados.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 126
ht-degree: 65%

---

# Visão geral das variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. Normalmente, elas não contêm valores de dimensão ou métrica.

## Definir variáveis de configuração

Em implementações que usam a extensão do Web SDK ou a extensão do Analytics, as variáveis de configuração normalmente são encontradas nas configurações da extensão:

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Clique na guia [!UICONTROL Extensões] e em [!UICONTROL Configurar] na extensão.

Em implementações JavaScript que usam `AppMeasurement.js`, as variáveis de configuração normalmente são definidas no lugar do arquivo JS.

>[!IMPORTANT]
>
>Verifique se todas as variáveis de configuração estão definidas antes de chamar um método de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Evite definir variáveis de configuração na função [`doPlugins()`](../functions/doplugins.md).
