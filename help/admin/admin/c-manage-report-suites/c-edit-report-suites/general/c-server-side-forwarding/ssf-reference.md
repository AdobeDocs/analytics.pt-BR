---
description: Uma lista detalhada e descrições das variáveis de configuração, cabeçalhos HTTP e sinais de dados nas chamadas de encaminhamento pelo lado do servidor.
title: Referência de dados e de código do encaminhamento pelo lado do servidor
feature: Server-Side Forwarding
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 97%

---

# Referência de dados e de código do encaminhamento pelo lado do servidor

Uma lista detalhada e descrições das variáveis de configuração, cabeçalhos HTTP e sinais de dados nas chamadas de encaminhamento pelo lado do servidor.

## Variáveis de configuração {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parâmetros com o prefixo `d_*` identificam pares de valores-chave especiais em nível de sistema usados pelos [servidores de coleta de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=pt-BR) (DCS). Consulte também [Atributos suportados para chamadas de API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=pt-BR).

| Parâmetro | Descrição |
|--- |--- |
| `d_rs` | (É definido com encaminhamento pelo lado do servidor baseado em servidor de rastreamento/legado) <br>Defina para os conjuntos de relatórios enviados para o Analytics com a ocorrência. |
| `d_dst_filter` | (É definido com o encaminhamento pelo lado do servidor baseado em conjunto de relatórios) <br>Defina para as IDs do conjunto de relatórios enviadas para o Analytics com a ocorrência. |
| `d_dst` | Defina `d_dst=1`  <br>se a solicitação ao Analytics estiver esperando que o conteúdo sobre o destino seja retornado para o cliente. |
| `d_mid` | A Experience Cloud ID enviada ao Analytics. |

## Cabeçalhos HTTP {#section_0549705E76004F9585224AEF872066C0}

Esses cabeçalhos são campos que contêm informações como solicitações de dados e respostas em uma chamada HTTP.

| Cabeçalho HTTP | Descrição | h_ key aceita pelo Audience Manager |
| --- | --- | --- |
| Host | Isso é definido como o nome do host de coleta de dados específico do cliente especificado no arquivo de configuração de host do Analytics. Aparece como `host name .demdex.net`. Consulte [Compreender chamadas para o domínio Demdex](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=pt-BR). | `h_host` |
| User-Agent | Defina para o cabeçalho User-Agent enviado para o Analytics. | `h_user-agent` |
| Accept-Language | Defina para o cabeçalho `Accept-Language` enviado para o Analytics. | `h_accept-language` |
| Referer | Definido para o URL da página enviado ao Analytics ou obtido do cabeçalho do `Referer` enviado ao Analytics. | `h_referer` |
| Referenciador | Definido para o URL da página enviado ao Analytics ou obtido do cabeçalho do `Referrer` enviado ao Analytics. | `h_referrer` |
| Data | Defina para o cabeçalho do `Date` enviado para o Analytics. | `h_date` |

Além disso, um sinal `h_ip` é gerado pelo IP do host que envia a solicitação para o DCS.

## Sinais definidos pelo cliente {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parâmetros com o prefixo `c_` identificam variáveis definidas pelo cliente. Consulte também [Atributos suportados para chamadas de API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=pt-BR).

| Sinal | Descrição |
| --- |--- |
| `c_browserWidth`  e `c_browserHeight` | Largura e altura da janela do navegador. |
| `c_campaign` | Definido por `s.campaign`. |
| `c_channel` | Definido por `s.channel`. |
| `c_clientDateTime` | Carimbo dde data e hora formatado como `dd/mm/yyy hh:mm:ss  W TZ` . `TZ` está em minutos e corresponde ao retorno do método `Date.getTimezoneOffset`. |
| `c_colorDepth` | Especificado como uma cor de 16 ou 32 bits. |
| `c_connectionType` | Especifica o tipo de conexão. As opções incluem:<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | Exemplos:<ul><li>AppMeasurement: `s.contextData`</li><li>[category] = &quot;news&quot;;</li><li>Sinal: `c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | Especifica se cookies podem ser habilitados. As opções incluem: sim, não, desconhecido |
| `c_currencyCode` | Tipo de moeda usada na transação. |
| `c_evar#` | eVars personalizadas |
| `c_events` | Definido por `s.events`. |
| `c_hier#` | Variáveis de hierarquia personalizadas. |
| `c_javaEnabled` | Especifica se o Java pode ser habilitado. As opções incluem: sim, não, desconhecido |
| `c_javaScriptVersion` | Versão do JavaScript compatível com um navegador. |
| `c_latitude` | Latitude numérica |
| `c_linkClick` | As opções incluem: personalizado, download, saída |
| `c_linkCustomName` | O nome personalizado fornecido para o link (se houver). |
| `c_linkDownloadURL` | O URL dos links de download. |
| `c_linkExitURL` | O URL do link de saída. |
| `c_list#` | Variáveis personalizadas de lista. |
| `c_longitude` | Longitude numérica. |
| `c_mediaPlayerType` | Para solicitações de rastreamento de transmissão de mídia. As opções incluem: other, primetime |
| `c_pageName` | O nome da página (se definido). |
| `c_pageURL` | O endereço da página na barra de endereços do navegador. |
| `c_products` | A sequência de caracteres do produto (definido por `s.products`). |
| `c_prop` | Propriedades personalizadas. |
| `c_purchaseID` | Uma ID exclusiva para a compra. |
| `c_referrer` | A página anterior à página atual. |
| `c_screenResolution` | Largura e altura da tela (em pixels). |
| `c_server` | Nome do servidor Web (definido por `s.server`). |
| `c_state` | Região geográfica (definido por `s.state`). |
| `c_timezone` | Diferença de tempo (em horas). |
| `c_transactionID` | Uma ID exclusiva para uma transação. |
| `c_zip` | Código postal (definido por `s.zip`). |
