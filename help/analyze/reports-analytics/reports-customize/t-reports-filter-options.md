---
description: Os filtros permitem restringir o relatório para incluir ou excluir itens de linha correspondentes a um filtro.
title: Filtro de dados de relatório
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Filtrar dados de relatório {#concept_09DC5B986A644738B12204DAC76A90E1}

Os filtros permitem restringir o relatório para incluir ou excluir itens de linha correspondentes a um filtro.

## Filtro simples {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

O filtro simples aparece na maioria dos relatórios para permitir que você encontre rapidamente itens de linha específicos. Filtros simples não usam qualquer caractere especial, portanto, `-, ", ', +` e outros caracteres especiais correspondem ao valor literal no relatório. Você pode encontrar itens de linha que contêm vários termos usando um espaço.

Por exemplo:

```
help search
```

Corresponde às seguintes páginas:

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## Filtros avançados {#section_E016626C084640E8A066B2FDA5B932BF}

filtros avançados permitem controlar o escopo da pesquisa usando uma coleção de filtros. Você pode selecionar para corresponder a todos os filtros ou a qualquer filtros.

![](assets/advanced_filter.png)

**Contém**

Corresponde se o termo é encontrado em qualquer lugar no item de linha. Isso opera da mesma forma que o filtro simples.

>[!NOTE] Os espaços não podem ser usados em filtros, pois os espaços são delimitadores em pesquisas

**Não contém**

Corresponde se o termo não for encontrado em qualquer lugar no item de linha. Você pode filtrar &quot;não especificado&quot;, &quot;nenhum&quot;, &quot;palavra-chave não disponível&quot; e outros [valores especiais](https://marketing.adobe.com/resources/help/pt_BR/reference/none-unspecified-unknown-other.html) de relatórios que usam &quot;não contém&quot;.

Não contém: `none`

Para obter um filtro mais exato, você pode usar um filtro Avançado (Caracteres especiais):

* Avançado (Caractere especial): `-^none$`
* Avançado (Caractere especial): `-"keyword unavailable"`

Por exemplo, o seguinte item de linha é filtrado pelo critério &quot;Não contém&quot;, mas não é filtrado pelo critério &quot;Avançado (Caractere Especial)&quot;:

```
help:Rename the None classification key
```

**Contém um de**

Corresponde se qualquer termo, separado por espaços, é encontrado no item de linha. O filtro a seguir mostra todas as páginas que contêm &quot;homens&quot; ou &quot;venda&quot;:

Contém um de: `mens sale`

Corresponde às seguintes páginas:

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**Igual**

Corresponde se o item de linha inteiro, incluindo espaços e outros caracteres, corresponde à frase especificada.

Igual: `mens:desk & travel`

`Mens:Desk & Travel`

**Começa com**

Corresponde se o item de linha, incluindo espaços e outros caracteres, start com a frase especificada.

Começa com: `mens`

Corresponde às seguintes páginas:

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Termina com**

Corresponde se o item de linha, incluindo espaços e outros caracteres, termina com a frase especificada.

Termina com: `jean`

Corresponde às seguintes páginas:

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Avançado (Caractere especial) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Avançado permite que você execute curingas e outras pesquisas complexas.

| Avançado (Caractere especial) | Descrição |
|--- |--- |
| `" "` | Corresponder à frase exata. |
| `*` | Curinga, correspondência voraz. <br>Por exemplo, `r*p` corresponde a &quot;Inscrição para registro&quot;. |
| `^` | Começa com. <br>Não inclua um espaço entre o caractere especial e a frase de pesquisa. |
| `$` | Termina com. <br>Não inclua um espaço entre o caractere especial e a frase de pesquisa. |
| `-` | Não. <br>Não inclua um espaço entre o caractere especial e a frase de pesquisa. |
| `|` | Ou <br>Observação: você deve incluir um espaço em cada lado do caracteres de barra vertical, `" | "`. |

## Criar filtros específicos de relatório {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Etapas que descrevem como criar filtros para relatórios.

<!-- 

t_reports_filter_specific.xml

 -->

Alguns relatórios contêm um filtro específico para esse relatório. Por exemplo, uma opção [!UICONTROL Purchase Conversion Funnel Report] permite filtrar por páginas da Web. Um [!UICONTROL Geosegmentation Report] permite filtrar por região geográfica. Relatórios adicionais têm outros filtros específicos para esses relatórios.

Ao acessar esses filtros, você pode ver as métricas de relatório dos itens especificados na lista.

**Para criar filtros específicos de relatórios**

1. Gere um relatório, como um [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. In the report header, click the **[!UICONTROL Filter]** link.
1. Na [!UICONTROL Filter Selector] página, clique em **[!UICONTROL Apply a Filter]**, em seguida, selecione um tipo de filtro.
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. Clique em **[!UICONTROL OK]**.

## Adicionar um filtro de correlação {#task_065042E384DA4BF3864C58AF2B88D6E2}

Etapas que descrevem como adicionar um filtro de correlação.

<!-- 

t_reports_correlation_filter.xml

 -->

Determinados relatórios permitem adicionar filtros de correlação personalizados. Por exemplo, se você estiver visualizando o [!UICONTROL Pages Report] para um conjunto de relatórios que tenha Seções do site correlacionadas a uma página para Mulheres, poderá criar uma regra de filtro que gera um relatório que mostra as páginas mais populares quando Seções do site = Mulheres.

Você pode filtrar os dados mostrados em um relatório de correlação usando qualquer correlação disponível. O exemplo mostra como você adiciona um filtro de correlação de mecanismo de pesquisa.

**Para adicionar um filtro de correlação**

1. Execute um relatório com suporte a correlações. (Consulte [Executar um relatório de detalhamento](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. Em [!UICONTROL Filter Rule Creator], selecione uma categoria para correlacionar com um item.
1. Clique em **[!UICONTROL OK.]**
