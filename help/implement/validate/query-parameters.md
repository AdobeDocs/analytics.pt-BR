---
title: Parâmetros de consulta para coleta de dados
description: Lista todos os parâmetros da cadeia de caracteres de consulta usados em solicitações de imagem.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 1111
ht-degree: 46%

---

# Parâmetros de consulta para coleta de dados

A tabela a seguir lista todos os parâmetros da cadeia de caracteres de consulta que a Adobe usa em solicitações de imagem. Essas informações são úteis ao depurar com [analisadores de pacotes](packet-monitor.md), ao codificar [solicitações de imagem codificada](../other/hardcoded.md) ou ao usar [variáveis dinâmicas](../vars/page-vars/dynamic-variables.md).

| Parâmetro | Variável de implementação do Analytics | Descrição |
| --- | --- | --- |
| `aamlh` | Nenhum | Dica de localização do Audience Manager. Identifica o data center regional usado para sincronização da Audience Manager ID por meio do Serviço de ID do visitante. |
| `aamb` | Nenhum | Blob do Audience Manager. Dados de perfil do Audience Manager codificados transmitidos durante a sincronização de ID pelo Serviço de ID do visitante. |
| `aid` | Nenhum | A ID de visitante herdada do Analytics, armazenada no cookie `s_vi`. Substituído pelo parâmetro `mid` em implementações modernas. |
| `AQB` | Nenhum | Indica o início a cadeia de caracteres de uma solicitação de imagem. |
| `AQE` | Nenhum | Indica o fim de uma solicitação de imagem e significa que a solicitação não foi truncada. |
| `bh` | Nenhum | Altura do navegador (em pixels). Usada na dimensão [[!UICONTROL Altura do navegador]](/help/components/dimensions/browser-height.md). |
| `bw` | Nenhum | Largura do navegador (em pixels). Usada na dimensão [[!UICONTROL Largura do navegador]](/help/components/dimensions/browser-width.md). |
| `c` | Nenhum | Qualidade de cor (em bits). Usada na dimensão [[!UICONTROL Intensidade de cor]](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica o início das variáveis de dados de contexto. Nunca contém um valor. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica o fim das variáveis de dados de contexto. Nunca contém um valor. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) ou variáveis de tráfego personalizadas. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | A moeda utilizada na ocorrência. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Não está mais em uso.** O número de períodos em um domínio. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | A codificação de caracteres da solicitação de imagem. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | A duração do cookie do visitante. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Usada na dimensão [[!UICONTROL Seções do site]](/help/components/dimensions/site-section.md). |
| `cp` | [`customerPerspective`](../vars/page-vars/customerperspective.md) | Especifica se uma ocorrência do aplicativo móvel ocorreu enquanto o aplicativo estava em primeiro ou segundo plano. Usado na dimensão [[!UICONTROL Tipo de ocorrência]](/help/components/dimensions/hit-type.md). |
| `ct` | Nenhum | Usado na dimensão [[!UICONTROL Tipo de conexão]](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica o que usar para variáveis dinâmicas. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Encurtar para o parâmetro `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Lista de eventos separados por vírgulas na página. Usada pela maioria das [métricas](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | O URL atual da página, até 255 bytes. Usada na dimensão [[!UICONTROL URL da página]](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../vars/page-vars/pageurl.md) | Os URLs maiores que 255 bytes são divididos. Os primeiros 255 bytes aparecem no parâmetro `g` e todos os bytes restantes aparecem no parâmetro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Encurtar para o parâmetro `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Encurtar para o parâmetro `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefixo para várias variáveis que representam [Dicas do cliente](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/page-variables.md#retired-page-variables) | **Não está mais em uso.** Dimensões de hierarquia. |
| `hp` | Nenhum | **Não está mais em uso.** Em versões anteriores do Adobe Analytics, determinava se o URL atual era a página inicial do navegador. |
| `j` | Nenhum | **Não está mais em uso.** A versão do JavaScript instalada no navegador. |
| `k` | Nenhum | Usada na dimensão [[!UICONTROL Suporte a cookies]](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variáveis da Lista. |
| `lat` | Nenhum | **Não está mais em uso.** Latitude Definido por implementações do Mobile SDK herdadas; as implementações móveis atuais enviam a geolocalização por meio de sequências de dados. |
| `lon` | Nenhum | **Não está mais em uso.** Longitude. Definido por implementações do Mobile SDK herdadas; as implementações móveis atuais enviam a geolocalização por meio de sequências de dados. |
| `lrt` | Nenhum | O &quot;tempo da última solicitação&quot;, que é o tempo de ida e volta para a última solicitação, em milissegundos. Ele é enviado somente quando mais de uma solicitação é enviada de uma única página, como em um aplicativo de página única (SPA). |
| `mcorgid` | Nenhum | A ID da organização IMS, que identifica a organização para o Serviço de ID de visitante. |
| `mid` | Nenhum | Usado na [[!UICONTROL dimensão ID de visitante da Experience Cloud]](/help/components/dimensions/experience-cloud-visitor-id.md). |
| `ms_a` | Nenhum | Definido pelo Media SDK como `1` quando a mídia de streaming rastreada é de áudio em vez de vídeo. |
| `ndh` | Nenhum | Adicionado pelo AppMeasurement a cada solicitação de imagem gerada. Como as solicitações codificadas normalmente a omitem, sua presença indica que a ocorrência veio do AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Não está mais em uso.** Ajuda a determinar onde os cookies são definidos. |
| `oi` | Nenhum | **Não está mais em uso.** Instância do objeto da última página. Usado em versões anteriores do Activity Map. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificador de objeto da última página. Usado na versão atual do Activity Map. |
| `oidt` | Nenhum | **Não está mais em uso.** Tipo de identificador de objeto da última página. Usado em versões anteriores do Activity Map. |
| `ot` | Nenhum | **Não está mais em uso.** Nome do objeto da última página. Usado em versões anteriores do Activity Map. |
| `p` | Nenhum | **Não está mais em uso.** Lista de plug-ins usados no navegador. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Usado na dimensão [[!UICONTROL Página]](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Usada na dimensão [[!UICONTROL Páginas não encontradas]](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Nenhum | Sinalizador de redirecionamento de verificação de cookie persistente. Definido pelos servidores de coleta de dados da Adobe para novos visitantes e sempre definido como `true`. Quando o suporte a cookies de um novo visitante é desconhecido, o servidor de coleta de dados redireciona a solicitação de imagem para si mesmo com esse sinalizador para confirmar se a verificação de cookie persistente já ocorreu. Esse parâmetro impede redirecionamentos infinitos se o visitante rejeitar cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determina o tipo de ocorrência. Os valores válidos incluem `lnk_o` ([[!UICONTROL Link personalizado]](/help/components/dimensions/custom-link.md)), `lnk_d` ([[!UICONTROL Link de download]](/help/components/dimensions/download-link.md)), `lnk_e` ([[!UICONTROL Link de saída]](/help/components/dimensions/exit-link.md)) e `tnt` (uma ocorrência do Analytics for Target). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | O URL no qual o link personalizado ocorreu. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | O nome amigável do [link personalizado](/help/components/dimensions/custom-link.md). |
| `pev3` | Nenhum | **Não está mais em uso.** Marcos rastreados em versões anteriores do relatório de vídeo. |
| `pf` | Nenhum | Sinalizador da plataforma; somente para uso da Adobe. Não alterar. |
| `pid` | Nenhum | **Não está mais em uso.** Identificador de página da última página. Usado em versões anteriores do Activity Map. |
| `pidt` | Nenhum | **Não está mais em uso.** Tipo de identificador de página da última página. Usado em versões anteriores do Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Encurtar para o parâmetro `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variável products. Usado nas dimensões [[!UICONTROL Produto]](/help/components/dimensions/product.md) e [[!UICONTROL Categoria]](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Usado na dimensão [[!UICONTROL ID de Compra]](/help/components/dimensions/purchase-id.md). |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | O URL referenciador da ocorrência. Usado em dimensões de fontes de tráfego, como [[!UICONTROL Referenciador]](/help/components/dimensions/referrer.md) e [[!UICONTROL Domínio referenciador]](/help/components/dimensions/referring-domain.md). |
| `s` | Nenhum | Resolução da tela, em `width x height`. Usada na dimensão [[!UICONTROL Resoluções do monitor]](/help/components/dimensions/monitor-resolution.md). |
| `sdid` | Nenhum | ID de dados complementares. Vincula várias ocorrências que descrevem o mesmo evento, como ocorrências do Analytics e do Target em uma integração do [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). |
| `server` | [`server`](../vars/page-vars/server.md) | Usado na dimensão [[!UICONTROL Servidor]](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Encurtar para o parâmetro `server`. |
| `state` | [`state`](../vars/page-vars/page-variables.md#retired-page-variables) | **Não está mais em uso.** Registrado o estado americano em que um visitante entrou, normalmente por meio de um formulário de envio ou de cobrança. |
| `t` | Nenhum | Data/hora da ocorrência gerada. Usa o formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` é data/hora no JavaScript. O mês `0` é janeiro, enquanto o mês `11` é dezembro.<br>- `w` é o dia da semana. `0` é domingo, enquanto `6` é sábado.<br>- `o` é o deslocamento GMT negativo em minutos. Por exemplo, `420` é GMT-7. |
| `tnt` | Nenhum | Carga de dados de destino usada em integrações do [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). Enviado quando `pe=tnt`. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | O carimbo de data e hora personalizado definido com a ocorrência. Normalmente é usado para rastreamento offline. |
| `u` | Nenhum | **Não está mais em uso.** Marcador de conta usado nas versões anteriores do Activity Map. |
| `v` | Nenhum | Usada na dimensão [[!UICONTROL Habilitada para Java]](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Usado na dimensão [[!UICONTROL Código de rastreamento]](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) ou dimensões de conversão personalizadas. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variável de substituição de ID de visitante. |
| `vidn` | Nenhum | Definido pelos servidores de coleta de dados da Adobe para novos visitantes, que acompanham o parâmetro `pccr` na solicitação de imagem redirecionada. Contém o valor da ID de visitante armazenada no cookie do visitante. |
| `vmf` | [`visitorMigrationServer`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Não está mais em uso.** Servidor de migração do visitante usado durante a migração de cookies de terceiros para cookies próprios. |
| `vmt` | [`visitorMigrationKey`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Não está mais em uso.** Chave de migração de visitante, que ajudou a migrar implementações de cookies de terceiros para cookies próprios. |
| `vvp` | Nenhum | **Não está mais em uso.** Provedor de variável usado no Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Usado com fontes de dados para unir dados online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Usado na dimensão [CEP](/help/components/dimensions/zip-code.md). |
