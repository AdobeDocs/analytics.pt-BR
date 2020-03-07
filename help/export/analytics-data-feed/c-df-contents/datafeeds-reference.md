---
description: Dados da tabela que descrevem as colunas no feed de dados.
keywords: Data Feed;columns
subtopic: data feeds
title: Referência da coluna de dados
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: e9158f4c1ea2fc338116df34d6c6edf93ff7050e

---


# Referência da coluna de dados

Use esta página para saber quais dados estão contidos em cada coluna. A maioria das implementações não usa cada coluna, portanto, essa página pode ser referenciada ao determinar quais colunas incluir em uma exportação de feed de dados.

> [!IMPORTANT] Para qualquer coluna (por exemplo, uma que esteja definida como 255 caracteres), devido à adição de valores de saída de caracteres em uma cadeia de caracteres. Lembre-se desses caracteres adicionais em potencial se sua implementação envia regularmente valores que excedem os limites de caracteres.

## Colunas, descrições e tipos de dados

> [!NOTE] A maioria das colunas contém uma coluna semelhante com um prefixo `post_`. Colunas de publicação contêm valores após a lógica do lado do servidor,  regras de processamento e regras VISTA. A Adobe recomenda usar tais colunas na maioria dos casos. Consulte [Perguntas frequentes sobre feeds de dados](../df-faq.md) para obter mais informações.

