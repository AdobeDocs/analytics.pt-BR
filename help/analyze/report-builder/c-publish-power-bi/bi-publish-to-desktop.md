---
description: Explica como transferir ativos publicados do Report Builder para o Power BI Desktop
title: Transferir ativos publicados para o Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 100%

---

# Transferir ativos publicados para o Power BI Desktop

Explica como transferir ativos publicados do Report Builder para o Power BI Desktop

## Pré-requisitos  {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* É preciso ter a versão mais recente do Power BI Desktop instalada (versão de abril de 2017)
* Este processo pressupõe que você já tenha publicado tabelas formatadas ou solicitações do Report Builder no serviço do Power BI.

## Processo {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Na atualização de abril de 2017 do Power BI Desktop, a Microsoft liberou a habilidade de conectar a conjuntos de dados no serviço do Power BI. Esse recurso permite a criação de novos relatórios a partir de conjuntos de dados existentes já publicados na nuvem. Você pode aproveitar esse recurso para melhor colaborar e reduzir esforços duplicados em toda a equipe.

1. No Power BI Desktop, vá para **[!UICONTROL Arquivo]** > **[!UICONTROL Opções e configurações]** > **[!UICONTROL Opções]** > **[!UICONTROL Visualizar recursos.]**
1. Habilite **[!UICONTROL Conexão em tempo real com o serviço Power BI]** e clique em **[!UICONTROL OK]**. ![Selecione Conexão em tempo real com o serviço Power BI e clique em OK. ](assets/bi-preview-features.png)

1. Reinicie o Power BI Desktop.
1. Uma vez que o desktop tenha sido reiniciado, vá para **[!UICONTROL Início]** > **[!UICONTROL Obter dados]** > **[!UICONTROL Mais...]**.
1. Procure por e selecione **[!UICONTROL Serviço Power BI]**.
1. Em **[!UICONTROL Serviço Microsoft Power BI]** > **[!UICONTROL Meu espaço de trabalho]**, selecione o conjunto de dados publicados anteriormente no Report Builder.

Para obter mais informações, consulte a [publicação do blog da Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
