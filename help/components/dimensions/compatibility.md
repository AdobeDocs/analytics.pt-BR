---
title: Compatibilidade de dimensões do Analytics
description: Referência para dimensões e relatórios do Analytics.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 92%

---


# Compatibilidade de dimensões do Analytics

Esta página lista dimensões compatíveis com seus respectivos recursos do Analytics.

>[!NOTE]
>
>Nomes personalizados de variáveis, classificações e atributos de visitante são omitidos desta lista. Esses valores de dimensão são específicos de conjuntos de relatórios individuais.

>[!NOTE]
>
>Há algumas sobreposições nas quais as ferramentas Analytics usam termos diferentes para dimensões semelhantes. Por exemplo, Relatórios e Analytics usam `browserwidth` enquanto o Analysis Workspace usa `browserwidthbucketed`.

## Dimensões compatíveis com o Reports &amp; Analytics e a Analysis Workspace

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|---|---|
| Analytics para o Target | `targetraw` |
| ID de públicos-alvo | `mcaudiences` |
| Navegador | `browser` |
| Tipo de navegador | `browsertype` |
| Categoria | `category` |
| Cidades | `geocity` |
| Intensidade de cor | `colordepth` |
| Tipo de conexão | `connectiontype` |
| Suporte a cookies | `cookie` |
| Países | `geocountry` |
| Fidelidade do Cliente | `customerloyalty` |
| Vars de conversão personalizada | `evar1`, `evar2`, etc. |
| Vars de Insight personalizado | `prop1`, `prop2`, etc. |
| Link personalizado | `customlink` |
| Dias antes da primeira compra | `daysbeforefirstpurchase` |
| Dias Desde a Última Compra | `dayssincelastpurchase` |
| Domínio | `filtereddomain` |
| Link de download | `downloadlink` |
| Página de entrada | `entrypage` |
| Página de entrada original | `entrypageoriginal` |
| Link de saída | `exitlink` |
| Canal de Primeiro Contato | `firsttouchchannel` |
| Detalhe de Canal de Primeiro Contato | `firsttouchchanneldetail` |
| Java ativado | `javaenabled` |
| Idioma | `language` |
| Canal de Último Contato | `lasttouchchannel` |
| Detalhe de Canal de Último Contato | `lasttouchchanneldetail` |
| Variáveis da Lista | `listvariables` |
| Canal de Marketing | `marketingchannel` |
| Suporte a Áudio Remoto | `mobileaudiosupport` |
| Operadora de celular | `mobilecarrier` |
| Intensidade de Cor Remota | `mobilecolordepth` |
| Suporte a cookie em dispositivo móvel | `mobilecookiesupport` |
| Dispositivo móvel | `mobiledevicename` |
| Tipo de dispositivo móvel | `mobiledevicetype` |
| Extensão máx. de email móvel | `mobileemaillength` |
| Suporte a imagem em dispositivo móvel | `mobileimagesupport` |
| Fabricante Remoto | `mobilemanufacturer` |
| Sistema operacional móvel (obsoleto) | `mobileos` |
| Altura da Tela Remota | `mobilescreenheight` |
| Tamanho da tela remota | `mobilescreensize` |
| Largura da Tela Remota | `mobilescreenwidth` |
| Extensão máx. do URL do navegador móvel | `mobileurllength` |
| Suporte a Vídeo Remoto | `mobilevideosupport` |
| Resolução do Monitor | `monitorresolution` |
| Sistemas operacionais | `operatingsystem` |
| Domínio de referência original | `referringdomainoriginal` |
| Página | `page` |
| Páginas não encontradas | `pagesnotfound` |
| Produto | `product` |
| Referenciador | `referrer` |
| Tipo de referenciador | `referrertype` |
| Domínio de referência | `referringdomain` |
| Regiões | `georegion` |
| Frequência de Retorno | `returnfrequency` |
| SC-TnT | `tntbase` |
| Mecanismo de pesquisa | `searchengine` |
| Palavra-chave de pesquisa | `searchenginekeyword` |
| Mecanismo de pesquisa - Natural | `searchenginenatural` |
| Mecanismo de pesquisa - Pago | `searchenginepaid` |
| Palavra-chave de pesquisa - Natural | `searchenginenaturalkeyword` |
| Palavra-chave de pesquisa - Paga | `searchenginepaidkeyword` |
| Toda a classificação da página de pesquisa | `searchenginepagerank` |
| Servidor | `server` |
| Visitas únicas à página | `singlepagevisits` |
| Seção do site | `sitesections` |
| Tempo gasto por visita - Granular | `sitetime` |
| Código de rastreamento | `campaign` |
| DMA dos EUA | `geodma` |
| Estados dos Estados Unidos | `state` |
| Tempo antes do evento | `timeprior` |
| Tempo gasto por visita - Em bucket | `timespent` |
| Profundidade da Visita | `pathlength` |
| Número da visita | `visitnumber` |
| Código Postal | `zip` |

