---
title: Variáveis de configuração
description: Use variáveis de configuração para ajudar a determinar como os dados são coletados.
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 64%

---

# Visão geral das variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. Normalmente, elas não contêm valores de dimensão ou métrica.

## Definir variáveis de configuração

Em implementações JavaScript que usam `AppMeasurement.js`, as variáveis de configuração normalmente são definidas no lugar do arquivo JS.

Em implementações que usam tags Adobe Experience Platform, as variáveis de configuração normalmente são encontradas ao configurar a extensão Adobe Analytics:

1. Vá para `experience.adobe.com` e faça logon quando solicitado.
1. Selecione [!UICONTROL Launch / Data Collection].
1. Clique em [!UICONTROL Ir para Iniciar/Coleta de dados] e selecione [!UICONTROL Tags].
1. Clique na propriedade que deseja editar.
1. Clique na guia [!UICONTROL Extensões] e, em seguida, clique em [!UICONTROL Configurar] no Adobe Analytics.

>[!IMPORTANT]
>
>Verifique se todas as variáveis de configuração estão definidas antes de chamar um método de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Evite definir variáveis de configuração na função [`doPlugins()`](../functions/doplugins.md).
