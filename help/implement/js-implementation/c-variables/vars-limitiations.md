---
description: Análise avançada das variáveis e suas limitações.
keywords: Implementação do Analytics; ; limitações; limit
seo-description: Análise avançada das variáveis e suas limitações.
seo-title: Variáveis e limitações
solution: Analytics
subtopic: Variáveis
title: Variáveis e limitações
topic: Desenvolvedor e implementação
uuid: 028677 a 7-2132-4 ee 7-9 cc 1-697 c 2 c 09 b 087
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variáveis e limitações

Análise avançada das variáveis e suas limitações.

>[!NOTE]
>
>See [Configuration Variables](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) and [Page Variables](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) for an in-depth look at the most common Analytics variables.

A tabela a seguir contém informações sobre as variáveis do [!DNL Analytics]:

| Variável | Descrição |
|---|---|
| s_account | Determina o conjunto de relatórios no qual os dados são armazenados e relatados. |
| browserHeight | Exibe a altura da janela do navegador. |
| browserWidth | Exibe a largura da janela do navegador. |
| campaign | Identifica campanhas de marketing usadas para trazer visitantes para o site. O valor de *`campaign`* geralmente é retirado de um parâmetro da string de consulta. |
| channel | Geralmente identifica uma seção do site. Por exemplo, um vendedor pode ter seções como Eletrônicos, Brinquedos ou Vestuário. Um site de mídia pode ter seções como Notícias, Esportes ou Negócios. |
| charSet | Converte o conjunto de caracteres da página da Web em UTF-8. |
| colorDepth | Exibe o número de bits usados para exibir cores em cada pixel da tela. |
| connectionType | Indica (no Internet Explorer) se o navegador está configurado em uma conexão LAN ou moderna. |
| cookieDomainPeriods | Determina o domínio em que o cookie da ID do visitante[!DNL Analytics] do  (s_vi) será determinado pela definição do número de períodos no domínio do URL da página. For `www.mysite.com`, *`cookieDomainPeriods`* should be "2." For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3." |
| cookieLifetime | Usada pelos servidores do JavaScript e do [!DNL Analytics] para determinar a duração de um cookie. |
| cookiesEnabled | Indica se um cookie de sessão primária pode ser definido por JavaScript. |
| currencyCode | Determina a taxa de conversão a ser aplicada à receita quando ela entrar nos bancos de dados do [!DNL Analytics]. Os bancos de dados do [!DNL Analytics] armazenam todos os valores monetários de uma moeda de sua escolha. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied. |
| dc | Permite definir o centro de dados para o qual seus dados são enviados. |
| doPlugins | *`doPlugins`* é uma referência à *`s_doPlugins`* função. It allows the *`s_doPlugins`* function to be called at the appropriate location within the JavaScript file. |
| dynamicAccountList | Seleciona dinamicamente um conjunto de relatórios para o qual os dados serão enviados. A variável *`dynamicAccountList`* contém as regras usadas para determinar o conjunto de relatórios de destino. |
| dynamicAccountMatch | Usa o objeto do DOM com a finalidade de recuperar a seção do URL a qual todas as regras em *`dynamicAccountList`* se aplicam. This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' |
| dynamicAccountSelection | Permite selecionar dinamicamente o conjunto de relatórios baseado no URL de cada página. |
| dynamicVariablePrefix | Permite a implantação de variáveis de sinalização que devem ser preenchidas dinamicamente. Os cookies, cabeçalhos de solicitação e parâmetros da string de consulta da imagem estão disponíveis para preenchimento dinâmico. |
| eVarN | Usadas par criar relatórios personalizados dentro do Módulo de conversão[!DNL Analytics] do . Quando uma eVar é definida como um valor para um visitante, o [!DNL Analytics] lembra automaticamente desse valor até sua expiração. Todos os eventos bem-sucedidos que um visitante encontra enquanto o valor eVar está ativo são contabilizados para o valor eVar. |
| events | Registra eventos bem-sucedidos comuns do carrinho de compras e eventos bem-sucedidos personalizados. |
| fpCookieDomainPeriods | Determina o domínio em que o cookie da [!DNL Analytics]ID do visitante[!UICONTROL  do ] (s_vi) será determinado pela definição do número de períodos no domínio da página. |
| hierN | Determina a localização de uma página da hierarquia do site. Essa variável é útil para sites com mais de três níveis na estrutura do site. |
| homepage | Indica (no Internet Explorer) se a página atual foi definida como página inicial do usuário. |
| javaEnabled | Indica se Java estava ativado no navegador. |
| javascriptVersion | Exibe a versão do JavaScript suportada pelo navegador. |
| linkDownloadFileTypes | Uma lista de extensões de arquivo separada por vírgulas. Se o site contém links para arquivos com qualquer uma dessas extensões, as URLs desses links aparecerão no Relatório de [!UICONTROL downloads de arquivo]. |
| linkExternalFilters | Se seu site contém vários links para sites externos e você não deseja rastrear todos os links de saída, use  *`linkExternalFilters`* para criar relatórios sobre um subconjunto específico de links de saída. |
| linkInternalFilters | Determina quais links do site são de saída. Trata-se de uma lista de filtros separada por vírgulas que representa os links que são parte do site. |
| linkLeaveQueryString | Determina se a string de consulta deve ou não ser incluída nos relatórios de [!UICONTROL Links de saída] e [!UICONTROL Downloads de arquivo]. |
| linkName | Uma variável opcional usada no [!UICONTROL rastreamento de link] que determina o nome de um link personalizado, de download ou de saída. A variável *`linkName`* normalmente não é necessária porque o terceiro parâmetro na *`tl()`* função a substitui. |
| linkTrackEvents | Contém os eventos que devem ser enviados com links personalizados, de download e de saída. Essa variável só é considerada se *`linkTrackVars`* contiver "events". |
| linkTrackVars | Uma lista de variáveis separada por vírgulas definidas com links personalizados, de saída e de download. Se *`linkTrackVars`* está definido como "", todas as variáveis com valores são enviadas com dados de link.  |
| linkType | Uma variável opcional usada no rastreamento de link que determina em qual relatório um Nome de link ou URL aparece (Personalizado, Download ou Links de saída). *`linkType`* normalmente não é necessária porque o segundo parâmetro na *`tl()`* função o substitui. |
| mediaLength | Especifica o tamanho total da mídia que está sendo reproduzida. |
| mediaName | Especifica o nome do vídeo ou item de mídia. Ela só está disponível pela [!UICONTROL API de inserção de dados] e [!UICONTROL fonte de dados de processamento completo]. |
| mediaPlayer | Especifica o player usado para consumir um item de mídia ou vídeo. |
| mediaSession | Especifica os segmentos de um vídeo ou ativo de mídia consumido. |
| Media.trackEvents | Identifica quais eventos devem ser enviados com uma ocorrência de mídia. Ela só é aplicável com JavaScript e [!UICONTROL ActionSource]. |
| Media.trackVars | Identifica quais variáveis devem ser enviadas com uma ocorrência de mídia. Ela só é aplicável com JavaScript e [!UICONTROL ActionSource]. |
| mobile | Controla a ordem em que os cookies e as IDs do assinante são usados para identificar visitantes. |
| s_objectID | Uma variável global que deve ser definida no evento [!UICONTROL onClick] de um link. Ao criar uma ID de objeto única para um link ou um local de link em uma página, você pode melhorar o rastreamento ou usar o mapa de cliques do visitante para informar sobre um tipo de link ou um local, em vez do URL do link. |
| pageName | Contém o nome de cada página de seu site. Se *`pageName`* for deixada em branco, a URL será usada para representar o nome da página no [!DNL Analytics]. |
| pageType | Usada para designar uma página de erro 404 (Página não encontrada). Ela só tem um valor possível, que é "errorPage". Em uma Página de erro 404, a variável *`pageName`* não deve ser preenchida. |
| pageURL | Em casos raros, a URL da página não é a URL que você deseja reportar no [!DNL Analytics]. To accommodate these situations, [!DNL Analytics] offers the *`pageURL`* variable, which overrides the actual URL of the page. |
| plug-ins | Nos navegadores baseados em Netscape e Mozilla, lista os plug-ins instalados no navegador. |
| products | Usada para rastrear produtos e categorias de produto, assim como quantidade e preço da compra. A variável *`products`* deve ser sempre definida juntamente com um evento bem-sucedido. Optionally, the *`products`* variable can track custom numeric and currency events, as well as [!UICONTROL Merchandising] eVars. |
| propN | Usada para criar relatórios personalizados dentro do Módulo de tráfego[!DNL Analytics] do . A [!UICONTROL props] pode ser usada como contadores (para contar o número de vezes que uma exibição de página é enviada), para relatório de definição de caminho ou em relatórios de correlação. |
| purchaseID | Usada para impedir que um pedido seja contado várias vezes pelo [!DNL Analytics]. Whenever the purchase event is used on your site, you should use the *`purchaseID`* variable. |
| referrer | Restaura as informações do referenciador. |
| resolution | Exibe a resolução do monitor do visitante que exibe a página da Web. |
| server | Mostra o domínio de uma página da Web (para mostrar para quais domínios as pessoas vão) ou o servidor que serve a página (para uma referência rápida de balanceamento de carga). |
| state | Captura o estado em que um visitante de seu site reside. |
| trackDownloadLinks | Definir *`trackDownloadLinks`* como'true'se você deseja rastrear links para arquivos baixáveis no site. If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* determines which links are downloadable files. |
| trackExternalLinks | If *`trackExternalLinks`* is 'true,' *`linkInternalFilters`* and *`linkExternalFilters`* determines whether any link clicked is an exit link. |
| trackingServer | Usada para a implementação de cookies primários para especificar o domínio em que a solicitação de imagem e o cookie são gravados. Usada para páginas não seguras.  |
| trackingServerSecure | Usada para a implementação de cookies primários para especificar o domínio em que a solicitação de imagem e o cookie são gravados. Usada para páginas seguras. |
| trackInlineStats | Determina se os dados do mapa de cliques do visitante estão reunidos. |
| transactionID | Associa dados offline a uma transação online (como um cliente potencial ou compra gerada online). Cada *`transactionID`* única enviada para a Adobe é registrada em preparação para um upload de [!UICONTROL Fontes de dados ]de informações offline sobre essa transação. Consulte o [Guia de fontes de dados](https://marketing.adobe.com/resources/help/en_US/sc/datasources/) |
| s_usePlugins | Se a variável *`s_doPlugins`* está disponível e contém código útil, [!UICONTROL s_ useplugins] deve ser definido como'true '. When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request. |
| visitorID | Visitors may be identified by the *`visitorID`* tag, or by IP address/User Agent. The *`visitorID`* may be up to 100 alphanumeric characters and must not contain a hyphen. |
| visitorNamespace | If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. Essa variável é usada para identificar o domínio com o qual os cookies são definidos. Se *`visitorNamespace`* for alterada, todos os visitantes relatados no [!DNL Analytics] podem ser tornar novos visitantes. Em resumo, não altere essa variável sem aprovação de um consultor da Adobe. |
| zip | Captura o CEP do endereço de um visitante de seu site. |

