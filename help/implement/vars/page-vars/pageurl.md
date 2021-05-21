---
title: pageURL
description: Substitua o URL da página coletado automaticamente em seu site.
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '272'
ht-degree: 100%

---

# pageURL

O AppMeasurement coleta automaticamente o URL da página em cada ocorrência. Se você quiser substituir o URL da página coletado automaticamente pelo AppMeasurement, use essa variável. Não é necessário definir essa variável na maioria dos casos.

>[!NOTE]
>
>Essa variável não é uma dimensão disponível no Analysis Workspace. Ela só está disponível no Data Warehouse e nos Feeds de dados. Além disso, os servidores de coleção de dados da Adobe removem essa dimensão de todas as solicitações de imagem de [rastreamento de link](/help/implement/vars/functions/tl-method.md). Se você quiser usar o URL da página como uma dimensão no Analysis Workspace ou quiser essa dimensão em ocorrências de rastreamento de link, considere transmitir a variável `pageURL` para uma [eVar](evar.md) em cada ocorrência.

## URL da página no Adobe Experience Platform Launch

O Launch preenche automaticamente o URL da página. No entanto, é possível definir a substituição do URL da página ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia **[!UICONTROL Regras]** e clique na regra desejada (ou crie uma regra).
4. Em **[!UICONTROL Ações]**, clique em uma ação **[!UICONTROL Adobe Analytics - Definir variáveis]** ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa **[!UICONTROL Extensão]** e defina **[!UICONTROL Tipo de ação]** como **[!UICONTROL Definir variáveis]**.
6. Localize a seção **[!UICONTROL URL da página]**.

Você pode definir o URL da página como qualquer valor de string.

## s.pageURL no AppMeasurement e no editor de código personalizado do Launch

A variável `s.pageURL` é uma string que contém o URL da página. O AppMeasurement coleta essa variável automaticamente, no entanto, você pode substituir o valor dela, se desejar.

```js
s.pageURL = "https://example.com";
```

Se você deseja usar o URL da página como uma dimensão nos relatórios, considere usar o seguinte na implementação:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
