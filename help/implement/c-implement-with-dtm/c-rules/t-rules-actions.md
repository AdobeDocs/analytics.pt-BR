---
description: Configure as ações que serão acionadas pela condição.
keywords: Gerenciamento dinâmico de tags; regra; criar regra; nova regra; tags javascript/de terceiros; configurar ações para condição; adicionar novo script; javascript não sequencial; javascript sequencial; html não sequencial
seo-description: Configure as ações que serão acionadas pela condição.
seo-title: Configurar as ações que serão acionadas pela condição
solution: Marketing Cloud, Analytics, Target, Gerenciamento dinâmico de tags
title: Configurar as ações que serão acionadas pela condição
uuid: 2 e 892 f 0 b -7261-41 ee-b 849-6 e 3054 a 38 de 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configurar as ações que serão acionadas pela condição

Configure as ações que serão acionadas pela condição.

Após configurar a condição, configure as ações que deseja que sejam acionadas pela condição. Essas ações podem incluir eventos do [!DNL Analytics], tags de terceiros e scripts personalizados. Esse exemplo descreve como configurar scripts ou tags de terceiros.

Além das ferramentas integradas como o [!DNL Adobe Analytics] e o Google Analytics, o Dynamic Tag Management pode acionar qualquer tipo de JavaScript ou introduzir o HTML no site, em páginas selecionadas ou em cenários específicos.

Cada regra pode acionar quantos scripts ou introduções de HTML que desejar.

>[!NOTE]
>
>Because DTM allows you to inject custom code into your page, please take care not to create cross-site scripting (XSS) vulnerabilities (see [OWASP’s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) for more info). O uso de elementos de dados em scripts requer atenção especial. Presuma sempre que a origem dos valores de elementos de dados não seja confiável.

**Para configurar ações para a condição do disparador**

1. Click **[!UICONTROL JavaScript / Third Party Tags]** to add a new script to your rule.

   ![](assets/scripts-actions.png)

1. Clique em **[!UICONTROL Adicionar novo script]**.

   ![](assets/scripts-actions2.png)

1. Nomeie o script.
1. Determine como deseja que o script seja acionado e cole o conteúdo desejado na área do texto. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

