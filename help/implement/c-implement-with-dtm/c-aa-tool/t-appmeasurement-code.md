---
description: Insira o código de AppMeasurement ao implantar manualmente o Dynamic Tag Management no Adobe Analytics.
keywords: Dynamic Tag Management, contas vinculadas, vinculação de contas, edição de código, appmeasurement, código do appmeasurement
seo-description: Insira o código de AppMeasurement ao implantar manualmente o Dynamic Tag Management no Adobe Analytics.
seo-title: Inserir o código principal do AppMeasurement
solution: Experience Cloud, Analytics, Target, Dynamic Tag Management
title: Inserir o código principal do AppMeasurement
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Inserir o código principal do AppMeasurement

Insira o código de AppMeasurement ao implantar manualmente o Dynamic Tag Management no Adobe Analytics.

1. Na página da ferramenta do [!DNL Adobe Analytics], amplie a seção **[!UICONTROL Geral]** e clique em **[!UICONTROL Abrir editor]**.
1. Descompacte o arquivo [!DNL AppMeasurement_JavaScript*.zip] que você baixou ao [implantar o Adobe Analytics](/help/implement/c-implement-with-dtm/t-analytics-deploy.md).

   Se optar pela biblioteca personalizada, ao abrir a janela, já terá presente a versão mais recente do código. Não é preciso baixar o arquivo compactado do Admin Console.
1. Abra o [!DNL AppMeasurement.js] em um editor de texto.
1. Copie e cole os conteúdos na janela **[!UICONTROL Editar código]**.

   ![](assets/edit-code.png)

1. A Adobe recomenda adicionar o seguinte código acima de *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >Se você adicionar esse código, é recomendável marcar também a caixa de seleção **[!UICONTROL Definir conjuntos de relatórios usando o código personalizado abaixo]** nas configurações gerais da biblioteca.

1. Clique em **[!UICONTROL Salvar e fechar]**.

   Se estiver usando o Módulo de mídia, Módulo de integração ou plug-ins de implementação, também poderá copiá-los na seção do código. O código gerenciado no Dynamic Tag Management pode ser configurado exatamente como o arquivo do JavaScript em uma implementação típica.