## Dimensões compatíveis somente com a Analysis Workspace

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| AM/PM | `timepartampm` |
| Altura do navegador - Classificado | `browserheightbucketed` |
| Largura do navegador - Classificado | `browserwidthbucketed` |
| Dia | `daterangeday` |
| Dia do mês | `timepartdayofmonth` |
| Dias da semana | `dayofweek` |
| Dias da semana | `timepartdayofweek` |
| Dia do ano | `timepartdayofyear` |
| Dias desde a última visita | `dayssincelastvisit` |
| Entrada de Insights personalizados | `entryprops` |
| Entrada de variáveis de lista | `entrylistvariables` |
| Servidor de entrada | `entryserver` |
| Entrada de seção do site | `entrysitesections` |
| Saída de Insights personalizados | `exitprops` |
| Saída de variáveis de lista | `exitlistvariables` |
| Página de Saída | `exitpage` |
| Saída do servidor | `exitserver` |
| Saída da seção do site | `exitsitesections` |
| Profundidade de ocorrência | `hitdepth` |
| Tipo de ocorrência | `hittype` |
| Hora | `daterangehour` |
| Hora do dia | `timeparthourofday` |
| Detalhes do canal de marketing | `marketingchanneldetail` |
| Minuto | `daterangeminute` |
| Extensão Max do Marcador Remoto | `mobilebookmarklength` |
| Número do dispositivo remoto | `mobiledevicenumber` |
| DRM Remoto | `mobiledrm` |
| Serviços de Informação Remotos | `mobileinformationservices` |
| Java VM Móvel | `mobilejavavm` |
| Decoração de correio móvel | `mobilemaildecoration` |
| Protocolos de Rede Remota | `mobilenetprotocols` |
| Push móvel para falar | `mobilepushtotalk` |
| Mês | `daterangemonth` |
| Mês do ano | `timepartmonthofyear` |
| Tipos de sistema operacional | `operatingsystemgroup` |
| Pesquisa paga | `paidsearch` |
| Suporte a cookie persistente | `persistentcookie` |
| Trimestre | `daterangequarter` |
| Trimestre do ano | `timepartquarterofyear` |
| Survey | `surveybase` |
| Tempo gasto na página - No intervalo | `averagepagetime` |
| Tempo gasto na página - Granular | `pagetimeseconds` |
| Motivo da desativação do rastreamento | `optoutreason` |
| Dia da semana/Fim de semana | `timepartweekdayweekend` |
| Semana | `daterangeweek` |
| Ano | `daterangeyear` |

## Dimensões sensívies a conteúdo compatíveis somente com a Analysis Workspace

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID da sessão de mídia | `videosessionid` |
| Método de acesso Nielsen | `nielsenaccmethod` |
| ID aplicativo Nielsen | `nielsenappid` |
| Ativo de canal Nielsen | `nielsenchannelasset` |
| Tipo de conteúdo Nielsen | `nielsencontenttype` |

## Dimensões compatíveis somente com Reports &amp; Analytics

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Altura da janela do navegador | `browserheight` |
| Largura da janela do navegador | `browserwidth` |
| Clientes únicos diários | `dailyuniquecustomers` |
| JavaScript | `javascriptsupport` |
| Versão do JavaScript | `javascriptversion` |
| Clientes únicos mensais | `monthlyuniquecustomers` |
| Clientes únicos trimestrais | `quarterlyuniquecustomers` |
| Fusos horários | `timezone` |
| Domínios de nível superior | `topleveldomain` |
| Estado do visitante | `legacystate` |
| Clientes únicos semanais | `weeklyuniquecustomers` |
| Clientes únicos anuais | `yearlyuniquecustomers` |

## Dimensões sensíveis ao conteúdo compatíveis com o Reports &amp; Analytics e a Analysis Workspace

