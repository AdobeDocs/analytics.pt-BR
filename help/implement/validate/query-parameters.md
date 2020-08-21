---
title: Parâmetros de consulta para coleta de dados
description: Lista todos os parâmetros da cadeia de caracteres de consulta usados em solicitações de imagem.
translation-type: ht
source-git-commit: edf3ac3ebc99444b86bcd9239cef9ed84d797565
workflow-type: ht
source-wordcount: '648'
ht-degree: 100%

---


# Parâmetros de consulta para coleta de dados

A tabela a seguir lista todos os parâmetros da cadeia de caracteres de consulta que a Adobe usa em solicitações de imagem. Essas informações podem ser usadas ao depurar usando [analisadores de pacote](packet-monitor.md), ao codificar [solicitações de imagem codificada](../other/hardcoded.md) ou ao usar [Variáveis dinâmicas](../vars/page-vars/dynamic-variables.md).

| Parâmetro | Variável de implementação do Analytics | Descrição |
| --- | --- | --- |
| `aamlh` | Nenhum | Dica de localização do Audience Manager. Usada na integração do perfil compartilhado da Experience Cloud. |
| `aamb` | Nenhum | Blob do Audience Manager. Usado na integração do perfil compartilhado da Experience Cloud. |
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
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensões de hierarquia. |
| `hp` | Nenhum | Não está mais em uso. Em versões anteriores do Adobe Analytics, determinava se o URL atual era a página inicial do navegador. |
| `j` | Nenhum | A versão do JavaScript instalada no navegador. |
| `k` | Nenhum | Usada na dimensão [Suporte a cookies](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variáveis da Lista. |
| `mid` | Nenhum | ID de visitante da Experience Cloud. |
| `ndh` | Nenhum | Sinalizador que indica se a solicitação de imagem se originou no AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Ajuda a determinar onde os cookies são definidos. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificador de objeto da última página. Usado no Activity Map. |
| `ot` | Nenhum | Nome do objeto da última página. Usado em versões anteriores do Activity Map. |
| `p` | Nenhum | Não está mais em uso. Lista de plug-ins usados no navegador. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Usado na dimensão [Página](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Usada na dimensão [Páginas não encontradas](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Nenhum | Definido somente para novos visitantes e sempre definido como `true`. Ajuda a evitar redirecionamentos infinitos. |
| `pe` | [`linkType`](../vars/config-vars/linktype.md) | Determina o tipo de link personalizado. Necessário para [Links personalizados](/help/components/dimensions/custom-link.md), [Links de download](/help/components/dimensions/download-link.md) e [Links da saída](/help/components/dimensions/exit-link.md). |
| `pev1` | Nenhum | O URL no qual o link personalizado ocorreu. |
| `pev2` | [`linkName`](../vars/config-vars/linkname.md) | Nome amigável do link personalizado. |
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
| `t` | Nenhum | Data/hora da ocorrência gerada. Usa o formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` é data/hora no JavaScript. O mês `0` é janeiro, enquanto o mês `11` é dezembro.<br>- `w` é o dia da semana. `0` é domingo, enquanto `6` é sábado.<br>- `o` é o desvio GMT negativo em minutos. Por exemplo, `420` é GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | O carimbo de data e hora personalizado definido com a ocorrência. Normalmente é usado para rastreamento offline. |
| `v` | Nenhum | Usada na dimensão [Habilitada para Java](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) ou dimensões de conversão personalizadas. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variável da ID do visitante. |
| `vmk` | `vmk` | Não está mais em uso. Chave de migração de visitante, que ajudou a migrar implementações de cookies de terceiros para cookies próprios. |
| `vvp` | `variableProvider` | Usado em Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Usado com fontes de dados para unir dados online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Usado na dimensão [CEP](/help/components/dimensions/zip-code.md). |
