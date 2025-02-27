---
description: O Construtor de segmentos permite que você compare e restrinja valores com os operadores selecionados.
title: Operadores de comparação para segmentos
feature: Segmentation
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 94%

---

# Operadores de comparação para segmentos

O Construtor de segmentos permite que você compare e restrinja valores com os operadores selecionados. Existem três categorias de operadores: Padrão, Data Warehouse e Contagem distinta.

O único caractere curinga aceito é o asterisco: &#42;. Se você precisar procurar por &#42;, poderá fazer um escape com uma barra invertida.

**Exemplo**: imagine que você possui uma página com o nome de &quot;Meu produto divertido&quot;. A regra de segmento &quot;Nome da página corresponde a Meu&#42;produto&quot; corresponderá ao nome de página acima. No entanto, a regra &quot;O nome da página corresponde a Meu\\&#42;produto&quot; corresponde somente ao nome da página &quot;Meu&#42;Produto&quot;.

## Operadores padrão

| Operador | A dimensão, o segmento ou o evento de métrica selecionado... |
|--- |--- |
| igual a | Retorna itens que possuem o mesmo valor numérico ou de sequência. Observação: se estiver usando caracteres curingas, use operador &quot;corresponde&quot;. |
| não é igual | Retorna todos os itens que não contêm a correspondência exata do valor inserido.  Observação: se estiver usando caracteres curingas, use operador &quot;não correspondente&quot;. |
| equivale a qualquer | Retorna itens que correspondem exatamente a qualquer valor no campo de entrada (até 500 itens). Por exemplo, inserir &quot;Resultados de pesquisa, Página inicial&quot; com esse operador corresponderia a &quot;Resultados de pesquisa&quot; e &quot;Página inicial&quot; e contaria como 2 itens. O campo de entrada desse operador é delimitado por vírgulas. |
| não equivale a qualquer | Identifica itens que correspondem exatamente a qualquer valor no campo de entrada (até 500 itens) e retorna apenas itens sem esses valores. Por exemplo, inserir &quot;Resultados de pesquisa, Página inicial&quot; com esse operador identificaria &quot;Resultados de pesquisa&quot; e &quot;Página inicial&quot; e os excluiria dos itens retornados. Esse exemplo contaria como 2 itens. O campo de entrada desse operador é delimitado por vírgulas. |
| contém | Retorna itens que se comparam às subsequências de caracteres dos valores inseridos. Por exemplo, se a regra para &quot;Página&quot; contém &quot;Pesquisa&quot;, então isso corresponderá a qualquer página com a subsequência de caracteres &quot;Pesquisar&quot; nela, incluindo &quot;Resultados de pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Pesquisando&quot;. A cláusula &quot;contains&quot; não diferencia maiúsculas de minúsculas no Adobe Analytics, mas faz isso no Customer Journey Analytics. |
| não contém | Retorna o inverso da regra &quot;contém&quot;. Especificamente, todos os itens que correspondem ao valor inserido serão excluídos dos valores inseridos. Por exemplo, se a regra para &quot;Página&quot; não contém &quot;Pesquisa&quot;, então não corresponde a qualquer página com a subsequência de caracteres &quot;Pesquisar&quot; nela, incluindo &quot;Resultados de pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Pesquisando&quot;. Esses valores serão excluídos dos resultados. |
| contém tudo | Retorna itens comparados às subsequências de caracteres, incluindo diversos valores unidos. Por exemplo, inserir &quot;Resultados de pesquisa&quot; com esse operador corresponderia &quot;Resultados de pesquisa&quot; e &quot;Resultados da pesquisa&quot;, mas não &quot;Pesquisa&quot; ou &quot;Resultados&quot; independentemente. Corresponderia Pesquisa E Resultados encontrados juntos. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| não contém todos os | Identifica itens comparados com subsequências (incluindo diversos valores agrupados) e só retorna os itens sem esses valores. Por exemplo, inserir &quot;Resultados de pesquisa&quot; com esse operador identificaria &quot;Resultados de pesquisa&quot; e &quot;Resultados da pesquisa&quot; (mas não &quot;Pesquisa&quot; ou &quot;Resultados&quot; separadamente), e esses itens seriam excluídos. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| contém qualquer um dos | Retorna itens comparados às subsequências de caracteres, incluindo diversos valores unidos ou identificados de forma independente. Por exemplo, inserir &quot;Resultados de pesquisa&quot; com esse operador corresponderia a &quot;Resultados da pesquisa&quot;, &quot;Resultados de pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Resultados&quot;. Corresponderia a &quot;Pesquisa&quot; OU &quot;Resultados&quot; encontrados junto ou de forma independente. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| não contém nenhum de | Identifica itens baseados em subsequências e retorna os valores que não contêm essas subsequências. Pode ter diversos valores reunidos ou valores identificados de maneira independente. Por exemplo, o termo &quot;Resultados de pesquisa&quot; seria correspondente a &quot;Resultados de pesquisa&quot;, &quot;Resultados da pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Resultados&quot;, sendo que &quot;Pesquisa&quot; ou &quot;Resultados&quot; podem ser encontrados juntos ou separados. Em seguida, os itens que possuíssem essas subsequências seriam excluídos. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| começa com | Retorna itens que iniciam com o caractere ou sequência de caracteres do valor inserido. |
| não inicia com | Retorna todos os itens que não iniciam com os caracteres ou as sequências de caracteres dos valores inseridos. É o inverso do operador &quot;inicia com&quot;. |
| termina com | Retorna itens que terminam com o caractere ou as sequências de caracteres do valor inserido. |
| não termina com | Retorna todos os itens que não terminam com os caracteres ou a sequência de caracteres do valor inserido. É o inverso do operador &quot;termina com&quot;. |
| corresponde | Retorna itens correspondentes com base no valor numérico ou de sequência. A cláusula &quot;matches&quot; diferencia maiúsculas de minúsculas no Adobe Analytics e no Customer Journey Analytics. **Observação**: use este operador quando utilizar recursos de curinga. Exemplos de recurso de curinga:<ul><li>`a*e` corresponde a `ae`, `abcde`, `adobe` e `a whole sentence`</li><li>`adob*` corresponde a `adobe`, `adobe analytics` e `adobo recipe`</li><li>`*dobe` corresponde a `dobe`, `adobe` e `cute little dobe`</li></ul> |
| não corresponde | Retorna todos os itens que não contêm a correspondência exata do valor inserido. Observação: use este operador quando utilizar recursos de curinga. |
| existe | Retorna o número de itens que existem. Por exemplo, se você avaliar a dimensão Páginas não encontradas usando o operador &quot;existe&quot;, o número de páginas de erro que existe é retornado. |
| não existe | Retorna todos os itens que não existem. Por exemplo, se você avaliar a dimensão Páginas não encontradas usando o operador &quot;não existe&quot;, o número de páginas nas quais esse erro não existia é retornado. |

