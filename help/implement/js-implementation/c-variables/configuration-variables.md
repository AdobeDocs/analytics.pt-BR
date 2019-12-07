---
description: Variáveis de configuração definidas no AppMeasurement.js.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de configuração
topic: Developer and implementation
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visão geral das variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. As variáveis de configuração mais comuns tipicamente definidas no JavaScript global principal (AppMeasurement.js. Essas variáveis podem ser definidas no código de página e nos links do Analytics, quando apropriado.

Nem todas essas variáveis aparecem no código por padrão ao gerar o código por meio da **[!UICONTROL Ferramenta de administração]** &gt; **[!UICONTROL Gerenciador de código]**. Algumas dessas variáveis de configuração podem não se aplicar às necessidades de implementação do site.

Alguns dos objetivos ao usar essas variáveis de configuração são:

* Rastrear vários sites ou domínios
* Fazer compras com qualquer moeda do mundo
* Capturar dados em vários idiomas
* Rastreamento de sites (número de arquivos baixados, links para arquivos externos).
* Rastrear links personalizados por razões particulares

> [!NOTE] [!DNL AppMeasurement] requer que todas as variáveis de configuração sejam definidas antes da chamada inicial para a função de rastreamento, `t()`. Se as variáveis de configuração forem definidas após a chamada para `t()`, podem ocorrer resultados inesperados. Para garantir a coleta de dados adequada, todas as variáveis de configuração devem estar acima da função `doPlugins`.

Para obter ajuda com variáveis de configuração específicas, clique em qualquer um dos links a seguir:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique o conjunto de relatórios no qual os dados são armazenados e reportados.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Selecione dinamicamente o conjunto de relatórios com base no URL de cada página.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Especifique as regras usadas para determinar o conjunto de relatórios de destino.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Use o objeto DOM para recuperar a seção do URL à qual todas as regras são aplicadas.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html): Implantar o sinalizador para variáveis preenchidas dinamicamente.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Converta dados de entrada em UTF-8 para armazenamento e relatórios do Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Determine a taxa de conversão a ser aplicada à receita.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html): Determina qual domínio os cookies `s_cc` e `s_sq` estão definidos.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html): Determine o domínio para `s_cc` e os `s_sq` cookies especificando o número de períodos no domínio do URL da página.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html): Especifique cookies definidos pelo JavaScript (`s_sq`, `s_cc`, plug-ins) que são inerentemente cookies primários, mesmo com domínios de terceiros `2o7.net` ou `omtrdc.net` .

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html): Determine a duração de um cookie como processado pelo JavaScript e pelos servidores de coleta de dados.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Consulte e permita que a função seja chamada no local apropriado no arquivo JavaScript.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Função para tomar como parâmetros o retorno de chamada (uma função) e os parâmetros para essa função.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Rastrear links para arquivos baixáveis do site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Determine se algum link clicado é um link de saída.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Determine se os dados do ClickMap são coletados.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html): Inclua uma lista separada por vírgulas de extensões de arquivo.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackintfilters.html): Inclui uma lista separada por vírgulas de filtros que representam os links que fazem parte do site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Determine se a string de consulta deve ou não ser incluída nos relatórios de Links de saída e Downloads de arquivo.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Inclua uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html): Use para relatar um subconjunto específico de links de saída.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html): Chame a `s_doPlugins` função antes de cada solicitação de imagem.

* [s.useForcedlinkTracking](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-usedforcedlinktracking.html): Desativa o rastreamento forçado de links para alguns navegadores.

* [s.linkType](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktype.html): Define o tipo de link para download, saída ou personalizado.

* [s.linkName](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html): Define o nome que aparece no relatório de download, saída ou link personalizado.

* [s.ForcedlinkTrackingTimeout](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-forcedlinktrackingtimeout.html): Define o tempo máximo de espera durante o rastreamento.

* [s.linkTrackEvents](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackingevents.html): Desativa o rastreamento forçado de links para alguns navegadores.

* [s.linkUrl](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkurl.html): Define o URL do link.

* [s.linkObject](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkobject.html): Faz referência a um objeto clicado.
