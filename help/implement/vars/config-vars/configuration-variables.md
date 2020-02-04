---
title: Variáveis de configuração
description: Use variáveis de configuração para ajudar a determinar como os dados são coletados.
translation-type: tm+mt
source-git-commit: e9a876a1f562333056387d63de46a9cfe3fb3939

---


# Visão geral das variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. Normalmente, eles não contêm valores de dimensão ou métrica.

## Configuração de variáveis de configuração

Em implementações JavaScript que usam `AppMeasurement.js`, as variáveis de configuração normalmente são definidas na parte superior do arquivo JS.

Em implementações que usam o Adobe Experience Platform Launch, as variáveis de configuração normalmente são encontradas ao configurar a extensão do Adobe Analytics:

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade que deseja editar.
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] Verifique se todas as variáveis de configuração estão definidas antes de chamar uma função de rastreamento (`t()` ou `tl()`). Evite definir variáveis de configuração na `doPlugins()` função.
