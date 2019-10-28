---
description: Configure as ações que serão acionadas pela condição.
keywords: Dynamic Tag Management, regra, criar regra, nova regra, tags de terceiros/javascript, configurar ações para condição, adicionar novo script, javascript não sequencial, javascript sequencial, html não sequencial
seo-description: Configure as ações que serão acionadas pela condição.
seo-title: Configurar as ações que serão acionadas pela condição
solution: Experience Cloud, Analytics, Target, Dynamic Tag Management
title: Configurar as ações que serão acionadas pela condição
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Configurar as ações que serão acionadas pela condição

Configure as ações que serão acionadas pela condição.

Após configurar a condição, configure as ações que deseja que sejam acionadas pela condição. Essas ações podem incluir eventos do [!DNL Analytics], tags de terceiros e scripts personalizados. Esse exemplo descreve como configurar scripts ou tags de terceiros.

Além das ferramentas integradas como o [!DNL Adobe Analytics] e o Google Analytics, o Dynamic Tag Management pode acionar qualquer tipo de JavaScript ou introduzir o HTML no site, em páginas selecionadas ou em cenários específicos.

Cada regra pode acionar quantos scripts ou introduções de HTML que desejar.

>[!NOTE]
>
>Como o DTM permite inserir código personalizado em sua página, tenha cautela para não criar vulnerabilidades de criação de script entre sites (XSS) (consulte o [guia da OWASP](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) para obter mais informações). O uso de elementos de dados em scripts requer atenção especial. Presuma sempre que a origem dos valores de elementos de dados não seja confiável.

**Para configurar ações para a condição do disparador**

1. Clique em **[!UICONTROL JavaScript / tags de terceiros]** para adicionar um novo script à regra.

   ![](assets/scripts-actions.png)

1. Clique em **[!UICONTROL Adicionar novo script]**.

   ![](assets/scripts-actions2.png)

1. Nomeie o script.
1. Determine como deseja que o script seja acionado e cole o conteúdo desejado na área do texto. ![](assets/scripts-actions3.png)

1. Clique em **[!UICONTROL Salvar código]** e o script será adicionado à fila da regra. ![](assets/scripts-actions4.png)

