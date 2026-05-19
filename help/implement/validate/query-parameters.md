---
title: Parâmetros de consulta para coleta de dados
description: Lista todos os parâmetros da cadeia de caracteres de consulta usados em solicitações de imagem.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 725
ht-degree: 92%

---

# Parâmetros de consulta para coleta de dados

A tabela a seguir lista todos os parâmetros da cadeia de caracteres de consulta que a Adobe usa em solicitações de imagem. Essas informações podem ser usadas ao depurar usando [analisadores de pacote](packet-monitor.md), ao codificar [solicitações de imagem codificada](../other/hardcoded.md) ou ao usar [Variáveis dinâmicas](../vars/page-vars/dynamic-variables.md).

| Parâmetro | Variável de implementação do Analytics | Descrição |
| --- | --- | --- |
| `aamlh` | Nenhum | Dica de localização do Audience Manager. Usado na integração do Perfil compartilhado corporativo CX. |
| `aamb` | Nenhum | Blob do Audience Manager. Usado na integração do Perfil compartilhado corporativo CX. |
| `aid` | Nenhum | ID de visitante do Analytics. |
| `AQB` | Nenhum | Indica o início a cadeia de caracteres de uma solicitação de imagem. |
| `AQE` | Nenhum | Indica o fim de uma solicitação de imagem e significa que a solicitação não foi truncada. |
| `bh` | Nenhum | Altura do navegador (em pixels). Usada na dimensão [Altura do navegador](/help/components/dimensions/browser-height.md). |
| `bw` | Nenhum | Largura do navegador (em pixels). Usada na dimensão [Largura do navegador](/help/components/dimensions/browser-width.md). |
| `c` | Nenhum | Qualidade de cor (em bits). Usada na dimensão [Intensidade de cor](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica o início das variáveis de dados de contexto. Nunca contém um valor. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica o fim das variáveis de dados de contexto. Nunca contém um valor. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) ou variáveis de tráfego personalizadas. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | A moeda utilizada na ocorrência. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | O número de períodos em um domínio. Usado para ajudar a armazenar cookies corretamente. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | A codificação de caracteres da solicitação de imagem. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | A duração do cookie do visitante. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Usada na dimensão [Seções do site](/help/components/dimensions/site-section.md). |
| `cp` | Nenhum | Usada na dimensão [Tipo de ocorrência](/help/components/dimensions/hit-type.md). |
| `ct` | Nenhum | Usada na dimensão [Tipo de conexão](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica o que usar para variáveis dinâmicas. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Encurtar para a cadeia de caracteres de consulta `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Lista de eventos separados por vírgulas na página. Usada pela maioria das [métricas](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | O URL atual da página, até 255 bytes. Usada na dimensão [URL da página](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Os URLs maiores que 255 bytes são divididos. Os primeiros 255 bytes aparecem no parâmetro `g` e todos os bytes restantes aparecem no parâmetro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Encurtar para a cadeia de caracteres de consulta `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Encurtar para a cadeia de caracteres de consulta `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefixo para várias variáveis que representam [Dicas do cliente](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensões de hierarquia. |
| `hp` | Nenhum | Não está mais em uso. Em versões anteriores do Adobe Analytics, determinava se o URL atual era a página inicial do navegador. |
| `j` | Nenhum | A versão do JavaScript instalada no navegador. |
| `k` | Nenhum | Usada na dimensão [Suporte a cookies](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variáveis da Lista. |
| `lrt` | Nenhum | O &quot;tempo da última solicitação&quot;, que é o tempo de ida e volta para a última solicitação, em milissegundos. Ele é enviado somente quando mais de uma solicitação está saindo de uma página ou quando a página é um aplicativo de página única (SPA). |
| `mid` | Nenhum | ID de visitante corporativo CX. |
| `ndh` | Nenhum | Sinalizador que indica se a solicitação de imagem se originou no AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Ajuda a determinar onde os cookies são definidos. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificador de objeto da última página. Usado no Activity Map. |
| `ot` | Nenhum | Nome do objeto da última página. Usado em versões anteriores do Activity Map. |
| `p` | Nenhum | Não está mais em uso. Lista de plug-ins usados no navegador. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Usado na dimensão [Página](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Usada na dimensão [Páginas não encontradas](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Nenhum | Definido somente para novos visitantes e sempre definido como `true`. Ajuda a evitar redirecionamentos infinitos se um visitante rejeitar cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determina o tipo de link personalizado. Necessário para [Links personalizados](/help/components/dimensions/custom-link.md), [Links de download](/help/components/dimensions/download-link.md) e [Links da saída](/help/components/dimensions/exit-link.md). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | O URL no qual o link personalizado ocorreu. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Nome amigável do link personalizado. |
| `pev3` | Nenhum | Não está mais em uso. Marcos rastreados em versões anteriores do relatório de vídeo. |
| `pf` | Nenhum | Sinalizador da plataforma; somente para uso da Adobe. Não alterar. |
| `pid` | Nenhum | Identificador de página da última página. Usado em versões anteriores do Activity Map. |
| `pidt` | Nenhum | Tipo de identificador de página da última página. Usado em versões anteriores do Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Encurtar para a cadeia de caracteres de consulta `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variável products. Usado nas dimensões [Produto](/help/components/dimensions/product.md) e [Categoria](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Usado para desduplicar compras. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | O URL referenciador da ocorrência. Usado em dimensões de fontes de tráfego, como [Referenciador](/help/components/dimensions/referrer.md) e [Domínio referenciador](/help/components/dimensions/referring-domain.md) |
| `s` | Nenhum | Resolução da tela, em `width x height`. Usada na dimensão [Resoluções do monitor](/help/components/dimensions/monitor-resolution.md). |
| `server` | [`server`](../vars/page-vars/server.md) | Dimensão do [Servidor](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Encurtar para a cadeia de caracteres de consulta `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimensão de estado. |
| `t` | Nenhum | Data/hora da ocorrência gerada. Usa o formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` é data/hora no JavaScript. O mês `0` é janeiro, enquanto o mês `11` é dezembro.<br>- `w` é o dia da semana. `0` é domingo, enquanto `6` é sábado.<br>- `o` é o deslocamento GMT negativo em minutos. Por exemplo, `420` é GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | O carimbo de data e hora personalizado definido com a ocorrência. Normalmente é usado para rastreamento offline. |
| `v` | Nenhum | Usada na dimensão [Habilitada para Java](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) ou dimensões de conversão personalizadas. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variável da ID do visitante. |
| `vidn` | Nenhum | Definido pelo AppMeasurement para novos visitantes. Contém o valor da ID armazenado no cookie do visitante. |
| `vmk` | `vmk` | Não está mais em uso. Chave de migração de visitante, que ajudou a migrar implementações de cookies de terceiros para cookies próprios. |
| `vvp` | `variableProvider` | Usado em Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Usado com fontes de dados para unir dados online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Usado na dimensão [CEP](/help/components/dimensions/zip-code.md). |
