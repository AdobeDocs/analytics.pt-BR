---
title: Variáveis de configuração
description: Use variáveis de configuração para ajudar a determinar como os dados são coletados.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%

---

# Visão geral das variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. Normalmente, elas não contêm valores de dimensão ou métrica.

## Definir variáveis de configuração

Em implementações JavaScript que usam `AppMeasurement.js`, as variáveis de configuração normalmente são definidas no lugar do arquivo JS.

Em implementações que usam tags da Adobe Experience Platform, as variáveis de configuração normalmente são encontradas por meio da configuração da extensão do Adobe Analytics:

1. Faça logon na [Interface da coleção de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
1. Clique na propriedade que você quer editar.
1. Clique na guia [!UICONTROL Extensões] e, em seguida, clique em [!UICONTROL Configurar] no Adobe Analytics.

>[!IMPORTANT]
>
>Verifique se todas as variáveis de configuração estão definidas antes de chamar um método de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Evite definir variáveis de configuração na função [`doPlugins()`](../functions/doplugins.md).