| Nome da coluna | Descrição da coluna | Tipo de dados |
| --- | --- | --- |
| `accept_language` | Lista todas as linguagens aceitas, conforme indicado no cabeçalho Linguagem aceita de HTTP em uma solicitação de imagem. | char(20) |
| `aemassetid` | Uma variável multivalor correspondente a IDs de ativos (GUID&#39;s) de um conjunto de ativos do Adobe Experience Manager. Incrementa eventos de impressão. | text |
| `aemassetsource` | Identifica a origem do evento do ativo. Usado no Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | ID de ativo referente a um ativo do Adobe Experience Manager. Incrementa eventos de clique. | varchar(255) |
| `browser` | ID numérica do navegador. Faz referência à tabela de pesquisa browser.tsv. | int unsigned |
| `browser_height` | Altura em pixels da janela do navegador. | smallint unsigned |
| `browser_width` | Largura em pixels da janela do navegador. | smallint unsigned |
| `c_color` | Profundidade de bits da paleta de cores. Usada como parte do cálculo da dimensão de Intensidade de cor. Usa a função screen.colorDepth() do JavaScript. | char(20) |
| `campaign` | Variável usada na dimensão Código de rastreamento. | varchar(255) |
| `carrier` | Variável de integração da Adobe Advertising Cloud. Especifica a operadora de celular. Faz referência à tabela de pesquisa de operadora. | varchar(100) |
| `channel` | Variável usada na dimensão Seções do site. | varchar(100) |
| `click_action` | Não está mais em uso. Endereço do link clicado na ferramenta herdada ClickMap. | varchar(100) |
| `click_action_type` | Não está mais em uso. Tipo de link da ferramenta herdada Clickmap.<br>0: HREF URL<br>1: ID Personalizado <br>2: Evento JavaScript onClick<br>3: Elemento de formulário | tinyint unsigned |
| `click_context` | Não está mais em uso. Nome da página na qual o clique no link ocorreu. Parte da ferramenta herdada Clickmap. | varchar(255) |
| `click_context_type` | Não está mais em uso. Indica se click_context tinha um nome de página ou se seu padrão era um URL de página.<br>0: URL da página<br>1: Nome da página | tinyint unsigned |
| `click_sourceid` | Não está mais em uso. ID numérica do local na página onde ocorreu o clique no link. Parte da ferramenta herdada Clickmap. | int unsigned |
| `click_tag` | Não está mais em uso. Tipo de elemento HTML que foi clicado. | char(10) |
| `clickmaplink` | Link para o Activity Map | varchar(255) |
| `clickmaplinkbyregion` | Link por região do Activity Map | varchar(255) |
| `clickmappage` | Página do Activity Map | varchar(255) |
| `clickmapregion` | Região do Activity Map | varchar(255) |
| `code_ver` | Versão da Biblioteca AppMeasurement usada para compilar e enviar a solicitação de imagem. | char(16) |
| `color` | ID de Intensidade de cor com base no valor da coluna c_color. Faz referência à tabela de pesquisa color_depth.tsv. | smallint unsigned |
| `connection_type` | ID numérica que representa o tipo de conexão. Variável usada na dimensão Tipo de conexão. Faz referência à tabela de pesquisa connection_type.tsv. | tinyint unsigned |
| `cookies` | Variável usada na dimensão Suporte a cookies.<br>Y: Ativado<br>N: Desativado<br>U: Desconhecido | char(1) |
| `country` | ID numérica que representa o país de onde a ocorrência foi originada. A Adobe formou uma parceria com a Digital Envoy para corresponder o endereço IP ao país. Usa a pesquisa country.tsv. | smallint unsigned |
| `ct_connect_type` | Relacionado à coluna connection_type. Os valores mais comuns são LAN/Wifi, Operadora de celular e Modem. | char(20) |
| `curr_factor` | Determina a posição decimal da moeda e é usado para conversão de moedas. Por exemplo, USD usa duas casas decimais, portanto o valor dessa coluna seria 2. | tinyint |
| `curr_rate` | A taxa de câmbio de quando a transação ocorreu. A Adobe formou uma parceria com a XE para determinar a taxa de câmbio atual. | decimal(24,12) |
| `currency` | O código de câmbio que foi usado durante a transação. | char(8) |
| `cust_hit_time_gmt` | Somente conjuntos de relatório com carimbos de data e hora habilitados. O carimbo de data e hora enviado com a ocorrência, com base em horário Unix. | int |
| `cust_visid` | Se uma ID de visitante personalizada estiver definida, será inserida nesta coluna. | varchar(255) |
| `daily_visitor` | Sinalizador para determinar se a ocorrência é um novo visitante diário. | tinyint unsigned |
| `date_time` | O horário da ocorrência em formato legível, com base no fuso horário do conjunto de relatórios. | datetime |
| `domain` | Variável usada na dimensão Fidelidade do cliente. Baseado no provedor de serviço de internet (ISP) do usuário. | varchar(100) |
| `duplicate_events` | Lista todos os eventos que são contados como duplicados. | varchar(255) |
| `duplicate_purchase` | Sinalizador que indica que o evento de compra para esta ocorrência deve ser ignorado, porque está duplicado. | tinyint unsigned |
| `duplicated_from` | Somente usado em conjuntos de relatórios contendo uma cópia da ocorrência com regras VISTA. Indica de qual conjunto de relatórios a ocorrência foi copiada. | varchar(40) |
| `ef_id` | A ef_id usada em integrações da Adobe Advertising Cloud. | varchar(255) |
| `evar1 - evar250` | Variáveis personalizadas 1-250. Cada organização usa eVars de maneiras diferentes. O melhor lugar para obter informações sobre como sua organização popula as respectivas eVars seria um documento de design da solução específico da sua organização. | varchar(255) |
| `event_list` | Lista de IDs numéricas separadas por vírgulas representando eventos acionados na ocorrência. Incli tanto eventos padrão quanto personalizados 1 - 1000. Usa a pesquisa event.tsv. | text |
| `exclude_hit` | Sinalizador indicando que a ocorrência está excluída de relatórios. A coluna visit_num não sofre alteração com as ocorrências excluídas.<br>1: Não usado. Parte de um recurso raspado.<br>2: Não usado. Parte de um recurso raspado.<br>3: Não está mais em uso. Exclusão do agente usuário<br>4: Exclusão baseada em endereço de IP<br>5: Informações vitais de ocorrência ausentes, como URL de página, nome de página, evento de página ou lista de eventos<br>6: JavaScript não processou a ocorrência corretamente<br>7: Exclusão específica da conta, como nas regras VISTA<br>8: Não usado. Exclusão específica da conta alternativa.<br>9: Não usado. Parte de um recurso raspado.<br>10: Código monetário inválido<br>11: Falta um carimbo na ocorrência ou um conjunto de relatórios no carimbo, ou uma ocorrência continha um carimbo em um conjunto de relatórios sem carimbo<br>12: Não usado. Parte de um recurso raspado.<br>13: Não usado. Parte de um recurso raspado.<br>14: Ocorrência do Target que não corresponde a uma ocorrência do Analytics<br>15: Não usado no momento.<br>16: Ocorrência da Advertising Cloud que não correspondeu a uma ocorrência do Analytics | tinyint unsigned |
| `first_hit_page_url` | O primeiro URL do visitante. | varchar(255) |
| `first_hit_pagename` | Variável usada na dimensão Página de entrada original. O nome original da página de entrada do visitante. | varchar(100) |
| `first_hit_ref_domain` | Variável usada na dimensão Domínio de referência original. Com base em first_hit_referrer. O primeiro domínio de referência do visitante. | varchar(100) |
| `first_hit_ref_type` | ID numérica que representa o tipo do primeiro referenciador do visitante. Usa a pesquisa referrer_type.tsv. | tinyint unsigned |
| `first_hit_referrer` | O primeiro URL de referência do visitante. | varchar(255) |
| `first_hit_time_gmt` | Carimbo de data e hora, em horário Unix, da primeira ocorrência de um visitante. | int |
| `geo_city` | Nome da cidade na qual a ocorrência foi originada, com base no IP. A Adobe formou uma parceria com a Digital Envoy para corresponder o endereço IP à cidade. | char(32) |
| `geo_country` | Abreviação do país no qual a ocorrência foi originada, com base no IP. A Adobe formou uma parceria com a Digital Envoy para corresponder o endereço IP ao país. | char(4) |
| `geo_dma` | ID numérica da área demográfica na qual a ocorrência foi originada, com base no IP. A Adobe formou uma parceria com a Digital Envoy para corresponder o endereço IP à área demográfica. | int unsigned |
| `geo_region` | Nome do estado ou região de origem da ocorrência, com base no IP. A Adobe formou uma parceria com a Digital Envoy para corresponder o endereço IP ao estado/região. | char(32) |
| `geo_zip` | O código postal de origem da ocorrência, com base no IP. A Adobe formou uma parceria com a Digital Envoy para corresponder o endereço IP ao código postal. | varchar(16) |
| `hier1 - hier5` | Usado em variáveis de hierarquia. Contém uma lista delimitada de valores. O delimitador é escolhido nas configurações do conjunto de relatórios. | varchar(255) |
| `hit_source` | Indica a origem da ocorrência. <br>1: Solicitação de imagem padrão sem carimbo de data e hora <br>2: Solicitação de imagem padrão com carimbo de data e hora <br>3: Carregamento de fonte de dados ao vivo com carimbos de data e hora <br>4: Não utilizado <br>5: Upload de fonte de dados genérica <br>6: Carregamento completo da fonte de dados de processamento <br>7: Carregamento da fonte de dados TransactionID <br>8: Deixar de ser utilizado; Versões anteriores das fontes de dados da Adobe Advertising Cloud <br>9: Deixar de ser utilizado; Métricas de resumo do Adobe Social | tinyint unsigned |
| `hit_time_gmt` | O carimbo de data e hora dos servidores de coleta de dados da Adobe de ocorrência recebeu a ocorrência, com base no horário Unix. | int |
| `hitid_high` | Usado em combinação com hitid_low para identificar uma ocorrência de maneira exclusiva. | bigint unsigned |
| `hitid_low` | Usado em combinação com hitid_high para identificar uma ocorrência de maneira exclusiva. | bigint unsigned |
| `homepage` | Não está mais em uso. Indica se o URL atual é a página inicial do navegador. | char(1) |
| `hourly_visitor` | Sinalizador para determinar se a ocorrência é um novo visitante por hora. | tinyint unsigned |
| `ip` | Endereço IP, com base no cabeçalho HTTP da solicitação de imagem. | char(20) |
| `ip2` | Não usado. Variável de referência de backend para conjuntos de relatórios contendo regras VISTA com base em endereço IP. | char(20) |
| `j_jscript` | A versão do JavaScript suportada pelo navegador. | char(5) |
| `java_enabled` | Sinalizador indicando se o Java está habilitado. <br>Y: Ativado <br>N: Desativado <br>U: Desconhecido | char(1) |
| `javascript` | ID de pesquisa da versão de JavaScript, com base em j_jscript. Usa uma tabela de pesquisa. | tinyint unsigned |
| `language` | ID numérica da linguagem. Usa a tabela de pesquisa languages.tsv. | smallint unsigned |
| `last_hit_time_gmt` | Carimbo de data e hora (em horário Unix) da ocorrência anterior. Usado para calcular a dimensão Dias desde a última visita. | int |
| `last_purchase_num` | Variável usada na dimensão Fidelização do cliente. Indica a quantidade de compras que o visitante fez anteriormente. <br>0: Nenhuma compra anterior (não é um cliente) <br>1: 1 compra prévia (novo cliente) <br>2: 2 compras anteriores (cliente recorrente) <br>3: 3 ou mais compras anteriores (cliente fidelizado) | int unsigned |
| `last_purchase_time_gmt` | Usado na dimensão Dias desde a última compra. Carimbo de data e hora (em horário Unix) da última compra feita. Para compras feitas pela primeira vez e visitantes que ainda não fizeram uma compra, esse valor é 0. | int |
| `latlon1` | Localização (abaixo de 10 km) | varchar(255) |
| `latlon23` | Localização (abaixo de 100 m) | varchar(255) |
| `latlon45` | Localização (abaixo de 1 m) | varchar(255) |
| `mc_audiences` | Lista de IDs de segmento do Audience Manager à qual o visitante pertence. | text |
| `mcvisid` | ID de visitante da Experience Cloud. Número de 128 bits que consiste em dois números concatenados de 64 bits arredondados para 19 dígitos. | varchar(255) |
| `mobile_id` | Se o visitante estiver usando um dispositivo móvel, o ID numérico do dispositivo. | int |
| `mobileaction` | Ação em dispositivo móvel. Coletado automaticamente quando trackAction é chamado no Mobile Services. Permite a criação de caminhos de ação automática no aplicativo. | varchar(100) |
| `mobileappid` | ID do aplicativo móvel. Armazena o nome e a versão do aplicativo no seguinte formato:[AppName] [BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | Usado no conector de dados Apteligent. O ID do aplicativo usado no Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Usado no conector de dados Apteligent. O ID de falha usado no Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Usado no conector de dados Appfigures. App Store Object ID | varchar(255) |
| `mobilebeaconmajor` | Beacon do Mobile Services maior | varchar(100) |
| `mobilebeaconminor` | Beacon do Mobile Services menor | varchar(100) |
| `mobilebeaconproximity` | Proximidade de beacon do Mobile Services | varchar(255) |
| `mobilebeaconuuid` | UUID de beacon do Mobile Services | varchar(100) |
| `mobilecampaigncontent` | O nome ou ID do conteúdo que exibiu o link. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| `mobilecampaignmedium` | Meio de marketing, como banner ou email. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| `mobilecampaignname` | Nome da campanha, também armazenado na variável da campanha. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| `mobilecampaignsource` | Referenciador original, como boletins informativos ou redes de mídia social. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| `mobilecampaignterm` | Palavras-chave pagas ou outros termos que você deseja acompanhar com essa aquisição. Preenchido pela Aquisição do dispositivo móvel. | varchar(255) |
| `mobiledayofweek` | Dia da semana no qual o aplicativo foi inicializado. | varchar(255) |
| `mobiledayssincefirstuse` | Número de dias desde a primeira execução do aplicativo. | varchar(255) |
| `mobiledayssincelastupgrade` | Coletada da variável de dados de contexto a.DaysSinceLastUpgrade. O número de dias que passaram desde a sessão anterior. | varchar(255) |
| `mobiledayssincelastuse` | Número de dias desde a execução mais recente do aplicativo. | varchar(255) |
| `mobiledeeplinkid` | Coletada da variável de dados de contexto a.<span>deeplink</span>.id. Usado nos relatórios de aquisição como um identificador para o link de aquisição móvel. | varchar(255) |
| `mobiledevice` | Nome do dispositivo móvel. No iOS, é armazenado em uma sequência de caracteres de 2 dígitos. O primeiro número representa a geração do dispositivo, e o segundo representa a família do dispositivo. | varchar(255) |
| `mobilehourofday` | Define a hora do dia que o aplicativo foi inicializado. Segue um formato numérico de 24 horas. | varchar(255) |
| `mobileinstalldate` | Data de instalação móvel. Fornece a data da primeira vez que um usuário abriu o aplicativo móvel. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Coletada da variável de dados de contexto a.LaunchesSinceUpgrade. Relata o número de inicializações desde a última atualização. | varchar(255) |
| `mobilelaunchnumber` | Há um aumento de um cada vez que o aplicativo é inicializado. | varchar(255) |
| `mobileltv` | Não está mais em uso. Preenchido pelos métodos trackLifetimeValue. | varchar(255) |
| `mobilemessagebuttonname` | Coletada da variável de dados de contexto a.<span>message</span>.button.id. Usado para mensagens no aplicativo para identificar o botão que fechou a mensagem. | varchar(100) |
| `mobilemessageid` | ID da mensagem no aplicativo | varchar(255) |
| `mobilemessageonline` | Mensagens no aplicativo on-line | varchar(255) |
| `mobilemessagepushoptin` | Coletada da variável de dados de contexto a.push.optin. Defina como &quot;true&quot; quando o usuário optar por enviar mensagens de push; caso contrário, o valor será &quot;false&quot;. | varchar(255) |
| `mobilemessagepushpayloadid` | Coletada da variável de dados de contexto a.push.payloadid. Usado em mensagens de push como o identificador de carga. | varchar(255) |
| `mobileosenvironment` | Coletada da variável de dados de contexto a.OSEnvironment. Aponta o ambiente do SO, como Android ou iOS. | varchar(255) |
| `mobileosversion` | Versão do sistema operacional do Mobile Services | varchar(255) |
| `mobileplaceaccuracy` | Coletada da variável de dados de contexto a.loc.acc. Indica a precisão do GPS em metros no momento da coleta. | varchar(255) |
| `mobileplacecategory` | Coletada da variável de dados de contexto a.loc.category. Descreve a categoria de um local específico. | varchar(255) |
| `mobileplaceid` | Coletada da variável de dados de contexto a.<span>loc</span>.id. Identificador para um determinado ponto de interesse. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Conteúdo de inicialização do Mobile Services | varchar(255) |
| `mobilerelaunchcampaignmedium` | Meio de lançamento do Mobile Services | varchar(255) |
| `mobilerelaunchcampaignsource` | Fonte de lançamento do Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Termo de lançamento do Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Coletada da variável de dados de contexto a.launch.campaign.trackingcode. Usado na aquisição como o código de rastreamento para a campanha de lançamento. | varchar(255) |
| `mobileresolution` | Resolução do dispositivo móvel. Largura x altura em pixels. | varchar(255) |
| `monthly_visitor` | Sinalizador indicando que o visitante é exclusivo no mês atual. | tinyint unsigned |
| `mvvar1` - `mvvar3` | Lista de valores de variáveis. Contém uma lista delimitada de valores personalizados dependendo da implementação. | text |
| `namespace` | Não usado. Parte de um recurso removido anos atrás. | varchar(50) |
| `new_visit` | Um sinalizador que determina se ocorrência atual é uma nova visita. Definido por servidores da Adobe depois de 30 minutos de inatividade da visita. | tinyint unsigned |
| `os` | ID numérica que representa o sistema operacional do visitante. Com base na coluna user_agent. Usa pesquisa de sistema operacional. | int unsigned |
| `p_plugins` | Não está mais em uso. Lista de plug-ins disponíveis para o navegador. Usado na função navigator.plugins() do JavaScript. | text |
| `page_event` | O tipo de ocorrência que é enviado na solicitação da imagem (ocorrência padrão, link de download, link personalizado, link de saída). [Pesquisa de evento da página](datafeeds-page-event.md). | tinyint unsigned |
| `page_event_var1` | Somente usado em solicitações de imagem de rastreamento de link. O URL dos links clicados, seja de download, de saída ou personalizados. | text |
| `page_event_var2` | Somente usado em solicitações de imagem de rastreamento de link. O nome personalizado (se especificado) do link. | varchar(100) |
| `page_event_var3` | Não está mais em uso. Continha dados de módulo de Pesquisa e de Mídia. Preenchia relatórios herdados de vídeo em versões anteriores do Adobe Analytics. | text |
| `page_type` | Usado para preencher a dimensão Páginas não encontradas, usada exclusivamente para páginas 404. Esta variável deve estar vazia ou conter “ErrorPage”. | char(20) |
| `page_url` | O URL da ocorrência. Não usada em solicitações de imagem de rastreamento de link. | varchar(255) |
| `pagename` | Usado para preencher a dimensão Páginas. Se a variável de nome de página estiver vazia, o Analytics usa page_url. | varchar(100) |
| `paid_search` | Sinalizador que é definido se a ocorrência corresponder à detecção de pesquisa paga. | tinyint unsigned |
| `partner_plugins` | Não usado. Parte de um recurso removido anos atrás. | varchar(255) |
| `persistent_cookie` | Usado pela dimensão Suporte a cookie persistente. Indica se o visitante suporta cookies que não são descartados depois de cada ocorrência. | char(1) |
| `plugins` | Não está mais em uso. Lista de IDs numéricas que correspondem a plug-ins disponíveis no navegador. Usa a pesquisa plugins.tsv. | varchar(180) |
| `pointofinterest` | Nome do ponto de interesse do Mobile Services | varchar(255) |
| `pointofinterestdistance` | Centro de distância do Mobile Services ao ponto de interesse | varchar(255) |
| `post_ columns` | Contém o valor usado por último em relatórios. Cada coluna de publicação contém valores após a lógica do lado do servidor, regras de processamento e regras VISTA. A Adobe recomenda usar tais colunas na maioria dos casos. | Consulte a respectiva coluna de não-publicação |
| `prev_page` | Não usado. Identificador da Adobe da página anterior. | int unsigned |
| `product_list` | Lista de produto conforme enviado por meio da variável de produtos. Produtos são delimitados por vírgulas, propriedades de produtos individuais são delimitados por ponto e vírgula. | text |
| `product_merchandising` | Não usado. Em vez disso, use product_list. | text |
| `prop1` - `prop75` | Variáveis de tráfego personalizadas 1 - 75. | varchar(100) |
| `purchaseid` | Identificador exclusivo de uma compra, definido usando a variável s_purchaseID. Usado pela coluna duplicate_purchase. | char(20) |
| `quarterly_visitor` | Sinalizador para determinar se a ocorrência é um novo visitante trimestral. | tinyint unsigned |
| `ref_domain` | Com base na coluna referrer. O domínio de referência da ocorrência. | varchar(100) |
| `ref_type` | Uma ID numérica que representa o tipo de referência para a ocorrência.<br>1: Dentro do site<br>2: Outros sites da web <br>3: Mecanismos de pesquisa <br>4: Disco rígido <br>5: USENET <br>6: Digitado/Marcado (sem referenciador) <br>7: E-mail <br>8: Sem JavaScript <br>9: Redes sociais | tinyint unsigned |
| `referrer` | URL da página anterior. Observe que, embora `referrer` use um tipo de dados de varchar(255), `post_referrer` usa um tipo de dados de varchar(244). | varchar(255) |
| `resolution` | ID numérica que representa a resolução do monitor. Preenche a dimensão Resolução do monitor. Usa a tabela de pesquisa resolution.tsv. | smallint unsigned |
| `s_kwcid` | A ID de palavra-chave usada em integrações da Adobe Advertising Cloud. | varchar(255) |
| `s_resolution` | Valor bruto da resolução da tela. Coletado usando a função screen.width x screen.height do JavaScript. | char(20) |
| `sampled_hit` | Não está mais em uso. Era usada anteriormente para amostragem na Ad Hoc Analysis. | char(1) |
| `search_engine` | ID numérica que representa o Mecanismo de pesquisa que direcionou o visitante ao seu site. Usa a pesquisa search_engines.tsv. | smallint unsigned |
| `search_page_num` | Usado pela dimensão Todas as classificações de páginas de pesquisa. Indica em qual página de resultados de pesquisa seu site foi exibido antes de o visitante clicar no seu site. | smallint unsigned |
| `secondary_hit` | Sinalizador que monitora ocorrências secundárias. Normalmente origina-se de tags de vários conjuntos e regras VISTA que copiam ocorrências. | tinyint unsigned |
| `service` | Não usado. Em vez disso, use page_event. | char(2) |
| `socialaccountandappids` | Não está mais em uso. Conta de rede social e IDs do aplicativo | varchar(255) |
| `socialassettrackingcode` | Não está mais em uso. Variável de campanha em rede social | varchar(255) |
| `socialauthor` | Não está mais em uso. Variável de editores em redes sociais | varchar(255) |
| `socialcontentprovider` | Não está mais em uso. Plataformas sociais / Propriedades | varchar(255) |
| `socialinteractiontype` | Não está mais em uso. Tipo de interação social | varchar(255) |
| `sociallanguage` | Não está mais em uso. Idioma da rede social | varchar(255) |
| `sociallatlong` | Não está mais em uso. Latitude/Longitude da rede social | varchar(255) |
| `socialowneddefinitioninsighttype` | Não está mais em uso. Tipo de insight da definição de propriedade social | varchar(255) |
| `socialowneddefinitioninsightvalue` | Não está mais em uso. Valor de insight da definição de propriedade social | varchar(255) |
| `socialowneddefinitionmetric` | Não está mais em uso. Métrica de definição de propriedade social | varchar(255) |
| `socialowneddefinitionpropertyvspost` | Não está mais em uso. Propriedade de definição social em comparação à posterior | varchar(255) |
| `socialownedpostids` | Não está mais em uso. IDs de publicação sociais | varchar(255) |
| `socialownedpropertyid` | Não está mais em uso. ID de propriedade social | varchar(255) |
| `socialownedpropertyname` | Não está mais em uso. Nome de propriedade social | varchar(255) |
| `socialownedpropertypropertyvsapp` | Não está mais em uso. Propriedade social vs aplicativo | varchar(255) |
| `state` | Variável de estado. | varchar(50) |
| `stats_server` | Não está em uso. Servidor interno da Adobe que processou o hit. | char(30) |
| `t_time_info` | Horário local do visitante. O formato é: M/D/AAAA HH:MM:SS Mês (0-11, 0=Janeiro) Deslocamento do fuso horário (em minutos) | varchar(100) |
| `tnt` | Usado em integrações do Adobe Target. | text |
| `tnt_action` | Usado em integrações do Adobe Target. | text |
| `tnt_post_vista` | Não está mais em uso. Em vez disso, use post_tnt. | text |
| `transactionid` | Um identificador exclusivo, em que vários pontos de dados podem ser carregados posteriormente via fontes de dados. | text |
| `truncated_hit` | Um sinalizador que indica que a solicitação de imagem estava truncada. Indica que uma ocorrência parcial foi recebida. <br>Y: Ocorrência truncada; ocorrência parcial recebida <br>N: Ocorrência não truncada; ocorrência total recebida | char(1) |
| `ua_color` | Não está mais em uso. Anteriormente usado como um fallback de intensidade de cor. | char(20) |
| `ua_os` | Não está mais em uso. Anteriormente usado como um fallback de sistema operacional. | char(80) |
| `ua_pixels` | Não está mais em uso. Anteriormente usado como um fallback de altura e largura do navegador. | char(20) |
| `user_agent` | Sequência de caracteres do agente do usuário enviada no cabeçalho HTTP da solicitação de imagem. | text |
| `user_hash` | Não está em uso. Hash na ID do report suite. Em vez disso, use username. | int unsigned |
| `user_server` | Variável usada na dimensão Servidor. | varchar(100) |
| `userid` | Não está em uso. A ID numérica da ID do conjunto de relatórios. Em vez disso, use username. | int unsigned |
| `username` | A ID do conjunto de relatórios para a ocorrência. | char(40) |
| `va_closer_detail` | Variável usada na dimensão Detalhes do último contato. | varchar(255) |
| `va_closer_id` | ID numérica que identifica a dimensão Canal de último contato. A pesquisa desta ID pode ser encontrada no Gerenciador de canais de marketing. | tinyint unsigned |
| `va_finder_detail` | Variável usada na dimensão Detalhes do primeiro contato. | varchar(255) |
| `va_finder_id` | ID numérica que identifica a dimensão Canal de primeira contato. A pesquisa desta ID pode ser encontrada no Gerenciador de canais de marketing. | tinyint unsigned |
| `va_instance_event` | Sinalizador para identificar instâncias de Canal de marketing. Usado pela métrica Instâncias do último contato do canal de marketing. | tinyint unsigned |
| `va_new_engagement` | Sinalizador para identificar novas participações de Canal de marketing. Usado pela métricas Novos envolvimentos. | tinyint unsigned |
| `video` | Conteúdo em vídeo | varchar(255) |
| `videoad` | Nome do anúncio de vídeo | varchar(255) |
| `videoadinpod` | Posição do anúncio do vídeo no pod | varchar(255) |
| `videoadlength` | Duração do anúncio de vídeo | varchar(255) |
| `videoadload` | Cargas de vídeos e anúncios | varchar(255) |
| `videoadname` | Nome do anúncio de vídeo | varchar(255) |
| `videoadplayername` | Nome do reprodutor do anúncio de vídeo | varchar(255) |
| `videoadpod` | Pod de anúncio do vídeo | varchar(255) |
| `videoadvertiser` | Anunciante de vídeo | varchar(255) |
| `videoaudioalbum` | Álbum de áudio de vídeo | varchar(255) |
| `videoaudioartist` | Artista de áudio de vídeo | varchar(255) |
| `videoaudioauthor` | Autor do áudio do vídeo | varchar(255) |
| `videoaudiolabel` | Etiqueta de áudio de vídeo | varchar(255) |
| `videoaudiopublisher` | Editor de áudio de vídeo | varchar(255) |
| `videoaudiostation` | Estação de áudio de vídeo | varchar(255) |
| `videocampaign` | Campanha de vídeo | varchar(255) |
| `videochannel` | Canal de vídeo | varchar(255) |
| `videochapter` | Nome do capítulo do vídeo | varchar(255) |
| `videocontenttype` | Tipo de conteúdo do vídeo. Defina como &#39;Vídeo&#39; automaticamente para todas as visualizações de vídeo | varchar(255) |
| `videodaypart` | Parte do dia do vídeo | varchar(255) |
| `videoepisode` | Episódio de vídeo | varchar(255) |
| `videofeedtype` | Tipo de feed do vídeo | varchar(255) |
| `videogenre` | Gênero de vídeo | text |
| `videolength` | Duração do vídeo | varchar(255) |
| `videomvpd` | Vídeo MVPD | varchar(255) |
| `videoname` | Nome do vídeo | varchar(255) |
| `videonetwork` | Rede de vídeo | varchar(255) |
| `videopath` | Caminho do vídeo | varchar(100) |
| `videoplayername` | Nome do reprodutor de vídeo | varchar(255) |
| `videoqoebitrateaverageevar` | Taxa média de bits de qualidade do vídeo | varchar(255) |
| `videoqoebitratechangecountevar` | Contagem de alternância de qualidade do vídeo | varchar(255) |
| `videoqoebuffercountevar` | Contagem de buffer de qualidade do vídeo | varchar(255) |
| `videoqoebuffertimeevar` | Tempo de buffer de qualidade do vídeo | varchar(255) |
| `videoqoedroppedframecountevar` | Contagem de redução de qualidade do vídeo em quadros | varchar(255) |
| `videoqoeerrorcountevar` | Contagem de erros de qualidade do vídeo | varchar(255) |
| `videoqoeextneralerrors` | Erros externos de qualidade de vídeo | text |
| `videoqoeplayersdkerrors` | Erros de SDK de qualidade de vídeo | text |
| `videoqoetimetostartevar` | Tempo para o início da qualidade do vídeo | varchar(255) |
| `videoseason` | Temporada de vídeo | varchar(255) |
| `videosegment` | Segmento de vídeo | varchar(255) |
| `videoshow` | Exibição de vídeo | varchar(255) |
| `videoshowtype` | Tipo de exibição de vídeo | varchar(255) |
| `videostreamtype` | Tipo de fluxo de vídeo | varchar(255) |
| `visid_high` | Usado em combinação com visid_low para identificar uma visita de maneira exclusiva. | bigint unsigned |
| `visid_low` | Usado em combinação com visid_high para identificar uma visita de maneira exclusiva. | bigint unsigned |
| `visid_new` | Sinalizador para identificar se a ocorrência contém uma ID de visitante gerada recentemente. | char(1) |
| `visid_timestamp` | Se a ID do visitante foi gerada recentemente, fornece o carimbo de data e hora (em horário Unix) de quando ela foi gerada. | int |
| `visid_type` | ID numérica que representa método usado para identificar o visitante. <br>0: ID de visitante personalizado <br>1: IP e fallback do agente do usuário <br>2: Cabeçalho do assinante do HTTP Mobile <br>3: Valor do cookie herdado (s_vi) <br>4: Valor do cookie de fallback (s_fid) <br>5: Serviço de identidade | tinyint unsigned |
| `visit_keywords` | Variável usada na dimensão Palavra-chave de pesquisa. Essa coluna usa um limite de caracteres não padrão para acomodar a lógica de back-end usada pela Adobe. | varchar(244) |
| `visit_num` | Variável usada na dimensão Número de visitas. Começa em 1, e incrementa a cada início de nova visita por visitante. | int unsigned |
| `visit_page_num` | Variável usada na dimensão Profundidade da ocorrência. Aumenta em 1 para cada ocorrência gerada pelo usuário. Redefine cada visita. | int unsigned |
| `visit_ref_domain` | Com base na coluna visit_referrer. O primeiro domínio de referência da visita. | varchar(100) |
| `visit_ref_type` | ID numérica que representa o tipo do primeiro referenciador da visita. Usa a tabela de pesquisa referrer_type.tsv. | tinyint unsigned |
| `visit_referrer` | O primeiro referenciador da visita. | varchar(255) |
| `visit_search_engine` | ID numérica do primeiro mecanismo de pesquisa da ocorrência. Usa a tabela de pesquisa search_engines.tsv. | smallint unsigned |
| `visit_start_page_url` | O primeiro URL da visita. | varchar(255) |
| `visit_start_pagename` | O nome da primeira página da visita. | varchar(100) |
| `visit_start_time_gmt` | Carimbo de data e hora (em horário Unix) da primeira ocorrência da visita. | int |
| `weekly_visitor` | Sinalizador para determinar se a ocorrência é um novo visitante semanal. | tinyint unsigned |
| `yearly_visitor` | Sinalizador para determinar se a ocorrência é um novo visitante anual. | tinyint unsigned |
| `zip` | Usado para preencher a dimensão Código Postal. | varchar(50) |

## Colunas vazias

A seguinte lista de colunas não é usada e não contém dados:

* mobileacquisitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedusers
* mobileappperformanceappid<span>.</span>app-perf-app-name
* mobileappperformanceappid<span>.</span>app-perf-platform
* mobileappperformancecrashes
* mobileappperformancecrashid<span>.</span>app-perf-crash-name
* mobileappperformance anceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreinapprevenue
* mobileappstoreinaproyalties
* mobileappstoreobjectid<span>.</span>app store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>nome do país
* mobileappstoreobjectid<span>.</span>fabricante do dispositivo
* mobileappstoreobjectid<span>.</span>nome do dispositivo
* mobileappstoreobjectid<span>.</span>nome do aplicativo
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>classificação por categoria
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>comentário de revisão
* mobileappstoreobjectid<span>.</span>título da revisão
* mobileappstoreonoffrevenue
* mobileappstoreonoffroyalties
* mobileappstorepurch
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerating
* mobileappstorerdivisor
* mobileavgprevsessionlength
* mobilecrashes
* mobilecrashrate
* mobiledailyengagedusers
* mobiledeeplinboy<span>.</span>name
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessageimpressions
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessageviews
* mobilemonthlyengagedusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaigntrackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (obsoleto)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink (obsoleto)
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty (obsoleto)
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist (obsoleto)
* socialtotalsentiment
* sourceid
* videoauthorized
* videoaverageminuteaudience
* videochaptercomplete
* videochapterstart
* videochaptertime
* videopause
* videopausecount
* videopausetime
* videoplay
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
* videoqoebitrateaverage
* videoqoebitratechange
* videoqoebuffer
* videoqoedropbeforestart
* videoqoedroppedframes
* videoqoeerror
* videoresume
* videototaltime
* videouniquetimeplay
