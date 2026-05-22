---
description: É possível visualizar dados do Document Cloud no Adobe Analytics
title: Configurar relatórios da Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
TQID: 'https://experienceleague.adobe.com/2X5YQxmTsMYdnwSWVL4EMr1K1aV9UM6FRMHa2P--Xuc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 140
ht-degree: 28%

---

# Configurar relatórios da Document Cloud

É possível configurar dimensões e métricas específicas do PDF para que estejam disponíveis no Adobe Analytics.

## Componentes adicionados ao habilitar os relatórios do PDF

Quando os relatórios do PDF são configurados corretamente, as seguintes dimensões e métricas estão disponíveis no Adobe Analytics:

**Dimensões:**

* Termo de pesquisa em PDF

* Nível de zoom do PDF

* Ação em PDF

* Número de página de PDF

* Nome de arquivo de PDF

**Métricas:**

* Visualizações em PDF

* Visualizações de página de PDF

* Downloads de PDF

* Pesquisa de PDF

* Marcadores de PDF usados

* Texto de cópia em PDF

* Impressão de PDF

## Ativar os relatórios do PDF no Adobe Analytics

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **`<select report suite>`** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Gerenciamento do Document Cloud]** > [!UICONTROL **Relatórios do Document Cloud**].

1. Na página Gerenciamento do Adobe Document Cloud, selecione [!UICONTROL **Habilitar Relatórios do PDF**].

1. Para configurar o Adobe Document Cloud para transmitir dados ao Adobe Analytics, use a [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html).
