---
description: Explica como transferir ativos publicados do Report Builder para o Power BI Desktop
title: Transferir ativos publicados para o Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 69%

---

# Transferir ativos publicados para o Power BI Desktop

{{legacy-arb}}

Explica como transferir ativos publicados do Report Builder para o Power BI Desktop

## Pré-requisitos {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* Você precisa ter a versão mais recente do Power BI Desktop instalada (versão de abril de 2017)
* Este processo pressupõe que você já tenha publicado tabelas formatadas ou solicitações do Report Builder no serviço do Power BI.

## Processo {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Na atualização de abril de 2017 do Power BI Desktop, a Microsoft lançou a capacidade de se conectar a conjuntos de dados no serviço do Power BI. Esse recurso permite criar novos relatórios dos conjuntos de dados existentes que você já publicou na nuvem. Você pode aproveitar esse recurso para colaborar melhor e reduzir esforços duplicados em sua equipe.

1. No Power BI Desktop, vá para **[!UICONTROL Arquivo]** > **[!UICONTROL Opções e configurações]** > **[!UICONTROL Opções]** > **[!UICONTROL Visualizar recursos.]**
1. Habilite **[!UICONTROL Conexão em tempo real com o serviço Power BI]** e clique em **[!UICONTROL OK]**. ![Selecione Conexão em tempo real com o serviço Power BI e clique em OK. &#x200B;](assets/bi-preview-features.png)

1. Reinicie o Power BI Desktop.
1. Uma vez que o desktop tenha sido reiniciado, vá para **[!UICONTROL Início]** > **[!UICONTROL Obter dados]** > **[!UICONTROL Mais...]**.
1. Procure por e selecione **[!UICONTROL Serviço Power BI]**.
1. Em **[!UICONTROL Serviço Microsoft Power BI]** > **[!UICONTROL Meu espaço de trabalho]**, selecione o conjunto de dados publicados anteriormente no Report Builder.

Para obter mais informações, consulte a [publicação do blog da Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
