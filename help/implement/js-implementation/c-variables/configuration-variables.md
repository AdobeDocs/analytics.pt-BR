---
description: Variáveis de configuração definidas em AppMeasurement.js.
keywords: Implementação do Analytics
seo-description: Configuration variables set in AppMeasurement.js for Adobe Analytics
seo-title: Variáveis de configuração
solution: Analytics
subtopic: Variáveis
title: Variáveis de configuração
topic: Desenvolvedor e implementação
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 9212d70ab8fd7bc0ccfb7e781a92b1731f0a40bd

---


# Configuration variables overview

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. As variáveis de configuração mais comuns que normalmente são definidas no AppMeasurement.js global principal do JavaScript. Essas variáveis podem ser definidas no código de nível de página do Analytics e nos links, quando apropriado.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Algumas dessas variáveis de configuração podem não se aplicar às necessidades de implementação do seu site.

Alguns dos objetivos ao usar essas variáveis de configuração são:

* Rastrear vários sites ou domínios.
* Fazer compras com qualquer moeda do mundo.
* Capturar dados em vários idiomas.
* Rastreamento de sites (número de arquivos baixados, links para arquivos externos.
* Rastrear links personalizados por razões particulares.

>[!NOTE]
>
>[!DNL AppMeasurement] requer que todas as variáveis de configuração sejam definidas antes da chamada inicial para a função de rastreamento, `t()`. If configuration variables are set after the call to , unexpected results may occur. `t()` To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

For help with specific configuration variables, click any of the following links:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique o conjunto de relatórios no qual os dados são armazenados e reportados.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Selecione dinamicamente o conjunto de relatórios com base no URL de cada página.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specify the rules used for determining the destination report suite.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Use o objeto DOM para recuperar a seção do URL à qual todas as regras são aplicadas.

* [s.dynamicVariablePrefix: Deploy flagging for dynamically-populated variables.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.charSet: Convert incoming data to UTF-8 for storage and reporting by Analytics.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.currencyCode: Determine the conversion rate to apply to revenue.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.cookieDomain: Determines which domain the  and  cookies are set.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_cc``s_sq`

* [s.cookieDomainPeriods: Determine the domain for  and  cookies by specifying the number of periods in the domain of the page URL.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_cc``s_sq`

* [s.fpCookieDomainPeriods: Specify cookies set by JavaScript (, , plug-ins) that are inherently first-party cookies, even with third-party  or  domains.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_sq``s_cc``2o7.net``omtrdc.net`

* [s.cookieLifetime: Determine lifespan of a cookie as processed by both JavaScript and data collection servers.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.doPlugins: Refer and allow the function to be called at the appropriate location within the JavaScript file.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Função para tomar como parâmetros o retorno de chamada (uma função) e os parâmetros para essa função.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Função para tomar como parâmetros o retorno de chamada (uma função) e os parâmetros para essa função.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Rastrear links para arquivos baixáveis do site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine se algum link clicado é um link de saída.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine se os dados do ClickMap são coletados.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclua uma lista separada por vírgulas de extensões de arquivo.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclui uma lista separada por vírgulas de filtros que representam os links que fazem parte do site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine se a string de consulta deve ou não ser incluída nos relatórios de Links de saída e Downloads de arquivo.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclua uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Use para relatar um subconjunto específico de links de saída.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Chame a `s_doPlugins` função antes de cada solicitação de imagem.

