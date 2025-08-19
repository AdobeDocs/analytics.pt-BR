---
title: Compatibilidade de dimensões do Analytics
description: Referência para dimensões e relatórios do Analytics.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 60%

---

# Compatibilidade de dimensões do Analytics

Esta página lista [dimensões](overview.md) compatíveis com seus respectivos recursos do Analytics.

>[!NOTE]
>
>Nomes personalizados de variáveis, classificações e atributos de visitante são omitidos nesta lista. Esses itens de dimensão são específicos de conjuntos de relatórios individuais.

## Dimensões compatíveis com o Analysis Workspace

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|---|---|
| Analytics for Target | `targetraw` |
| ID de públicos-alvo | `mcaudiences` |
| [Navegador](browser.md) | `browser` |
| [Tipo de navegador](browser-type.md) | `browsertype` |
| [Categoria](category.md) | `category` |
| [Cidades](cities.md) | `geocity` |
| [Intensidade de cor](color-depth.md) | `colordepth` |
| [Tipo de conexão](connection-type.md) | `connectiontype` |
| [Suporte a cookies](cookie-support.md) | `cookie` |
| [Países](countries.md) | `geocountry` |
| [Fidelidade do Cliente](customer-loyalty.md) | `customerloyalty` |
| [Vars de conversão personalizada](evar.md) | `evar1`, `evar2`, etc. |
| [Custom Insight Vars](prop.md) | `prop1`, `prop2`, etc. |
| [Link Personalizado](custom-link.md) | `customlink` |
| [Dias Antes da Primeira Compra](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [Dias Desde a Última Compra](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [Domínio](domain.md) | `filtereddomain` |
| [Link de Download](download-link.md) | `downloadlink` |
| [Página de entrada](entry-dimensions.md) | `entrypage` |
| [Página de entrada original](entry-dimensions.md) | `entrypageoriginal` |
| [Link de saída](exit-link.md) | `exitlink` |
| [Canal de Primeiro Contato](first-touch-channel.md) | `firsttouchchannel` |
| [Detalhes do canal de primeiro contato](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Java ativado](java-enabled.md) | `javaenabled` |
| [Idioma](language.md) | `language` |
| [Canal de Último Contato](last-touch-channel.md) | `lasttouchchannel` |
| [Detalhes do Canal de Último Contato](last-touch-detail.md) | `lasttouchchanneldetail` |
| Variáveis da lista | `listvariables` |
| [Canal de marketing](marketing-channel.md) | `marketingchannel` |
| [Suporte de áudio móvel](mobile-dimensions.md) | `mobileaudiosupport` |
| [Operadora de celular](mobile-dimensions.md) | `mobilecarrier` |
| [Intensidade de Cor do Dispositivo Móvel](mobile-dimensions.md) | `mobilecolordepth` |
| [Suporte a cookie em dispositivo móvel](mobile-dimensions.md) | `mobilecookiesupport` |
| [Dispositivo móvel](mobile-dimensions.md) | `mobiledevicename` |
| [Tipo de dispositivo móvel](mobile-dimensions.md) | `mobiledevicetype` |
| [Comprimento Máximo do Email para Dispositivo Móvel](mobile-dimensions.md) | `mobileemaillength` |
| [Suporte a imagem no dispositivo móvel](mobile-dimensions.md) | `mobileimagesupport` |
| [Fabricante do Dispositivo Móvel](mobile-dimensions.md) | `mobilemanufacturer` |
| [Sistema operacional do dispositivo móvel (obsoleto)](mobile-dimensions.md) | `mobileos` |
| [Altura da tela do dispositivo móvel](mobile-dimensions.md) | `mobilescreenheight` |
| [Tamanho de tela do dispositivo móvel](mobile-dimensions.md) | `mobilescreensize` |
| [Largura da tela do dispositivo móvel](mobile-dimensions.md) | `mobilescreenwidth` |
| [Tamanho máximo da URL do navegador móvel](mobile-dimensions.md) | `mobileurllength` |
| [Suporte a vídeo em dispositivo móvel](mobile-dimensions.md) | `mobilevideosupport` |
| [Resolução do Monitor](monitor-resolution.md) | `monitorresolution` |
| [Sistemas operacionais](operating-systems.md) | `operatingsystem` |
| [Domínio de Referência Original](original-referring-domain.md) | `referringdomainoriginal` |
| [Página](page.md) | `page` |
| [Páginas não encontradas](pages-not-found.md) | `pagesnotfound` |
| [Produto](product.md) | `product` |
| [Referenciador](referrer.md) | `referrer` |
| [Tipo de referenciador](referrer-type.md) | `referrertype` |
| [Domínio de referência](referring-domain.md) | `referringdomain` |
| [Regiões](regions.md) | `georegion` |
| [Frequência de Retorno](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [Mecanismo de pesquisa](search-engine.md) | `searchengine` |
| [Palavra-chave de pesquisa](search-keyword.md) | `searchenginekeyword` |
| [Mecanismo de pesquisa - Natural](search-engine.md) | `searchenginenatural` |
| [Mecanismo de pesquisa - Pago](search-engine.md) | `searchenginepaid` |
| [Palavra-chave de Pesquisa - Natural](search-keyword.md) | `searchenginenaturalkeyword` |
| [Palavra-chave de Pesquisa - Paga](search-keyword.md) | `searchenginepaidkeyword` |
| [Toda a classificação da página de pesquisa](all-search-page-rank.md) | `searchenginepagerank` |
| [Servidor](server.md) | `server` |
| [Visitas únicas à página](single-page-visits.md) | `singlepagevisits` |
| [Seção do site](site-section.md) | `sitesections` |
| [Tempo gasto por visita - Granular](time-spent-per-visit.md) | `sitetime` |
| [Código de rastreamento](tracking-code.md) | `campaign` |
| [DMA dos EUA](us-dma.md) | `geodma` |
| [Estados dos EUA](us-states.md) | `state` |
| [Tempo antes do evento](time-prior-to-event.md) | `timeprior` |
| [Tempo gasto por visita - Classificado](time-spent-per-visit.md) | `timespent` |
| [Profundidade da visita](visit-depth.md) | `pathlength` |
| [Número da visita](visit-number.md) | `visitnumber` |
| [Código postal](zip-code.md) | `zip` |
| [AM / PM](am-pm.md) | `timepartampm` |
| [Altura do Navegador - Classificada](browser-height.md) | `browserheightbucketed` |
| [Largura do Navegador - Classificada](browser-width.md) | `browserwidthbucketed` |
| [Dia](day.md) | `daterangeday` |
| [Dia do mês](day-of-month.md) | `timepartdayofmonth` |
| [Dia da semana](day-of-week.md) | `dayofweek` |
| [Dia da semana](day-of-week.md) | `timepartdayofweek` |
| [Dia do ano](day-of-year.md) | `timepartdayofyear` |
| [Dias desde a última visita](days-since-last-visit.md) | `dayssincelastvisit` |
| [Insights Personalizados de Entrada](entry-dimensions.md) | `entryprops` |
| [Variáveis de Lista de Entradas](entry-dimensions.md) | `entrylistvariables` |
| [Servidor de entrada](entry-dimensions.md) | `entryserver` |
| [Seção de entrada do site](entry-dimensions.md) | `entrysitesections` |
| [Insights personalizados de saída](exit-dimensions.md) | `exitprops` |
| [Variáveis de lista de saída](exit-dimensions.md) | `exitlistvariables` |
| [Página de saída](exit-dimensions.md) | `exitpage` |
| [Sair do Servidor](exit-dimensions.md) | `exitserver` |
| [Sair da Seção do Site](exit-dimensions.md) | `exitsitesections` |
| [Profundidade da ocorrência](hit-depth.md) | `hitdepth` |
| [Tipo de ocorrência](hit-type.md) | `hittype` |
| [Hora](hour.md) | `daterangehour` |
| [Hora do dia](hour-of-day.md) | `timeparthourofday` |
| [Detalhes do canal de marketing](marketing-detail.md) | `marketingchanneldetail` |
| [Minuto](minute.md) | `daterangeminute` |
| [Comprimento Máximo do Indicador Móvel](mobile-dimensions.md) | `mobilebookmarklength` |
| [Número do Dispositivo Móvel](mobile-dimensions.md) | `mobiledevicenumber` |
| [DRM Móvel](mobile-dimensions.md) | `mobiledrm` |
| [Serviços de Informações Móveis](mobile-dimensions.md) | `mobileinformationservices` |
| [VM Java para dispositivo móvel](mobile-dimensions.md) | `mobilejavavm` |
| [Decoração de Email Móvel](mobile-dimensions.md) | `mobilemaildecoration` |
| [Protocolos de Rede Móvel](mobile-dimensions.md) | `mobilenetprotocols` |
| [Push To Talk Para Dispositivos Móveis](mobile-dimensions.md) | `mobilepushtotalk` |
| [Mês](month.md) | `daterangemonth` |
| [Mês do ano](month-of-year.md) | `timepartmonthofyear` |
| [Tipos de sistema operacional](operating-system-types.md) | `operatingsystemgroup` |
| [Pesquisa paga](paid-search.md) | `paidsearch` |
| [Suporte a Cookies Persistentes](persistent-cookie-support.md) | `persistentcookie` |
| [Trimestre](quarter.md) | `daterangequarter` |
| [Trimestre do ano](quarter-of-year.md) | `timepartquarterofyear` |
| Survey | `surveybase` |
| [Tempo gasto na página - Classificado](time-spent-on-page.md) | `averagepagetime` |
| [Tempo gasto na página - Granular](time-spent-on-page.md) | `pagetimeseconds` |
| [Motivo da desativação do rastreamento](tracking-opt-out-reason.md) | `optoutreason` |
| [Dia da semana/Fim de semana](weekday-weekend.md) | `timepartweekdayweekend` |
| [Semana](week.md) | `daterangeweek` |
| [Ano](year.md) | `daterangeyear` |

## Dimensões com reconhecimento de conteúdo compatíveis somente com o Analysis Workspace

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID da sessão de mídia | `videosessionid` |
| Método de acesso Nielsen | `nielsenaccmethod` |
| ID de aplicativo Nielsen | `nielsenappid` |
| Ativo de canal Nielsen | `nielsenchannelasset` |
| Tipo de conteúdo Nielsen | `nielsencontenttype` |

## Dimensões com reconhecimento de conteúdo compatíveis com o Analysis Workspace

### Vídeo (Serviços de mídia de transmissão)

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| [Conteúdo](sm-core.md) | `video` |
| [Segmento de conteúdo](sm-core.md) | `videosegment` |
| [Tipo de conteúdo](sm-core.md) | `videocontenttype` |
| [Nome do reprodutor do anúncio](sm-ads.md) | `videoadplayername` |
| [Posição do anúncio no pod](sm-ads.md) | `videoadinpod` |
| [Queda de quadros](sm-quality.md) | `videoqoedroppedframecountevar` |
| [Erros](sm-quality.md) | `videoqoeerrorcountevar` |
| [Taxa média de bits](sm-quality.md) | `videoqoebitrateaverageevar` |
| [Alterações na taxa de bits](sm-quality.md) | `videoqoebitratechangecountevar` |
| [Duração total do buffer](sm-quality.md) | `videoqoebuffertimeevar` |
| [Eventos do buffer](sm-quality.md) | `videoqoebuffercountevar` |
| [Hora de início](sm-quality.md) | `videoqoetimetostartevar` |
| [Pod de anúncios](sm-ads.md) | `videoadpod` |
| [Caminho da mídia](sm-core.md) | `videopath` |
| [Publicidade](sm-ads.md) | `videoad` |
| [Nome do reprodutor de conteúdo](sm-core.md) | `videoplayername` |
| [Canal de conteúdo](sm-core.md) | `videochannel` |
| [Capítulo](sm-chapters.md) | `videochapter` |
| [Nome do conteúdo (variável)](sm-core.md) | `videoname` |
| [Duração de conteúdo (variável)](sm-core.md) | `videolength` |
| [Nome do anúncio (variável)](sm-ads.md) | `videoadname` |
| [Comprimento do anúncio (variável)](sm-ads.md) | `videoadlength` |
| [Programa](sm-video-metadata.md) | `videoshow` |
| [Temporada](sm-video-metadata.md) | `videoseason` |
| [Episódio](sm-video-metadata.md) | `videoepisode` |
| [Rede](sm-video-metadata.md) | `videonetwork` |
| [Mostrar tipo](sm-video-metadata.md) | `videoshowtype` |
| [Carregamentos de anúncio](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [Faixa de horário](sm-video-metadata.md) | `videodaypart` |
| [Anunciante](sm-ads.md) | `videoadadvertiser` |
| [ID da campanha](sm-ads.md) | `videoadcampaign` |
| [Gênero](sm-video-metadata.md) | `videogenre` |
| [Tipo de fluxo](sm-core.md) | `videostreamtype` |
| [IDs de erro do SDK do reprodutor](sm-quality.md) | `videoqoeplayersdkerrors` |
| [IDs de erro externo](sm-quality.md) | `videoqoeextneralerrors` |
| [Tipo de feed de mídia](sm-video-metadata.md) | `videofeedtype` |
| [Caminho da Mídia de Entrada](entry-dimensions.md) | `entryvideopath` |
| [Caminho da mídia de saída](exit-dimensions.md) | `exitvideopath` |
| [Gênero de entrada](entry-dimensions.md) | `entryvideogenre` |
| [Gênero de Saída](exit-dimensions.md) | `exitvideogenre` |
| [IDs de Erro do Player SDK de Entrada](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [IDs de Erro do Player SDK de Saída](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [IDs de Erro Externo de Entrada](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [IDs de Erro Externo de Saída](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

O Adobe Social foi descontinuado.

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Termos | `socialterm` |
| Plataformas sociais / Propriedades | `socialcontentprovider` |
| Autores | `socialauthor` |
| Idioma | `sociallanguage` |
| Latitude / longitude | `sociallatlong` |
| Códigos de acompanhamento de ativos | `socialassettrackingcode` |
| Propriedades sociais próprias | `socialaccountandappids` |
| IDs de post próprias | `socialownedpostids` |
| Definições sociais próprias | `socialinteractiontype` |
| IDs de propriedades próprias | `socialownedpropertyid` |
| Propriedade x aplicativos próprios | `socialownedpropertypropertyvsapp` |
| Nome de propriedade próprio | `socialownedpropertyname` |
| Propriedade de definição x post próprio | `socialowneddefinitionpropertyvspost` |
| Tipos de Insight de definição próprios | `socialowneddefinitioninsighttype` |
| Valor de Insight de definição próprio | `socialowneddefinitioninsightvalue` |
| Métrica de definição própria | `socialowneddefinitionmetric` |
| Ativo | `socialmediaid` |

### SDK móvel

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| [Data da primeira inicialização](lifecycle-dimensions.md) | `mobileinstalldate` |
| [Id Do Aplicativo](lifecycle-dimensions.md) | `mobileappid` |
| [Número de Lançamento](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [Dias desde a primeira utilização](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [Dias desde a última utilização](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [Hora do dia (SDK)](lifecycle-dimensions.md) | `mobilehourofday` |
| [Dia da Semana (SDK)](lifecycle-dimensions.md) | `mobiledayofweek` |
| [Sistema Operacional (SDK)](lifecycle-dimensions.md) | `mobileosenvironment` |
| [Dias desde a última atualização](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [Inicializações desde a última atualização](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [Nome do dispositivo (SDK)](lifecycle-dimensions.md) | `mobiledevice` |
| [Versão do Sistema Operacional (SDK)](lifecycle-dimensions.md) | `mobileosversion` |
| [Beacon Principal](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [Beacon secundário](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [UUID do sinal](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [Proximidade do sinal](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [Localização (abaixo de 10 km)](lifecycle-dimensions.md) | `latlon1` |
| [Localização (abaixo de 100 m)](lifecycle-dimensions.md) | `latlon23` |
| [Localização (abaixo de 1 m)](lifecycle-dimensions.md) | `latlon45` |
| [Nome do ponto de interesse](lifecycle-dimensions.md) | `pointofinterest` |
| [Distância até o centro do ponto de interesse](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [Precisão do local](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [Colocar Categoria](lifecycle-dimensions.md) | `mobileplacecategory` |
| [ID do local](lifecycle-dimensions.md) | `mobileplaceid` |
| [Entrada principal do sinal](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [Sair do Sinal Principal](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [Entrada do menor sinal](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [Sair do menor sinal](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [Entrada do UUID do sinal](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [Saída do UUID do sinal](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [Proximidade de entrada do sinal](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [Proximidade do sinal de saída](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| ID do AMO | `amo_cid` |

### Activity Map

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| [Link Do Activity Map Por Região](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Região do Activity Map](activity-map-region.md) | `clickmapregion` |
| [Link do Activity Map](activity-map-link.md) | `clickmaplink` |
| [Página do Activity Map](activity-map-page.md) | `clickmappage` |

### Integração Nielsen

Para obter mais informações sobre como implementar esta integração, consulte a [Extensão Nielsen](https://exchange.adobe.com/apps/ec/101361) no Adobe Exchange.

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Modelo de anúncios Nielsen | `nielsenadmodel` |
| Segmento C Nielsen | `nielsensegmentc` |
| Segmento B Nielsen | `nielsensegmentb` |
| Segmento A Nielsen | `nielsensegmenta` |
| ID de conteúdo Nielsen | `nielsencontentid` |
| Ativo/programa Nielsen | `nielsenasset` |
| VCID Nielsen | `nielsenvcid` |
| Opção de não participação do Nielsen | `nielsenoptout` |
| ID do cliente Nielsen + VCID | `nielsenclientidvcid` |
| ID de cliente Nielsen | `nielsenclientid` |
| Entrada da opção de não participação do Nielsen | `entrynielsenoptout` |
| Saída da opção de não participação do Nielsen | `exitnielsenoptout` |
| Entrada da ID do cliente Nielsen + VCID | `entrynielsenclientidvcid` |
| Saída da ID do cliente Nielsen + VCID | `exitnielsenclientidvcid` |
| Entrada da ID do cliente Nielsen | `entrynielsenclientid` |
| Saída da ID do cliente Nielsen | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| ID do ativo | `aemassetid` |
| Origem do ativo | `aemassetsource` |
| ID de clique do ativo | `aemclickedassetid` |
| Entrada da ID do ativo | `entryaemassetid` |
| Saída da ID do ativo | `exitaemassetid` |

### Adobe Campaign

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| ID de entrega executada do Adobe Campaign | `ac_delivery_internal_name` |
