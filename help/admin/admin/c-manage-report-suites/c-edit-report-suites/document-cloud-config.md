---
description: Você pode visualizar dados do Document Cloud no Adobe Analytics
title: Configurar relatórios da Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: bdd9473b0ac3bd77ffeff53a095876e21ca2f4d4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# Configurar relatórios da Document Cloud

É possível configurar dimensões e métricas específicas do PDF para que estejam disponíveis no Adobe Analytics.

## Componentes adicionados quando você habilita os relatórios de PDF

Quando os relatórios de PDF estão configurados corretamente, as seguintes dimensões e métricas estão disponíveis no Adobe Analytics:

**Dimensões:**

* Termo de pesquisa PDF

* Nível de zoom do PDF

* Ação PDF

* Número de página do PDF

* Nome de arquivo do PDF

**Métricas:**

* Exibições do PDF

* Exibições de página do PDF

* Downloads do PDF

* Pesquisa PDF

* Marcadores PDF usados

* Texto de cópia do PDF

* Impressão PDF

## Ativar os relatórios de PDF no Adobe Analytics

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **`<select report suite>`** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Gerenciamento de Document Cloud]** > [!UICONTROL **Relatórios de Document Cloud**].

1. Na página Gerenciamento do Adobe Document Cloud, selecione [!UICONTROL **Habilitar Relatórios de PDF**].

1. Para configurar o Adobe Document Cloud para transmitir dados para o Adobe Analytics, use o [SDK JavaScript do Adobe Document Cloud](https://www.adobe.io/apis/documentcloud/dcsdk.html).
