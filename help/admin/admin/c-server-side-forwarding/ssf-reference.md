---
description: Uma lista detalhada e descrições das variáveis de configuração, cabeçalhos HTTP e sinais de dados nas chamadas de encaminhamento pelo lado do servidor.
seo-description: Uma lista detalhada e descrições das variáveis de configuração, cabeçalhos HTTP e sinais de dados nas chamadas de encaminhamento pelo lado do servidor.
seo-title: Referência de código e dados de encaminhamento pelo lado do servidor
title: Referência de código e dados de encaminhamento pelo lado do servidor
uuid: 3 eb 3 ea 0 f-a 530-448 d-bba 5-6408 b 2490 dc 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Referência de código e dados de encaminhamento pelo lado do servidor

Uma lista detalhada e descrições das variáveis de configuração, cabeçalhos HTTP e sinais de dados nas chamadas de encaminhamento pelo lado do servidor.

## Variáveis de configuração {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parameters prefixed with `d_*` identify special, system-level key-value pairs used by our [data collection servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) (DCS). Consulte também [Atributos suportados para chamadas de API DCS](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Parâmetro | Descrição |
|--- |--- |
| d_rs | (Gets set with legacy/tracking-server-based server-side forwarding) <br>Set to the report suites passed in with the hit to Analytics. |
| d_dst_filter | (Gets set with report-suite-based server-side forwarding)  <br>Set to the report suite IDs passed in with the hit to Analytics. |
| d_dst | Defina d_dst=1<br> se a solicitação ao Analytics estiver esperando que o conteúdo sobre o destino seja retornado para o cliente. |
| d_mid | A Experience Cloud ID enviada ao Analytics. |

## Cabeçalhos HTTP {#section_0549705E76004F9585224AEF872066C0}

Esses cabeçalhos são campos que contêm informações como solicitações de dados e respostas em uma chamada HTTP.

<!-- Meike, missing link in table below: "See Understanding Calls to the Demdex Domain" -->

| Cabeçalho HTTP | Descrição |
|--- |--- |
| Host | Isso é definido como o nome do host de coleta de dados específico do cliente especificado no arquivo de configuração de host do Analytics. Aparece como   `host name .demdex.net` .  Consulte Compreender as chamadas para o domínio Demdex . |
| User-Agent | Defina para o cabeçalho User-Agent enviado para o Analytics. |
| X-Original-User-Agent | É definido somente se um agente de usuário alternativo tiver sido especificado por um destes cabeçalhos: </br>`X-Device-User-Agent\ `  </br>`X-Original-User-Agent\`   </br>`X-OperaMini-Phone-UA\`   </br>`X-Skyfire-Phone\`    </br>`X-Bolt-Phone-UA\` |
| X-Forwarded-For | Defina para o endereço IP do cliente que fez a solicitação. O Analytics já terá analisado o cabeçalho de entrada `X-Forwarded-For` e determinado o endereço IP correto para usar. |
| Accept-Language | Defina para o cabeçalho `Accept-Language` enviado para o Analytics. |
| Referer | Definido para o URL da página enviado ao Analytics ou obtido do cabeçalho Referer enviado ao Analytics. |

## Sinais definidos pelo cliente {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parameters prefixed with `c_` identify customer-defined variables. Consulte também [Atributos suportados para chamadas de API DCS](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Sinal | Descrição |
|--- |--- |
| c_browserWidth e c_browserHeight | Largura e altura da janela do navegador. |
| c_campaign | Definido por s.campaign . |
| c_channel | Definido por s.channel . |
| c_clientDateTime | Carimbo de data e hora formatado como dd/mm/aaa hh: mm: ss W TZ. TZ está em minutos e corresponde o retorno do método Date.getTimezoneOffset. |
| c_colorDepth | Especificado como uma cor de 16 ou 32 bits. |
| c_connectionType | Especifica o tipo de conexão. As opções incluem:<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | Exemplos:<ul><li>Appmeasurement: s. contextdata</li><li>[" category "] =" news ";</li><li>Sinal: c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Especifica se cookies podem ser habilitados. As opções incluem: sim, não, desconhecido |
| c_currencyCode | Tipo de moeda usada na transação. |
| c_evar# | eVars personalizadas |
| c_events | Definido por s.events . |
| c_hier# | Variáveis personalizadas de hierarquia. |
| c_javaEnabled | Especifica se o Java pode ser habilitado. As opções incluem: sim, não, desconhecido |
| c_javaScriptVersion | Versão do JavaScript suportada por um navegador. |
| c_latitude | Latitude numérica |
| c_linkClick | As opções incluem: personalizado, saída de download |
| c_linkCustomName | O nome personalizado (se houver) fornecido para o link. |
| c_linkDownloadURL | O URL dos links de download. |
| c_linkExitURL | O URL do link de saída. |
| c_list# | Variáveis personalizadas de lista. |
| c_longitude | Longitude numérica. |
| c_mediaPlayerType | Para solicitações de rastreamento de transmissão de mídia. As opções incluem:  outro, primetime |
| c_pageName | O nome da página (se definido). |
| c_pageURL | O endereço da página na barra de endereço do navegador. |
| c_products | A string do produto (definido por s.products ). |
| c_prop | Propriedades personalizadas. |
| c_purchaseID | Uma ID única para a compra. |
| c_referrer | A página anterior à página atual. |
| c_screenResolution | Largura e altura da tela (em pixels). |
| c_server | Nome do servidor da Web (definido por s.server ). |
| c_state | Região geográfica (definido por s.state ). |
| c_timezone | Deslocamento de tempo (em horas). |
| c_transactionID | Uma ID exclusiva para cada transação. |
| c_zip | Código postal (definido por s.zip ). |