## Operadores de Data Warehouse

| Operador | A dimensão, o segmento ou o evento de métrica selecionado... |
| --- | --- |
| é menor que | Retorna itens cuja contagem numérica é inferior ao valor inserido. |
| é menor que ou igual a | Retorna itens cuja contagem numérica é inferior ou igual ao valor inserido. |
| é maior que | Retorna itens cuja contagem numérica é superior ao valor inserido. |
| é maior que ou igual a | Retorna itens cuja contagem numérica é superior ou igual ao valor inserido. |

## Operadores de contagem distinta

É possível segmentar em uma contagem distinta de itens em uma dimensão. Exemplos: “Visitantes que visualizaram mais de 5 produtos distintos”, ou “Visitas em que mais de 5 páginas distintas foram.”

| Operador | A dimensão, o segmento ou o evento de métrica selecionado... |
| --- | --- |
| igual a | Retorna itens de dimensão cuja contagem específica é igual ao valor inserido. |
| não é igual | Retorna itens de dimensão cuja contagem específica não é igual ao valor inserido. |
| é maior que | Retorna itens de dimensão cuja contagem específica é superior ao valor inserido. |
| é menor que | Retorna itens de dimensão cuja contagem específica é inferior ao valor inserido. |
| é maior que ou igual a | Retorna itens de dimensão cuja contagem específica é superior ou igual ao valor inserido. |
| é menor que ou igual a | Retorna itens de dimensão cuja contagem específica é inferior ou igual ao valor inserido. |


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Distinct dimension counts](https://video.tv.adobe.com/v/27257?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]
