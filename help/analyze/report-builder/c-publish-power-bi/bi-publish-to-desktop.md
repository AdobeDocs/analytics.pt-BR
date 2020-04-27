---
description: Explica como transferir ativos publicados do Report Builder para o Power BI Desktop
title: Transferir ativos publicados para o Power BI Desktop
uuid: ef47d5c7-31e0-44fc-a792-bc9d12bb089e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Transferir ativos publicados para o Power BI Desktop

Explica como transferir ativos publicados do Report Builder para o Power BI Desktop

## Pré-requisitos {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* É preciso ter a versão mais recente do Power BI Desktop instalada (versão de abril de 2017)
* Este processo pressupõe que você já tenha publicado tabelas formatadas ou solicitações do Report Builder no serviço do Power BI.

## Processo {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Na atualização de abril de 2017 do Power BI Desktop, a Microsoft liberou a habilidade de conectar a conjuntos de dados no serviço do Power BI. Esse recurso permite a criação de novos relatórios a partir de conjuntos de dados existentes já publicados na nuvem. Você pode aproveitar esse recurso para melhor colaborar e reduzir esforços duplicados em toda a equipe.

1. No Power BI Desktop, vá para **[!UICONTROL File]** > **[!UICONTROL Options and settings]** > **[!UICONTROL Options]** > **[!UICONTROL Preview features.]**
1. Ative **[!UICONTROL Power BI Service Live Connection]** e clique em **[!UICONTROL OK]**. ![](assets/bi-preview-features.png)

1. Reinicie o Power BI Desktop.
1. Depois de reiniciar a área de trabalho, vá para **[!UICONTROL Home]** > **[!UICONTROL Get Data]** > **[!UICONTROL More...]**.
1. Procure e selecione **[!UICONTROL Power BI service]**.
1. Em **[!UICONTROL Microsoft Power BI service]** > **[!UICONTROL My Workspace]**, selecione o conjunto de dados publicado anteriormente no Construtor de relatórios.

Para obter mais informações, consulte esta [publicação do blog da Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
