---
description: Dados da tabela que descrevem as colunas no feed de dados.
keywords: Feed de dados;colunas
subtopic: data feeds
title: Referência da coluna de dados
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '3642'
ht-degree: 66%

---

# Referência da coluna de dados

Use esta página para saber quais dados estão contidos em cada coluna. A maioria das implementações não usa cada coluna, portanto, essa página pode ser referenciada ao determinar quais colunas incluir em uma exportação de feed de dados.

>[!IMPORTANT]
>
>Para qualquer coluna (por exemplo, uma que esteja definida como 255 caracteres), devido à adição de valores de saída de caracteres em uma cadeia de caracteres. Lembre-se desses caracteres adicionais em potencial se sua implementação envia regularmente valores que excedem os limites de caracteres.

## Colunas, descrições e tipos de dados

>[!NOTE]
>
>A maioria das colunas contém uma coluna semelhante com um prefixo `post_`. Colunas de publicação contêm valores após a lógica do lado do servidor, regras de processamento e regras VISTA. A Adobe recomenda usar tais colunas na maioria dos casos. Consulte [Perguntas frequentes sobre feeds de dados](../df-faq.md) para obter mais informações.

As atualizações anteriores desta tabela podem ser encontradas no [histórico de confirmações desta página no GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Nome da coluna | Descrição da coluna | Tipo de dados |
| --- | --- | --- |
| **`accept_language`** | Lista todas as linguagens aceitas, conforme indicado no cabeçalho Linguagem aceita de HTTP em uma solicitação de imagem. | char(20) |
| **`adload`** | Cargas de anúncios de mídia | varchar(255) |
| **`aemassetid`** | Uma variável de vários valores correspondente às IDs de ativos (GUIDs) de um conjunto de Adobe Experience Manager Assets. Incrementa eventos de impressão. | texto |
| **`aemassetsource`** | Identifica a origem do evento do ativo. Usado no Adobe Experience Manager. | varchar(255) |
| **`aemclickedassetid`** | ID de ativo referente a um ativo do Adobe Experience Manager. Incrementa eventos de clique. | varchar(255) |
| **`browser`** | Uma ID numérica que representa o navegador. Faz referência à tabela de pesquisa `browser.tsv`. | int unsigned |
| **`browser_height`** | A dimensão [Altura do Navegador](/help/components/dimensions/browser-height.md). | smallint unsigned |
| **`browser_width`** | A [Largura do Navegador](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`c_color`** | Profundidade de bits da paleta de cores. Usado como parte do cálculo da dimensão [Intensidade de cor](/help/components/dimensions/color-depth.md). O AppMeasurement usa a função JavaScript `screen.colorDepth()`. | char(20) |
| **`campaign`** | A dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). | varchar(255) |
| **`carrier`** | Variável de integração da Adobe Advertising Especifica a operadora de celular. O valor-chave da [pesquisa dinâmica](dynamic-lookups.md) `carrier.tsv`. | varchar(100) |
| **`ch_hdr`** | Dicas do cliente coletadas por meio do cabeçalho de solicitação HTTP. | texto |
| **`ch_js`** | Dicas do cliente coletadas por meio da API JavaScript de dicas do cliente de usuário-agente. | texto |
| **`channel`** | A dimensão [Seções do site](/help/components/dimensions/site-section.md). | varchar(100) |
| **`clickmaplink`** | Link para o Activity Map | varchar(255) |
| **`clickmaplinkbyregion`** | Link por região do Activity Map | varchar(255) |
| **`clickmappage`** | Página do Activity Map | varchar(255) |
| **`clickmapregion`** | Região do Activity Map | varchar(255) |
| **`code_ver`** | Versão da API ou SDK cliente usada para compilar e enviar a solicitação de imagem. | char(16) |
| **`color`** | ID de Intensidade de cor com base no valor da coluna `c_color`. Faz referência à tabela de pesquisa `color_depth.tsv`. | smallint unsigned |
| **`connection_type`** | Uma ID numérica que representa o tipo de conexão. A dimensão [Tipo de conexão](/help/components/dimensions/connection-type.md). Faz referência à tabela de pesquisa `connection_type.tsv`. | tinyint unsigned |
| **`cookies`** | A dimensão [Suporte a cookies](/help/components/dimensions/cookie-support.md).<br>Y: Ativado<br>N: Desativado<br>U: Desconhecido | char(1) |
| **`country`** | Uma ID numérica que representa o país do visitante. Faz referência à tabela de pesquisa `country.tsv`. | smallint unsigned |
| **`ct_connect_type`** | Relacionado à coluna `connection_type`. Os valores mais comuns são LAN/Wifi, Operadora de celular e Modem. | char(20) |
| **`curr_factor`** | Determina a posição decimal da moeda e é usado para conversão de moedas. Por exemplo, USD usa duas casas decimais, então esse valor de coluna seria `2`. | tinyint |
| **`curr_rate`** | A taxa de câmbio de quando a transação ocorreu. A Adobe formou uma parceria com a XE para determinar a taxa de câmbio atual. | decimal(24,12) |
| **`currency`** | O código de moeda usado durante a transação. Defina usando [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| **`cust_hit_time_gmt`** | Somente conjuntos de relatório com carimbos de data e hora habilitados. O carimbo de data e hora enviado com a ocorrência, com base no horário UNIX®. | int |
| **`cust_visid`** | A ID de visitante personalizada, se definida usando [`visitorID`](/help/implement/vars/config-vars/visitorid.md). | varchar(255) |
| **`customer_perspective`** | Determina se a ocorrência é uma ocorrência em segundo plano móvel. Consulte [Sessões sensíveis ao contexto](/help/components/vrs/vrs-mobile-visit-processing.md) para obter mais informações. | tinyint unsigned |
| **`daily_visitor`** | Um sinalizador que determina se a ocorrência é um novo visitante diário. | tinyint unsigned |
| **`dataprivacyconsentoptin`** | A dimensão [Consentimento de aceitação](/help/components/dimensions/cm-opt-in.md). Vários valores podem estar presentes por ocorrência, separados por uma barra vertical (`\|`). Os valores válidos incluem `DMP` e `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | A dimensão [Recusa de gerenciamento de consentimento](/help/components/dimensions/cm-opt-out.md). Vários valores podem estar presentes por ocorrência, separados por uma barra vertical (`\|`). Os valores válidos incluem `SSF`, `DMP` e `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Um valor que identifica se o consentimento é adquirido para enviar dados do Adobe Analytics por meio do Adobe Advertising para provedores de publicidade de terceiros (como o Google). Consulte [Consentimento de publicidade](/help/components/dimensions/ad-consent.md) para mais informações. | varchar(100) |
| **`date_time`** | O horário da ocorrência em formato legível, com base no fuso horário do conjunto de relatórios. | datetime |
| **`domain`** | A dimensão [Domínio](/help/components/dimensions/domain.md). Com base no ponto de acesso de Internet do visitante. | varchar(100) |
| **`duplicate_events`** | Lista todos os eventos que são contados como duplicados. | varchar(255) |
| **`duplicate_purchase`** | Um sinalizador que determina se o evento de compra para esta ocorrência é ignorado porque está duplicado. | tinyint unsigned |
| **`duplicated_from`** | Somente usado em conjuntos de relatórios contendo uma cópia da ocorrência com regras VISTA. Indica de qual conjunto de relatórios a ocorrência foi copiada. | varchar(40) |
| **`ef_id`** | A `ef_id` usada em integrações da Adobe Advertising  | varchar(255) |
| **`evar1 - evar250`** | Variáveis personalizadas 1-250. Usado nas dimensões [eVar](/help/components/dimensions/evar.md). Cada organização usa eVars de maneiras diferentes. O melhor lugar para obter mais informações sobre como sua organização preenche as respectivas eVars seria em um [documento de design de solução](/help/implement/prepare/solution-design.md) específico para sua organização. | varchar(255) |
| **`event_list`** | Lista separada por vírgulas de IDs numéricas que representam eventos acionados na ocorrência. Inclui tanto eventos padrão quanto [eventos personalizados 1-1000](/help/components/metrics/custom-events.md). Usa a pesquisa `event.tsv`. | texto |
| **`exclude_hit`** | Um sinalizador que determina se a ocorrência é excluída dos relatórios. A coluna `visit_num` não é incrementada para hits excluídos.<br>1: Não usado. Parte de um recurso raspado.<br>2: Não usado. Parte de um recurso raspado.<br>3: Não está mais em uso. Exclusão de agente usuário<br>4: exclusão com base no endereço IP<br>5: faltam informações essenciais do hit, como `page_url`, `pagename`, `page_event` ou `event_list`<br>6: o JavaScript não processou corretamente o hit<br>7: exclusão específica da conta, como em regras VISTA<br>8: não usada. Exclusão específica da conta alternativa.<br>9: Não usado. Parte de um recurso raspado.<br>10: Código monetário inválido<br>11: Falta um carimbo na ocorrência ou um conjunto de relatórios no carimbo, ou uma ocorrência continha um carimbo em um conjunto de relatórios sem carimbo<br>12: Não usado. Parte de um recurso raspado.<br>13: Não usado. Parte de um recurso raspado.<br>14: Ocorrência do Target que não corresponde a uma ocorrência do Analytics<br>15: Não usado no momento.<br>16: Ocorrência da Advertising Cloud que não correspondeu a uma ocorrência do Analytics | tinyint unsigned |
| **`first_hit_page_url`** | O primeiro URL do visitante. | varchar(255) |
| **`first_hit_pagename`** | A dimensão [Página de entrada original](/help/components/dimensions/entry-dimensions.md). O nome original da página de entrada do visitante. | varchar(100) |
| **`first_hit_ref_domain`** | A dimensão [Domínio referenciador original](/help/components/dimensions/original-referring-domain.md). Baseado em `first_hit_referrer`. O primeiro domínio de referência do visitante. | varchar(100) |
| **`first_hit_ref_type`** | Uma ID numérica que representa o tipo do primeiro referenciador do visitante. Faz referência à tabela de pesquisa `referrer_type.tsv`. | tinyint unsigned |
| **`first_hit_referrer`** | O primeiro URL de referência do visitante. | varchar(255) |
| **`first_hit_time_gmt`** | Carimbo de data e hora da primeira ocorrência de um(a) visitante, com base no horário UNIX®. | int |
| **`geo_city`** | O nome da cidade na qual a ocorrência foi originada, com base no IP. Usada na dimensão [Cidades](/help/components/dimensions/cities.md). | char(32) |
| **`geo_country`** | A abreviação do país no qual a ocorrência foi originada, com base no IP. Usado na dimensão [Países](/help/components/dimensions/countries.md). | char(4) |
| **`geo_dma`** | Uma ID numérica da área demográfica na qual a ocorrência foi originada, com base no IP. Usado na dimensão [US DMA](/help/components/dimensions/us-dma.md). | int unsigned |
| **`geo_region`** | O nome do estado ou região em que a ocorrência foi originada, com base no IP. Usado na dimensão [Regiões](/help/components/dimensions/regions.md). | char(32) |
| **`geo_zip`** | O código postal no qual a ocorrência foi originada, com base no IP. Ajuda a preencher a dimensão [CEP](/help/components/dimensions/zip-code.md). Consulte também `zip`. | varchar(16) |
| **`hit_source`** | A origem da ocorrência. As fontes de ocorrência 1, 2 e 6 são faturadas. <br>1: Solicitação de imagem padrão sem carimbo de data e hora <br>2: Solicitação de imagem padrão com carimbo de data e hora <br>3: Carregamento de fonte de dados ao vivo com carimbos de data e hora <br>4: Não utilizado <br>5: Upload de fonte de dados genérica <br>6: Carregamento completo da fonte de dados de processamento <br>7: Carregamento da fonte de dados TransactionID <br>8: Deixar de ser utilizado; Versões anteriores das fontes de dados da Adobe Advertising Cloud <br>9: Deixar de ser utilizado; Métricas de resumo do Adobe Social <br>10: Encaminhamento do lado do servidor do Audience Manager usado | tinyint unsigned |
| **`hit_time_gmt`** | O carimbo de data e hora de quando os servidores de coleta de dados de ocorrências da Adobe receberam a ocorrência, com base no horário UNIX®. | int |
| **`hitid_high`** | Usado em combinação com `hitid_low` para identificar uma ocorrência. | bigint unsigned |
| **`hitid_low`** | Usado em combinação com `hitid_high` para identificar uma ocorrência. | bigint unsigned |
| **`hourly_visitor`** | Um sinalizador que determina se a ocorrência é um novo visitante por hora. | tinyint unsigned |
| **`ip`** | O endereço IPv4, com base no cabeçalho HTTP da solicitação de imagem. Mutualmente exclusivo de `ipv6`; se essa coluna contiver um endereço IP não ofuscado, `ipv6` está em branco. | char(20) |
| **`ipv6`** | O endereço IPv6 compactado, se disponível. Mutualmente exclusivo de `ip`; se essa coluna contiver um endereço IP não ofuscado, `ip` está em branco. | varchar(40) |
| **`j_jscript`** | A versão do JavaScript suportada pelo navegador. | char(5) |
| **`java_enabled`** | O [[!UICONTROL Java habilitado]](/help/components/dimensions/java-enabled.md). <br>Y: Ativado <br>N: Desativado <br>U: Desconhecido | char(1) |
| **`javascript`** | Uma ID de pesquisa da versão do JavaScript, com base em `j_jscript`. Faz referência à tabela de pesquisa `javascript_version`. | tinyint unsigned |
| **`language`** | Uma ID numérica que representa o idioma do visitante. Faz referência à tabela de pesquisa `languages.tsv`. | smallint unsigned |
| **`last_hit_time_gmt`** | Carimbo de data e hora (em horário UNIX®) da ocorrência anterior. Usado para calcular a dimensão [[!UICONTROL Dias desde a última visita]](/help/components/dimensions/days-since-last-visit.md). | int |
| **`last_purchase_num`** | A dimensão [Fidelização do cliente](/help/components/dimensions/customer-loyalty.md). O número de compras que o visitante fez anteriormente. <br>0: Nenhuma compra anterior (não é um cliente) <br>1: 1 compra prévia (novo cliente) <br>2: 2 compras anteriores (cliente recorrente) <br>3: 3 ou mais compras anteriores (cliente fidelizado) | int unsigned |
| **`last_purchase_time_gmt`** | Usado na dimensão [[!UICONTROL Dias desde a última compra]](/help/components/dimensions/days-since-last-purchase.md). Carimbo de data e hora (em horário UNIX®) da última compra feita. Para compras feitas pela primeira vez e visitantes que ainda não fizeram uma compra, esse valor é `0`. | int |
| **`latlon1`** | Localização (abaixo de 10 km) | varchar(255) |
| **`latlon23`** | Localização (abaixo de 100 m) | varchar(255) |
| **`latlon45`** | Localização (abaixo de 1 m) | varchar(255) |
| **`mc_audiences`** | Lista de IDs de segmento do Audience Manager à qual o visitante pertence. A coluna `post_mc_audiences` altera o delimitador para `--**--`. | texto |
| **`mcvisid`** | ID de visitante da Experience Cloud. Número de 128 bits que consiste em dois números concatenados de 64 bits arredondados para 19 dígitos. | varchar(255) |
| **`mobile_id`** | Se o(a) visitante estiver usando um dispositivo móvel, o ID numérico do dispositivo. O valor-chave da [pesquisa dinâmica](dynamic-lookups.md) `mobile_attributes.tsv`. | int |
| **`mobileaction`** | Ação em dispositivo móvel. Coletado automaticamente quando `trackAction` é chamado em implementações móveis. Permite a criação de caminhos de ação automática no aplicativo. | varchar(100) |
| **`mobileappid`** | ID do aplicativo móvel. Armazena o nome e a versão do aplicativo no seguinte formato: `[AppName] [BundleVersion]`.  | varchar(255) |
| **`mobileappperformanceappid`** | Usado no conector de dados Apteligent. O ID do aplicativo usado no Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Usado no conector de dados Apteligent. O ID de falha usado no Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Usado no conector de dados [!DNL Appfigures]. ID do objeto na loja de aplicativos. | varchar(255) |
| **`mobilebeaconmajor`** | Beacon do Mobile Services maior | varchar(100) |
| **`mobilebeaconminor`** | Beacon do Mobile Services menor | varchar(100) |
| **`mobilebeaconproximity`** | Proximidade de beacon do Mobile Services | varchar(255) |
| **`mobilebeaconuuid`** | UUID de beacon do Mobile Services | varchar(100) |
| **`mobilecampaigncontent`** | O nome ou a ID do conteúdo que exibiu o link. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| **`mobilecampaignmedium`** | Meio de marketing, como banner ou email. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| **`mobilecampaignname`** | O nome da campanha, também armazenado na variável da campanha. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| **`mobilecampaignsource`** | Referenciador original, como informativos ou redes sociais. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| **`mobilecampaignterm`** | Palavras-chave pagas ou outros termos que você deseja rastrear com essa aquisição. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| **`mobiledayofweek`** | Dia da semana no qual o aplicativo foi inicializado. | varchar(255) |
| **`mobiledayssincefirstuse`** | Número de dias desde a primeira execução do aplicativo. | varchar(255) |
| **`mobiledayssincelastuse`** | Número de dias desde a execução mais recente do aplicativo. | varchar(255) |
| **`mobiledeeplinkid`** | Coletada da variável de dados de contexto `a.deeplink.id`. Usado nos relatórios de aquisição como um identificador para o link de aquisição móvel. | varchar(255) |
| **`mobiledevice`** | Nome do dispositivo móvel. No iOS, é armazenado em uma sequência de caracteres de 2 dígitos. O primeiro número representa a geração do dispositivo, e o segundo representa a família do dispositivo. | varchar(255) |
| **`mobilehourofday`** | Define a hora do dia em que o aplicativo foi inicializado. Segue um formato numérico de 24 horas. | varchar(255) |
| **`mobileinstalldate`** | Data de instalação móvel. Fornece a data da primeira vez que um usuário abriu o aplicativo móvel. | varchar(255) |
| **`mobilelaunchnumber`** | Há um aumento de um cada vez que o aplicativo é inicializado. | varchar(255) |
| **`mobilemessagebuttonname`** | Coletada da variável de dados de contexto `a.message.button.id`. Usado para mensagens no aplicativo para identificar o botão que fechou a mensagem. | varchar(100) |
| **`mobilemessageid`** | ID da mensagem no aplicativo | varchar(255) |
| **`mobilemessageonline`** | Mensagens no aplicativo online | varchar(255) |
| **`mobilemessagepushoptin`** | Coletada da variável de dados de contexto `a.push.optin`. Defina como &quot;true&quot; quando o usuário optar por enviar mensagens de push; caso contrário, o valor será &quot;false&quot;. | varchar(255) |
| **`mobilemessagepushpayloadid`** | Coletada da variável de dados de contexto `a.push.payloadid`. Usado em mensagens de push como o identificador de carga. | varchar(255) |
| **`mobileosversion`** | Versão do sistema operacional do Mobile Services | varchar(255) |
| **`mobileplaceaccuracy`** | Coletada da variável de dados de contexto `a.loc.acc`. Indica a precisão do GPS em metros no momento da coleta. | varchar(255) |
| **`mobileplacecategory`** | Coletada da variável de dados de contexto `a.loc.category`. Descreve a categoria de um local específico. | varchar(255) |
| **`mobileplaceid`** | Coletada da variável de dados de contexto `a.loc.id`. Identificador para um determinado ponto de interesse. | varchar(255) |
| **`mobilepushoptin`** | Aceitação por push do Mobile Services | varchar(255) |
| **`mobilepushpayloadid`** | ID do conteúdo de push do Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Conteúdo de inicialização do Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Meio de lançamento do Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Fonte de lançamento do Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Termo de lançamento do Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | Coletada da variável de dados de contexto `a.launch.campaign.trackingcode`. Usado na aquisição como o código de rastreamento para a campanha de lançamento. | varchar(255) |
| **`mobileresolution`** | Resolução do dispositivo móvel. `[Width] x [Height]` em pixels. | varchar(255) |
| **`monthly_visitor`** | Um sinalizador que determina se o visitante é único no mês atual. | tinyint unsigned |
| **`mvvar1`** - `mvvar3` | [Listar valores de variáveis](/help/implement/vars/page-vars/list.md). Contém uma lista delimitada de valores personalizados dependendo da implementação. As colunas `post_mvvar1` - `post_mvvar3` substituem o delimitador original por `--**--`. | texto |
| **`mvvar1_instances`** - `mvvar3_instances` | Os valores da variável de lista que foram definidos na ocorrência atual. Substitui o delimitador original por `--**--`. As colunas `post` normalmente não contêm dados. | texto |
| **`new_visit`** | Um sinalizador que determina se a ocorrência atual é uma nova visita. Definido pelo Adobe após 30 minutos de inatividade da visita. | tinyint unsigned |
| **`os`** | Uma ID numérica que representa o sistema operacional do visitante. Com base na coluna `user_agent`. O valor-chave da pesquisa padrão `operating_system.tsv` e da [pesquisa dinâmica](dynamic-lookups.md) `operating_system_type.tsv`. | int unsigned |
| **`page_event`** | O tipo de ocorrência que é enviado na solicitação da imagem (ocorrência padrão, link de download, link personalizado, link de saída). [Pesquisa de evento da página](datafeeds-page-event.md). | tinyint unsigned |
| **`page_event_var1`** | Somente usado em solicitações de imagem de rastreamento de link. O URL dos links clicados, seja de download, de saída ou personalizados. | texto |
| **`page_event_var2`** | Somente usado em solicitações de imagem de rastreamento de link. O nome personalizado (se especificado) do link. Define o [Link personalizado](/help/components/dimensions/custom-link.md), o [Link de download](/help/components/dimensions/download-link.md) ou o [Link de saída](/help/components/dimensions/exit-link.md), dependendo do valor em `page_event`. | varchar(100) |
| **`page_type`** | A dimensão [Páginas não encontradas](/help/components/dimensions/pages-not-found.md), que é normalmente usada para páginas 404. | char(20) |
| **`page_url`** | O URL da ocorrência. Observe que `post_page_url` é removido para solicitações de imagem de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) e usa um tipo de dados de varchar(255). | texto |
| **`pagename`** | A dimensão [Página](/help/components/dimensions/page.md). Se a variável [`pagename`](/help/implement/vars/page-vars/pagename.md) estiver vazia, o Analytics usa `page_url`. | varchar(100) |
| **`pagename_no_url`** | Semelhante a `pagename`, exceto que não retorna a `page_url`. Somente a coluna `post` está disponível. | varchar(100) |
| **`paid_search`** | Um sinalizador que determina se a ocorrência corresponde à detecção de pesquisa paga. | tinyint unsigned |
| **`persistent_cookie`** | Usado na dimensão [Suporte à cookie persistente](/help/components/dimensions/persistent-cookie-support.md). Indica se o visitante suporta cookies que não são descartados depois de cada ocorrência. | char(1) |
| **`pointofinterest`** | Nome do ponto de interesse do Mobile Services | varchar(255) |
| **`pointofinterestdistance`** | Centro de distância do Mobile Services ao ponto de interesse | varchar(255) |
| Colunas **`post_`** | Contém o valor usado por último em relatórios. Cada coluna de publicação contém valores após a lógica do lado do servidor, regras de processamento e regras VISTA. A Adobe recomenda usar tais colunas na maioria dos casos. | Consulte a respectiva coluna de não-publicação |
| **`product_list`** | A variável de página [`products`](/help/implement/vars/page-vars/products.md). Ajuda a preencher várias dimensões e métricas, incluindo [Categoria](/help/components/dimensions/category.md), [Produto](/help/components/dimensions/product.md), [Unidades](/help/components/metrics/units.md) e [Receita](/help/components/metrics/revenue.md). | texto |
| **`prop1`** - `prop75` | Variáveis de tráfego personalizadas 1 - 75. Usado nas dimensões [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`purchaseid`** | Identificador exclusivo de uma compra, definido usando a variável [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Usado pela coluna `duplicate_purchase`. | char(20) |
| **`quarterly_visitor`** | Um sinalizador que determina se a ocorrência é um novo visitante trimestral. | tinyint unsigned |
| **`ref_domain`** | A dimensão [Domínio referenciador](/help/components/dimensions/referring-domain.md). Com base na coluna `referrer`. | varchar(100) |
| **`ref_type`** | Uma ID numérica que representa o tipo de referência para a ocorrência. Usado na dimensão [Tipo de referenciador](/help/components/dimensions/referrer-type.md). <br>1: Dentro do site<br>2: Outros sites da web <br>3: Mecanismos de pesquisa <br>4: Disco rígido <br>5: USENET <br>6: Digitado/Marcado (sem referenciador) <br>7: E-mail <br>8: Sem JavaScript <br>9: Redes sociais | tinyint unsigned |
| **`referrer`** | A dimensão [Referenciador](/help/components/dimensions/referrer.md). Observe que, embora o `referrer` use um tipo de dados de varchar(255), o `post_referrer` usa um tipo de dados de varchar(244). | varchar(255) |
| **`resolution`** | Uma ID numérica que representa a resolução do monitor. Usado na dimensão [Resolução do monitor](/help/components/dimensions/monitor-resolution.md). Usa uma tabela de pesquisa `resolution.tsv`. | smallint unsigned |
| **`s_kwcid`** | A ID de palavra-chave usada em integrações da Adobe Advertising  | varchar(255) |
| **`s_resolution`** | Valor bruto da resolução da tela. Coletado usando a função do JavaScript `screen.width x screen.height`. | char(20) |
| **`search_engine`** | Uma ID numérica que representa o mecanismo de pesquisa que direcionou o visitante ao seu site. Usado nas dimensões [Mecanismo de Pesquisa](/help/components/dimensions/search-engine.md). Faz referência à tabela de pesquisa `search_engines.tsv`. | smallint unsigned |
| **`search_page_num`** | Usado pela dimensão [Todas as classificações da página de pesquisa](/help/components/dimensions/all-search-page-rank.md). Indica em qual página dos resultados de pesquisa seu site foi exibido antes de o usuário clicar no seu site. | smallint unsigned |
| **`secondary_hit`** | Um sinalizador que determina se a ocorrência é secundária. Normalmente, esse sinalizador se origina da marcação de vários conjuntos e das regras VISTA que copiam ocorrências. | tinyint unsigned |
| **`sourceid`** | ID da origem | int unsigned |
| **`state`** | Variável de estado. | varchar(50) |
| **`stats_server`** | Não está em uso. Servidor interno da Adobe que processou o hit. | char(30) |
| **`t_time_info`** | Horário local do visitante. O formato é: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Usado em integrações do Adobe Target. Representa todos os testes qualificados até o momento. O formato é: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | texto |
| **`tnt_action`** | Usado em integrações do Adobe Target. Representa todos os testes para os quais o hit se qualificou. | texto |
| **`tnt_instances`** | Usado em integrações do Adobe Target. Variável de instâncias do Target. | texto |
| **`transactionid`** | Um identificador exclusivo, em que vários pontos de dados podem ser carregados posteriormente via fontes de dados. Coletado usando a variável [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | texto |
| **`truncated_hit`** | Um sinalizador que indica que a solicitação de imagem foi truncada. Indica que uma ocorrência parcial foi recebida. <br>Y: Ocorrência truncada; ocorrência parcial recebida <br>N: Ocorrência não truncada; ocorrência total recebida | char(1) |
| **`user_agent`** | A sequência de agente do usuário enviada no cabeçalho HTTP da solicitação de imagem. | texto |
| **`user_hash`** | Não está em uso. Hash na ID do report suite. Use `username` no lugar dela. | int unsigned |
| **`user_server`** | Usado na dimensão [Servidor](/help/components/dimensions/server.md). | varchar(100) |
| **`userid`** | Não está em uso. A ID numérica da ID do conjunto de relatórios. Use `username` no lugar dela. | int unsigned |
| **`username`** | A ID de conjunto de relatórios da ocorrência. | char(40) |
| **`va_closer_detail`** | A dimensão [Detalhe do último contato](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| **`va_closer_id`** | Uma ID numérica que identifica a dimensão [Canal de último contato](/help/components/dimensions/last-touch-channel.md). A pesquisa dessa ID pode ser encontrada no Gerenciador de canal de marketing. | tinyint unsigned |
| **`va_finder_detail`** | A dimensão [Detalhe de primeiro contato](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| **`va_finder_id`** | Uma ID numérica que identifica a dimensão [Canal de primeiro contato](/help/components/dimensions/first-touch-channel.md). A pesquisa dessa ID pode ser encontrada no Gerenciador de canal de marketing. | tinyint unsigned |
| **`va_instance_event`** | Um sinalizador que identifica [Instâncias](/help/components/metrics/instances.md) do Canal de Marketing. | tinyint unsigned |
| **`va_new_engagement`** | Um sinalizador que identifica o Canal de marketing [Novos engajamentos](/help/components/metrics/new-engagements.md). | tinyint unsigned |
| **`video`** | A dimensão [Conteúdo](/help/components/dimensions/sm-core.md) de mídia de streaming. | varchar(255) |
| **`videoad`** | A dimensão [Anúncio](/help/components/dimensions/sm-ads.md) de mídia de streaming. | varchar(255) |
| **`videoadinpod`** | A [Ad na posição pod](/help/components/dimensions/sm-ads.md) dimensão de mídia de streaming. | varchar(255) |
| **`videoadlength`** | A [Dimensão Comprimento do anúncio (variável)](/help/components/dimensions/sm-ads.md) Mídia de Streaming. | inteiro |
| **`videoadload`** | O [Anúncio carrega](/help/components/dimensions/sm-ads.md) dimensão de Mídia de Streaming. | varchar(255) |
| **`videoadname`** | O [Nome do anúncio (variável)](/help/components/dimensions/sm-ads.md) Dimensão de mídia de streaming. | varchar(255) |
| **`videoadplayername`** | A dimensão [Nome do player do anúncio](/help/components/dimensions/sm-ads.md) Mídia de Streaming. | varchar(255) |
| **`videoadpod`** | A dimensão [Pod de anúncio](/help/components/dimensions/sm-ads.md) Mídia de streaming. | varchar(255) |
| **`videoadvertiser`** | A dimensão Mídia de Streaming de [Anunciante](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoaudioalbum`** | A dimensão [Álbum](/help/components/dimensions/sm-audio-metadata.md) de streaming de mídia. | varchar(255) |
| **`videoaudioartist`** | A dimensão Mídia de Streaming de [Artista](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videoaudioauthor`** | A dimensão [Autor](/help/components/dimensions/sm-audio-metadata.md) da mídia de streaming. | varchar(255) |
| **`videoaudiolabel`** | A dimensão [Rótulo](/help/components/dimensions/sm-audio-metadata.md) de Mídia de Streaming. | varchar(255) |
| **`videoaudiopublisher`** | A dimensão Mídia de Streaming de [Publicador](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videoaudiostation`** | A dimensão [Estação](/help/components/dimensions/sm-audio-metadata.md) de Mídia de Streaming. | varchar(255) |
| **`videocampaign`** | A dimensão [ID da Campanha](/help/components/dimensions/sm-ads.md) para mídia de streaming. | varchar(255) |
| **`videochannel`** | A dimensão [Canal de conteúdo](/help/components/dimensions/sm-core.md) de mídia de streaming. | varchar(255) |
| **`videochapter`** | A dimensão [Capítulo](/help/components/dimensions/sm-chapters.md) de mídia de streaming. | varchar(255) |
| **`videocontenttype`** | A dimensão [Tipo de conteúdo](/help/components/dimensions/sm-core.md) de mídia de streaming. | varchar(255) |
| **`videodaypart`** | A [parte do dia](/help/components/dimensions/sm-video-metadata.md) dimensão de mídia de streaming. | varchar(255) |
| **`videoepisode`** | A dimensão [Episódio](/help/components/dimensions/sm-video-metadata.md) da mídia de streaming. | varchar(255) |
| **`videofeedtype`** | O [Tipo de feed de mídia](/help/components/dimensions/sm-video-metadata.md) Dimensão de mídia de transmissão. | varchar(255) |
| **`videogenre`** | A dimensão [Gênero](/help/components/dimensions/sm-video-metadata.md) de mídia de streaming. Essa dimensão permite vários valores na mesma ocorrência, delimitados por vírgula. | texto |
| **`videolength`** | A [dimensão Comprimento do conteúdo (variável)](/help/components/dimensions/sm-core.md) Mídia de Streaming. | inteiro |
| **`videomvpd`** | A dimensão [MVPD](/help/components/dimensions/sm-video-metadata.md) de mídia de streaming. | varchar(255) |
| **`videoname`** | O [Nome do conteúdo (variável)](/help/components/dimensions/sm-core.md) Dimensão de mídia de streaming. | varchar(255) |
| **`videonetwork`** | A dimensão [Rede](/help/components/dimensions/sm-video-metadata.md) de Mídia de Streaming. | varchar(255) |
| **`videopath`** | A dimensão [Caminho da mídia](/help/components/dimensions/sm-core.md) para mídia de streaming. | varchar(100) |
| **`videoplayername`** | A dimensão [Nome do player de conteúdo](/help/components/dimensions/sm-core.md) Mídia de Streaming. | varchar(255) |
| **`videotime`** | A métrica [Tempo gasto com o conteúdo](/help/components/metrics/sm-core.md) para mídia de streaming. | inteiro |
| **`videoqoebitrateaverageevar`** | A dimensão [Taxa média de bits](/help/components/dimensions/sm-quality.md) da mídia de streaming. | varchar(255) |
| **`videoqoebitratechangecountevar`** | A [taxa de bits altera](/help/components/dimensions/sm-quality.md) a dimensão de mídia de streaming. | varchar(255) |
| **`videoqoebuffercountevar`** | A dimensão [Eventos de buffer](/help/components/dimensions/sm-quality.md) Mídia de streaming. | varchar(255) |
| **`videoqoebuffertimeevar`** | A [Duração total do buffer](/help/components/dimensions/sm-quality.md) da dimensão de Mídia de Streaming. | varchar(255) |
| **`videoqoedroppedframecountevar`** | A [Dimensão Quadros soltos](/help/components/dimensions/sm-quality.md) de Mídia de Streaming. | varchar(255) |
| **`videoqoeerrorcountevar`** | A dimensão [Erros](/help/components/dimensions/sm-quality.md) de mídia de streaming. | varchar(255) |
| **`videoqoeextneralerrors`** | A [dimensão Mídia de Streaming de IDs de erro externo](/help/components/dimensions/sm-quality.md). Essa dimensão permite vários valores na mesma ocorrência. | texto |
| **`videoqoeplayersdkerrors`** | A dimensão [IDs de erro do Player SDK](/help/components/dimensions/sm-quality.md) para Streaming de Mídia. Essa dimensão permite vários valores na mesma ocorrência. | texto |
| **`videoqoetimetostartevar`** | A dimensão [Hora de início](/help/components/dimensions/sm-quality.md) da mídia de streaming. | varchar(255) |
| **`videoseason`** | A dimensão [Temporada](/help/components/dimensions/sm-video-metadata.md) de Mídia de Streaming. | varchar(255) |
| **`videosegment`** | A dimensão [Segmento de conteúdo](/help/components/dimensions/sm-core.md) de mídia de streaming. | varchar(255) |
| **`videoshow`** | A dimensão [Programa](/help/components/dimensions/sm-video-metadata.md) de streaming de mídia. | varchar(255) |
| **`videoshowtype`** | A dimensão [Tipo de programa](/help/components/dimensions/sm-video-metadata.md) de mídia de streaming. | varchar(255) |
| **`videostreamtype`** | A dimensão [Tipo de fluxo](/help/components/dimensions/sm-core.md) Mídia de streaming. | varchar(255) |
| **`visid_high`** | Usado em combinação com `visid_low` para identificar exclusivamente um(a) visitante. | bigint unsigned |
| **`visid_low`** | Usado em combinação com `visid_high` para identificar exclusivamente um(a) visitante. | bigint unsigned |
| **`visid_new`** | Um sinalizador que determina se a ocorrência contém uma ID de visitante recém-gerada. | char(1) |
| **`visid_timestamp`** | Se uma ID de visitante for recém-gerada, fornece o carimbo de data e hora no UNIX® de quando ela foi gerada. | int |
| **`visid_type`** | Não destinado a uso externo; usado internamente pela Adobe para otimizar o processamento. Uma ID numérica que representa o método usado para identificar o visitante.<br>`0`: ID de visitante personalizado ou desconhecido/não aplicável<br>`1`: fallback de IP e agente de usuário <br>`2`: cabeçalho de assinante móvel HTTP <br>`3`: valor de cookie herdado (`s_vi`) <br>`4`: valor de cookie de fallback (`s_fid`) <br>`5`: serviço de identidade | tinyint unsigned |
| **`visit_keywords`** | A dimensão [Palavra-chave de pesquisa](/help/components/dimensions/search-keyword.md). Essa coluna usa um limite de caracteres não padrão de varchar(244) para acomodar a lógica de back-end usada pela Adobe. | varchar(244) |
| **`visit_num`** | A dimensão [Número de visitas](/help/components/dimensions/visit-number.md). Começa em 1, e incrementa a cada início de nova visita por visitante. | int unsigned |
| **`visit_page_num`** | A dimensão [profundidade da ocorrência](/help/components/dimensions/hit-depth.md). Aumenta em 1 para cada ocorrência gerada pelo visitante. Redefine cada visita. | int unsigned |
| **`visit_ref_domain`** | Com base na coluna `visit_referrer`. O primeiro domínio de referência da visita. | varchar(100) |
| **`visit_ref_type`** | Uma ID numérica que representa o tipo do primeiro referenciador da visita. Faz referência à tabela de pesquisa `referrer_type.tsv`. | tinyint unsigned |
| **`visit_referrer`** | O primeiro referenciador da visita. | varchar(255) |
| **`visit_search_engine`** | Uma ID numérica que representa o primeiro mecanismo de pesquisa da visita. Faz referência à tabela de pesquisa `search_engines.tsv`. | smallint unsigned |
| **`visit_start_page_url`** | O primeiro URL da visita. | varchar(255) |
| **`visit_start_pagename`** | O valor Nome da página na primeira ocorrência da visita. | varchar(100) |
| **`visit_start_time_gmt`** | Carimbo de data e hora (em horário UNIX®) da primeira ocorrência da visita. | int |
| **`weekly_visitor`** | Um sinalizador que determina se a ocorrência é um novo visitante semanal. | tinyint unsigned |
| **`yearly_visitor`** | Um sinalizador que determina se a ocorrência é um novo visitante anual. | tinyint unsigned |
| **`zip`** | Ajuda a preencher a dimensão [CEP](/help/components/dimensions/zip-code.md). Consulte também `geo_zip`. | varchar(50) |

{style="table-layout:auto"}

## Colunas não usadas ou desativadas

A lista de colunas a seguir não é usada, foi removida ou não contém valor no relatório. Algumas dessas colunas estão vinculadas a recursos que foram descontinuados, enquanto outras não são mais necessárias devido a recursos novos e mais robustos. A maioria dessas colunas não contém dados. As colunas que ainda podem conter dados não são compatíveis com as bibliotecas de coleção de dados atuais e não estão disponíveis no Analysis Workspace.

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `sampled_hit`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`

>[!MORELIKETHIS]
>
>[Mapeamento da variável de objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md)
>&#x200B;>[Mapeamento da variável de objeto de dados](/help/implement/aep-edge/data-var-mapping.md)
