---
description: Configuration variables set in AppMeasurement.js.
keywords: Implementação do Analytics
seo-description: Variáveis de configuração definidas no AppMeasurement.js para o Adobe Analytics
seo-title: Variáveis de configuração
solution: Analytics
subtopic: Variáveis
title: Variáveis de configuração
topic: Desenvolvedor e implementação
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# Visão geral das variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. As variáveis de configuração mais comuns que normalmente são definidas no AppMeasurement.js global principal do JavaScript. These variables can be set within the Analytics page-level code and links when appropriate.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Algumas dessas variáveis de configuração podem não se aplicar às necessidades de implementação do seu site.

Alguns dos objetivos ao usar essas variáveis de configuração são:

* Rastrear vários sites ou domínios.
* Fazer compras com qualquer moeda do mundo.
* Capturar dados em vários idiomas.
* Rastreamento de sites (número de arquivos baixados, links para arquivos externos.
* Rastrear links personalizados por razões particulares.

>[!NOTE]
>
>[!DNL AppMeasurement] requer que todas as variáveis de configuração sejam definidas antes da chamada inicial para a função de rastreamento, `t()`. Se as variáveis de configuração forem definidas após a chamada para `t()`, podem ocorrer resultados inesperados. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

Para obter ajuda com variáveis de configuração específicas, consulte os seguintes links:

* [s_account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique o conjunto de relatórios no qual os dados são armazenados e reportados.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Selecione dinamicamente o conjunto de relatórios com base no URL de cada página.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique as regras usadas para determinar o conjunto de relatórios de destino.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Use o objeto DOM para recuperar a seção do URL à qual todas as regras são aplicadas.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Implantar o sinalizador para variáveis preenchidas dinamicamente.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Converta dados de entrada em UTF-8 para armazenamento e relatórios do Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine a taxa de conversão a ser aplicada à receita.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determina qual domínio os cookies `s_cc` e `s_sq` estão definidos.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine the domain for `s_cc` and `s_sq` cookies by specifying the number of periods in the domain of the page URL.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique cookies definidos pelo JavaScript (`s_sq`, `s_cc`, plug-ins) que são inerentemente cookies primários, mesmo com domínios de terceiros `2o7.net` ou `omtrdc.net` .

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine lifespan of a cookie as processed by both JavaScript and data collection servers.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Refer and allow the function to be called at the appropriate location within the JavaScript file.

* [s.registerPreTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.registerPostTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.trackDownLoadLinks: Track links to downloadable files on your site.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.trackExternalLinks: Determine whether any link clicked is an exit link.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [strackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine se os dados do ClickMap são coletados.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclua uma lista separada por vírgulas de extensões de arquivo.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclui uma lista separada por vírgulas de filtros que representam os links que fazem parte do site.

* [s.linkLeaveQueryString: Determine whether or not the query string should be included in the Exit Links and File Download reports.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclua uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Use para relatar um subconjunto específico de links de saída.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Chame a `s_doPlugins` função antes de cada solicitação de imagem.

