---
description: É possível visualizar dados do Document Cloud no Adobe Analytics
title: Configurar relatórios da Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# Configurar relatórios da Document Cloud

É possível configurar dimensões e métricas específicas do PDF para que estejam disponíveis no Adobe Analytics.

## Componentes adicionados ao habilitar os relatórios do PDF

Quando os relatórios do PDF são configurados corretamente, as seguintes dimensões e métricas estão disponíveis no Adobe Analytics:

**Dimensões:**

* Termo de pesquisa do PDF

* Nível de zoom do PDF

* Ação do PDF

* Número de página do PDF

* Nome de arquivo do PDF

**Métricas:**

* Visualizações do PDF

* Exibições de página do PDF

* Downloads da PDF

* Pesquisa no PDF

* Marcadores PDF usados

* PDF Copy Text

* Impressão no PDF

## Ativar os relatórios do PDF no Adobe Analytics

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **`<select report suite>`** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Gerenciamento do Document Cloud]** > [!UICONTROL **Relatórios do Document Cloud**].

1. Na página Gerenciamento do Adobe Document Cloud, selecione [!UICONTROL **Habilitar Relatórios do PDF**].

1. Para configurar o Adobe Document Cloud para transmitir dados ao Adobe Analytics, use a [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html).