### Vídeo (Análise de mídia)

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Conteúdo | `video` |
| Segmento de conteúdo | `videosegment` |
| Tipo de conteúdo | `videocontenttype` |
| Nome do reprodutor do anúncio | `videoadplayername` |
| Posição do anúncio no pod | `videoadinpod` |
| Queda de quadros | `videoqoedroppedframecountevar` |
| Erros | `videoqoeerrorcountevar` |
| Taxa média de bits | `videoqoebitrateaverageevar` |
| Alterações da taxa de bits | `videoqoebitratechangecountevar` |
| Duração total do buffer | `videoqoebuffertimeevar` |
| Eventos de buffer | `videoqoebuffercountevar` |
| Hora de início | `videoqoetimetostartevar` |
| Pod de anúncios | `videoadpod` |
| Caminho da mídia | `videopath` |
| Publicidade | `videoad` |
| Nome do reprodutor de conteúdo | `videoplayername` |
| Canal de conteúdo | `videochannel` |
| Capítulo | `videochapter` |
| Nome do conteúdo (variável) | `videoname` |
| Duração de conteúdo (variável) | `videolength` |
| Nome do anúncio (variável) | `videoadname` |
| Comprimento do anúncio (variável) | `videoadlength` |
| Programa | `videoshow` |
| Temporada | `videoseason` |
| Episódio | `videoepisode` |
| Rede | `videonetwork` |
| Mostrar tipo | `videoshowtype` |
| Carregamento de anúncio | `videoadload` |
| MVPD | `videomvpd` |
| Faixa de horário | `videodaypart` |
| Anunciante | `videoadadvertiser` |
| ID da campanha | `videoadcampaign` |
| Gênero | `videogenre` |
| Tipo de fluxo | `videostreamtype` |
| IDs de erro do SDK do reprodutor | `videoqoeplayersdkerrors` |
| IDs de erro externo | `videoqoeextneralerrors` |
| Tipo de feed de mídia | `videofeedtype` |
| Entrada do caminho da mídia | `entryvideopath` |
| Saída do caminho da mídia | `exitvideopath` |
| Entrada do gênero | `entryvideogenre` |
| Saída do gênero | `exitvideogenre` |
| Entrada das IDs de erro do Player SDK | `entryvideoqoeplayersdkerrors` |
| Saída das IDs de erro do Player SDK | `exitvideoqoeplayersdkerrors` |
| Entrada das IDs de erro externo | `entryvideoqoeextneralerrors` |
| Saída das IDs de erro externo | `exitvideoqoeextneralerrors` |

### Adobe Social

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Termos | `socialterm` |
| Plataformas sociais / Propriedades | `socialcontentprovider` |
| Autores | `socialauthor` |
| Idioma | `sociallanguage` |
| Latitude / longitude | `sociallatlong` |
| Códigos de acompanhamento de ativos | `socialassettrackingcode` |
| Propriedades sociais possuídas | `socialaccountandappids` |
| IDs de post possuídas | `socialownedpostids` |
| Definições sociais possuídas | `socialinteractiontype` |
| IDs de propriedades possuídas | `socialownedpropertyid` |
| Propriedade x aplicativo possuídos | `socialownedpropertypropertyvsapp` |
| Nome de propriedade possuído | `socialownedpropertyname` |
| Propriedade de definição x post possuída | `socialowneddefinitionpropertyvspost` |
| Tipos de Insight de definição possuído | `socialowneddefinitioninsighttype` |
| Valor de Insight de definição possuído | `socialowneddefinitioninsightvalue` |
| Métrica de definição possuída | `socialowneddefinitionmetric` |
| Ativo | `socialmediaid` |

### SDK móvel

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Data da primeira inicialização | `mobileinstalldate` |
| ID do aplicativo | `mobileappid` |
| Número de Lançamento | `mobilelaunchnumber` |
| Dias desde a primeira utilização | `mobiledayssincefirstuse` |
| Dias desde a última utilização | `mobiledayssincelastuse` |
| Horário do dia (SDK) | `mobilehourofday` |
| Dia da semana (SDK) | `mobiledayofweek` |
| Sistema operacional (SDK) | `mobileosenvironment` |
| Dias desde a última atualização | `mobiledayssincelastupgrade` |
| Inicializações desde a última atualização | `mobilelaunchessincelastupgrade` |
| Nome do dispositivo (SDK) | `mobiledevice` |
| Versão do sistema operacional (SDK) | `mobileosversion` |
| Maior sinal | `mobilebeaconmajor` |
| Menor sinal | `mobilebeaconminor` |
| UUID do sinal | `mobilebeaconuuid` |
| Proximidade do sinal | `mobilebeaconproximity` |
| Localização (abaixo de 10 km) | `latlon1` |
| Localização (abaixo de 100 m) | `latlon23` |
| Localização (abaixo de 1 m) | `latlon45` |
| Nome do ponto de interesse | `pointofinterest` |
| Distância até o centro do ponto de interesse | `pointofinterestdistance` |
| Precisão do local | `mobileplaceaccuracy` |
| Categoria do local | `mobileplacecategory` |
| ID do local | `mobileplaceid` |
| Entrada do maior sinal | `entrymobilebeaconmajor` |
| Saída do maior sinal | `exitmobilebeaconmajor` |
| Entrada do menor sinal | `entrymobilebeaconminor` |
| Saída do menor sinal | `exitmobilebeaconminor` |
| Entrada do UUID do sinal | `entrymobilebeaconuuid` |
| Saída do UUID do sinal | `exitmobilebeaconuuid` |
| Entrada da proximidade do sinal | `entrymobilebeaconproximity` |
| Saída da proximidade do sinal | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| ID do AMO | `amo_cid` |

### Activity Map

| Nome da dimensão (visível na interface do usuário do Analytics) | ID da dimensão (usada em solicitações de API) |
|--- |--- |
| Link por região do Activity Map | `clickmaplinkbyregion` |
| Região do Activity Map | `clickmapregion` |
| Link para o Activity Map | `clickmaplink` |
| Página do Activity Map | `clickmappage` |

### Integração Nielsen

For more information on how to implement this integration, see the [Nielsen Extension](https://exchange.adobe.com/experiencecloud.details.101361.html).

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
