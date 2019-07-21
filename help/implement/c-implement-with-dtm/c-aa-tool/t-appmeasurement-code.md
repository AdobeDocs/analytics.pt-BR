---
description: Insira o código de AppMeasurement ao implantar manualmente o Dynamic Tag Management no Adobe Analytics.
keywords: Gerenciamento dinâmico de tags; contas vinculadas; vinculação de contas; editar código; appmeasurement; código de appmeasurement
seo-description: Insira o código de AppMeasurement ao implantar manualmente o Dynamic Tag Management no Adobe Analytics.
seo-title: Inserir o código principal do AppMeasurement
solution: Marketing Cloud, Analytics, Target, Gerenciamento dinâmico de tags
title: Inserir o código principal do AppMeasurement
uuid: 3 f 83 fbb 1-3 ed 5-4 e 45-888 a -0 a 183 aac 1 a 90
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Inserir o código principal do AppMeasurement

Insira o código de AppMeasurement ao implantar manualmente o Dynamic Tag Management no Adobe Analytics.

1. Na página da ferramenta do [!DNL Adobe Analytics], amplie a seção **Geral** e clique em **[!UICONTROL Abrir editor]**.
1. Unzip the [!DNL AppMeasurement_JavaScript*.zip] file you downloaded in [deploy Adobe Analytics](../../../implement/c-implement-with-dtm/t-analytics-deploy.md#task_3A00639CADF14C9C844F962222077E4E).

   Se optar pela biblioteca personalizada, ao abrir a janela, já terá presente a versão mais recente do código. Não é preciso baixar o arquivo compactado do Admin Console.
1. Open [!DNL AppMeasurement.js] in a text editor.
1. Copy and paste the contents into the **[!UICONTROL Edit Code]** window.

   ![](assets/edit-code.png)

1. Adobe recommends adding the following code above the *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >If you add this code, it is recommended that you also select the **[!UICONTROL Set report suites using custom code below]** checkbox in the overall library settings.

1. Click **[!UICONTROL Save and Close]**.

   Se estiver usando o Módulo de mídia, Módulo de integração ou plug-ins de implementação, também poderá copiá-los na seção do código. O código gerenciado no Dynamic Tag Management pode ser configurado exatamente como o arquivo do JavaScript em uma implementação típica.

