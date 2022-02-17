---
title: eVar
description: Uma dimensão personalizada que você pode usar nos relatórios.
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 100%

---

# eVar

*Esta página de ajuda descreve como as eVars funcionam como uma dimensão. Para obter informações sobre como implementar eVars, consulte [eVars](/help/implement/vars/page-vars/evar.md) no guia de usuário Implementar.*

As eVars são variáveis personalizadas que podem ser usadas da maneira que você desejar. Se você tiver um [documento de design de solução](/help/implement/prepare/solution-design.md)[!UICONTROL , a maioria das dimensões específicas da sua organização acabarão como eVars]. Por padrão, as eVars persistem além da ocorrência em que estão definidas. Você pode personalizar a expiração e a alocação em [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)[!UICONTROL  nas configurações do conjunto de relatórios].

O número de eVars disponíveis depende do seu contrato com a Adobe. Até 250 eVars estarão disponíveis se seu contrato com a Adobe permitir.

A caixa (alta ou baixa) usada nos relatórios é baseada no primeiro valor registrado pelo sistema de back-end. Esse valor pode ser a primeira instância vista ou pode variar em determinado período (por exemplo, mensal), dependendo da variedade e da quantidade de dados associados ao conjunto de relatórios.

## Preencher eVars com dados

Cada eVar coleta dados da [`v1` - `v250` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. Por exemplo, o parâmetro da sequência de consulta `v1` coleta dados para eVar1, enquanto o parâmetro da sequência de consulta `v222` coleta dados para eVar222.

O AppMeasurement, que compila variáveis JavaScript em uma solicitação de imagem para coleta de dados, usa as variáveis `eVar1` - `eVar250`. Consulte [eVar](/help/implement/vars/page-vars/evar.md) no guia Implementar usuário para obter diretrizes de implementação.

## Itens de dimensão

Como as eVars contêm strings personalizadas na implementação, sua organização determina quais itens de dimensão são para cada eVar. Registre a finalidade de cada eVar e os itens de dimensão típicos em um [documento de design de solução](/help/implement/prepare/solution-design.md).

## Como funcionam as eVars

Ao enviar dados para o Adobe Analytics, os servidores de coleta de dados traduzem a ocorrência em uma única linha de dados com centenas de colunas. Duas colunas são dedicadas a cada eVar; um para coleta direta de dados e outro para valores persistentes.

* Uma coluna padrão contém dados enviados para a Adobe a partir da solicitação de imagem.
* Uma coluna &quot;pós&quot; contém dados persistentes, que dependem da expiração e da alocação da eVar.

Em quase todas as circunstâncias, a coluna `post_evar` é usada nos relatórios.

### Como as eVars se vinculam às métricas

Eventos bem-sucedidos e eVars são frequentemente definidos em solicitações de imagem diferentes. A coluna `post_evar` permite que os valores de eVar se vinculem aos eventos, mostrando os dados no relatórios. Faça a seguinte visita, por exemplo:

1. Um visitante chega ao seu site na home page.
2. Eles pesquisam por &quot;gatos&quot; usando a pesquisa interna do site. Sua implementação usa eVar1 para pesquisa interna.
3. Eles visualizam um produto e avançam para o processo de finalização.

Uma versão simplificada dos dados brutos seria semelhante ao seguinte:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* A coluna `visitor_id` vincula ocorrências ao mesmo visitante. Nos dados brutos reais, os valores concatenados de `visid_high` e `visid_low` determinam a ID do visitante.
* A coluna `pagename` preenche a dimensão Páginas.
* A coluna `evar` determina as ocorrências quando eVar1 foi explicitamente definida.
* O `post_evar1` carrega o valor anterior, dependendo da alocação e do conjunto de expiração da variável nas configurações do conjunto de relatórios.
* A coluna `event_list` contém todos os dados de métrica. Neste exemplo, `event1` é &quot;Pesquisas&quot; e os outros eventos são métricas padrão do carrinho de compras. Nos dados brutos reais, o `event_list` contém um conjunto de números delimitados por vírgulas com uma tabela de pesquisa que vincula esses números a uma métrica.

### Traduzindo a coleta de dados para relatórios

As ferramentas no Adobe Analytics, como o Analysis Workspace, funcionam fora desses dados coletados. Por exemplo, se você solicitou um relatório usando eVar1 como a dimensão e Pedidos como a métrica, você verá um relatório semelhante ao seguinte:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

O Analysis Workspace faz esse relatório usando a seguinte lógica:

* Analise todos os valores de `event_list` e escolha todas as ocorrências com `purchase` neles.
* Dessas ocorrências, exiba o valor `post_evar1`.

### A importância da alocação e da expiração

Como determinam quais valores persistem, a alocação e a expiração são essenciais para obter o máximo valor de uma implementação de análise. A Adobe recomenda que você discuta em sua organização como vários valores para cada eVar são tratados (alocação) e quando as eVars param de persistir nos dados (expiração).

* Por padrão, uma eVar usa a última alocação. Novos valores substituem os valores persistentes.
* Por padrão, uma eVar usa uma expiração de visita. Quando uma visita termina, os valores param de copiar de linha para linha na coluna `post_evar`.

Você pode alterar a alocação e a expiração da eVar em [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nas configurações do conjunto de relatórios.

## Valor de eVars em relação a props

A Adobe recomenda o uso de eVars na maioria dos casos, com suporte do seguinte:

* As eVars têm um limite de 255 bytes nos relatórios. As Props têm um limite de 100 bytes.
* As props, por padrão, não persistem além da ocorrência às quais que estão definidas. As eVars têm expiração personalizada, permitindo determinar quando uma eVar não mais recebe incremento por um evento subsequente. No entanto, se você usar a opção [reportar processamento de tempo](/help/components/vrs/vrs-report-time-processing.md), props e eVars poderão usar um modelo de atribuição personalizado.
* A Adobe aceita até 250 eVars e apenas 75 props.

Consulte [prop](prop.md) para obter mais comparações entre props e eVars.
