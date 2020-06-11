---
title: eVar
description: Uma dimensão personalizada que você pode usar no relatórios.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 5%

---


# eVar

*Esta página de ajuda descreve como as eVars funcionam como uma dimensão. Para obter informações sobre como implementar eVars, consulte[eVars](/help/implement/vars/page-vars/evar.md)no guia Implementar usuário.*

As eVars são variáveis personalizadas que podem ser usadas da maneira que você desejar. Se você tiver um documento [de design de](/help/implement/prepare/solution-design.md)solução, a maioria das dimensões específicas da sua organização acabarão como eVars. Por padrão, as eVars persistem além da ocorrência em que estão definidas. Você pode personalizar a expiração e a alocação em Variáveis [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversão nas configurações do conjunto de relatórios.

O número de eVars disponíveis depende de seu contrato com a Adobe. Até 250 eVars estarão disponíveis se seu contrato com a Adobe oferecer suporte para isso.

## Preencher eVars com dados

Cada eVar coleta dados da string [`v1` - `v250` query string](/help/implement/validate/query-parameters.md) em solicitações de imagem. Por exemplo, o parâmetro da string de `v1` query coleta dados para eVar1, enquanto o parâmetro da string de `v222` query coleta dados para eVar222.

O AppMeasurement, que compila variáveis JavaScript em uma solicitação de imagem para coleta de dados, usa as variáveis `eVar1` - `eVar250`. Consulte [eVar](/help/implement/vars/page-vars/evar.md) no guia Implementar usuário para obter diretrizes de implementação.

## Valores de dimensão

Como as eVars contêm strings personalizadas na implementação, sua organização determina quais valores de dimensão são para cada eVar. Certifique-se de registrar a finalidade de cada eVar e os valores de dimensão típicos em um documento [de design de](/help/implement/prepare/solution-design.md)solução.

## Como funcionam as eVars

Quando você envia dados para o Adobe Analytics, os servidores de coleta de dados traduzem a ocorrência em uma única linha de dados com centenas de colunas. Duas colunas são dedicadas a cada eVar; um para coleta direta de dados e outro para valores persistentes.

* Uma coluna padrão contém dados enviados para a Adobe a partir da solicitação de imagem.
* Uma coluna &quot;pós&quot; contém dados persistentes, que dependem da expiração e da alocação da eVar.

Em quase todas as circunstâncias, a `post_evar` coluna é usada nos relatórios.

### Como as eVars se vinculam às métricas

eventos bem-sucedidos e eVars são frequentemente definidos em solicitações de imagem diferentes. A `post_evar` coluna permite que os valores de eVar se vinculem aos eventos, mostrando os dados no relatórios. Faça a seguinte visita, por exemplo:

1. Um visitante chega ao seu site no seu home page.
2. Eles pesquisam por &quot;gatos&quot; usando a pesquisa interna do site. Sua implementação usa eVar1 para pesquisa interna.
3. Eles visualizações um produto e continuam pelo processo de checkout.

Uma versão simplificada dos dados brutos seria semelhante ao seguinte:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* A `visitor_id` coluna vincula ocorrências ao mesmo visitante. Nos dados brutos reais, os valores concatenados de `visid_high` e `visid_low` determinam a ID do visitante.
* A `pagename` coluna preenche a dimensão Páginas.
* A `evar` coluna determina as ocorrências quando eVar1 foi explicitamente definida.
* O `post_evar1` carrega o valor anterior, dependendo da alocação e do conjunto de expiração da variável nas configurações do conjunto de relatórios.
* A `event_list` coluna contém todos os dados de métrica. Neste exemplo, `event1` é &quot;Pesquisas&quot; e os outros eventos são métricas padrão do carrinho de compras. Nos dados brutos reais, `event_list` contém um conjunto de números delimitados por vírgulas com uma tabela de pesquisa que vincula esses números a uma métrica.

### Traduzindo a coleta de dados para o relatórios

As ferramentas no Adobe Analytics, como a área de trabalho da Análise, funcionam fora desses dados coletados. Por exemplo, se você puxou um relatório usando eVar1 como a dimensão e Pedidos como a métrica, você verá um relatório semelhante ao seguinte:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

A área de trabalho da Análise puxa esse relatório usando a seguinte lógica:

* Analise todos os `event_list` valores e escolha todas as ocorrências com `purchase` eles.
* Dessas ocorrências, exiba o `post_evar1` valor.

### A importância da alocação e da expiração

Como a alocação e a expiração determinam quais valores persistem, eles são vitais para obter o máximo valor de uma implementação do Analytics. A Adobe recomenda que você discuta em sua organização como vários valores para cada eVar são tratados (alocação) e quando as eVars param de persistir nos dados (expiração).

* Por padrão, uma eVar usa a última alocação. Novos valores substituem os valores persistentes.
* Por padrão, uma eVar usa uma expiração de visita. Quando uma visita termina, os valores param de copiar de linha para linha na `post_evar` coluna.

Você pode alterar a alocação e a expiração da eVar em Variáveis [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversão nas configurações do conjunto de relatórios.

## Valor de eVars em props

A Adobe recomenda o uso de eVars na maioria dos casos, com suporte do seguinte:

* As eVars têm um limite de 255 bytes nos relatórios. As props têm um limite de 100 bytes.
* As props, por padrão, não persistem além da ocorrência às quais que estão definidas. As eVars têm expiração personalizada, permitindo determinar quando uma eVar não mais recebe incremento por um evento subsequente. No entanto, se você usar o processamento [de tempo do](/help/components/vrs/vrs-report-time-processing.md)relatório, props e eVars poderão usar um modelo de atribuição personalizado.
* A Adobe suporta até 250 eVars e apenas 75 props.

Consulte [prop](prop.md) para obter mais comparações entre props e eVars.
