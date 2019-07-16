---
description: O Construtor de segmentos permite que você compare e restrinja valores com os operadores selecionados.
seo-description: O Construtor de segmentos permite que você compare e restrinja valores com os operadores selecionados.
seo-title: Operadores de comparação para segmentos
solution: Analytics
title: Operadores de comparação para segmentos
topic: Segmentos
uuid: 02 ad 814 c -2 c 7 c -4833-9 bb 2-4113 dcf 9475 d
translation-type: tm+mt
source-git-commit: c36bc5a74e89fda3e23113851f850fd6c98b8c40

---


# Operadores de comparação para segmentos

O Construtor de segmentos permite que você compare e restrinja valores usando operadores selecionados.

Há três categorias de operadores: Padrão, Data Warehouse e Contagem distinta.

O único caractere genérico compatível é o asterisco: *. Caso seja necessário pesquisar por *, você pode isolá-lo com barras invertidas.

**Exemplo**: Suponha que você tenha um nome de página chamado &quot;Meu produto divertido&quot;. A regra do segmento &quot;O nome da página corresponde a Meu*produto&quot; corresponderá ao nome da página acima. No entanto, a regra &quot;O nome da página corresponde a Meu\\*produto&quot; será correspondente somente com o nome da página &quot;Meu*produto&quot;.

| Operador | A dimensão, o segmento ou o evento de métrica selecionado... |
|--- |--- |
| **Padrão** |  |
| igual a | Retorna itens que possuem o mesmo valor numérico ou de sequência. Observação: se estiver usando caracteres curingas, use operador &quot;corresponde&quot;. |
| não é igual | Retorna todos os itens que não contêm a correspondência exata do valor inserido.  Observação: se estiver usando caracteres curingas, use operador &quot;não correspondente&quot;. |
| equivale a qualquer | Retorna itens que correspondem exatamente a qualquer valor no campo de entrada (até 500 itens). Por exemplo, inserir &quot;Resultados de pesquisa, Página inicial&quot; com esse operador corresponderia a &quot;Resultados de pesquisa&quot; e &quot;Página inicial&quot; e contagem como 2 itens. O campo de entrada para esse operador é delimitado por vírgulas. |
| não equivale a qualquer | Identifica itens que correspondem exatamente a qualquer valor no campo de entrada (até 500 itens) e, em seguida, retorna apenas itens sem esses valores. Por exemplo, inserir &quot;Resultados de pesquisa, Página inicial&quot; com esse operador identificaria &quot;Resultados de pesquisa&quot; e &quot;Página inicial&quot; e, em seguida, exclua-os dos itens retornados. Este exemplo conta como 2 itens. O campo de entrada para esse operador é delimitado por vírgulas. |
| contém | Retorna itens que se comparam às subsequências de caracteres dos valores inseridos. Por exemplo, se a regra para &quot;Página&quot; contém &quot;Pesquisa&quot;, então isso corresponderá a qualquer página com a subsequência de caracteres &quot;Pesquisar&quot; nela, incluindo &quot;Resultados de pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Pesquisando&quot;. |
| não contém | Retorna o inverso da regra &quot;contém&quot;. Especificamente, todos os itens que correspondem ao valor inserido serão excluídos dos valores inseridos. Por exemplo, se a regra para &quot;Página&quot; não contém &quot;Pesquisa&quot;, então não corresponde a qualquer página com a subsequência de caracteres &quot;Pesquisar&quot; nela, incluindo &quot;Resultados de pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Pesquisando&quot;. Esses valores serão excluídos dos resultados. |
| contém tudo | Retorna itens comparados às subsequências de caracteres, incluindo diversos valores unidos. Por exemplo, inserir &quot;Resultados de pesquisa&quot; com esse operador corresponderia &quot;Resultados de pesquisa&quot; e &quot;Resultados da pesquisa&quot;, mas não &quot;Pesquisa&quot; ou &quot;Resultados&quot; independentemente. Corresponderia Pesquisa E Resultados encontrados juntos. O campo de entrada para esse operador é delimitado por espaços (100 palavras). |
| não contém todos os | Identifica itens comparados com subsequências (incluindo diversos valores agrupados) e só retorna os itens sem esses valores. Por exemplo, inserir &quot;Resultados de pesquisa&quot; com esse operador identificaria &quot;Resultados de pesquisa&quot; e &quot;Resultados da pesquisa&quot; (mas não &quot;Pesquisa&quot; ou &quot;Resultados&quot; separadamente), e esses itens seriam excluídos. O campo de entrada para esse operador é delimitado por espaços (100 palavras). |
| contém qualquer um dos | Retorna itens comparados às subsequências de caracteres, incluindo diversos valores unidos ou identificados de forma independente. Por exemplo, inserir &quot;Resultados de pesquisa&quot; com esse operador corresponderia a &quot;Resultados da pesquisa&quot;, &quot;Resultados de pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Resultados&quot;. Corresponderia a &quot;Pesquisa&quot; OU &quot;Resultados&quot; encontrados junto ou de forma independente. O campo de entrada para esse operador é delimitado por espaços (100 palavras). |
| não contém nenhum de | Identifica itens baseados em subsequências e retorna os valores que não contêm essas subsequências. Pode ter diversos valores reunidos ou valores identificados de maneira independente. Por exemplo, o termo &quot;Resultados de pesquisa&quot; seria correspondente a &quot;Resultados de pesquisa&quot;, &quot;Resultados da pesquisa&quot;, &quot;Pesquisa&quot; e &quot;Resultados&quot;, sendo que &quot;Pesquisa&quot; ou &quot;Resultados&quot; podem ser encontrados juntos ou separados. Em seguida, os itens que possuíssem essas subsequências seriam excluídos. O campo de entrada para esse operador é delimitado por espaços (100 palavras). |
| começa com | Retorna itens que iniciam com o caractere ou sequência de caracteres do valor inserido. |
| não inicia com | Retorna todos os itens que não iniciam com os caracteres ou as sequências de caracteres dos valores inseridos. É o inverso do operador &quot;inicia com&quot;. |
| termina com | Retorna itens que terminam com o caractere ou as sequências de caracteres do valor inserido. |
| não termina com | Retorna todos os itens que não terminam com os caracteres ou a sequência de caracteres do valor inserido. É o inverso do operador &quot;termina com&quot;. |
| corresponde | Retorna itens correspondentes com base no valor numérico ou de sequência. Observação: use este operador quando utilizar recursos de curinga. |
| não corresponde a | Retorna todos os itens que não contêm a correspondência exata do valor inserido. Observação: use este operador quando utilizar recursos de curinga. |
| existe | Retorna o número de itens que existem. Por exemplo, se você avaliar a dimensão Páginas não encontradas usando o operador &quot;existe&quot;, o número de páginas de erro que existe é retornado. |
| não existe | Retorna todos os itens que não existem. Por exemplo, se você avaliar a dimensão Páginas não encontradas usando o operador &quot;não existe&quot;, o número de páginas nas quais esse erro não existia é retornado. |
| **Data Warehouse** |  |
| é menor que | Retorna itens cuja contagem numérica é inferior ao valor inserido. |
| é menor que ou igual a | Retorna itens cuja contagem numérica é inferior ou igual ao valor inserido. |
| é maior que | Retorna itens cuja contagem numérica é superior ao valor inserido. |
| é maior que ou igual a | Retorna itens cuja contagem numérica é superior ou igual ao valor inserido. |
| **Contagem distinta** | É possível segmentar uma contagem distinta de itens em uma dimensão. Exemplos: “Visitantes que visualizaram mais de 5 produtos distintos”, ou “Visitas em que mais de 5 páginas distintas foram.”  |
| igual a | Retorna itens de dimensão cuja contagem exclusiva é igual ao valor inserido. |
| não é igual | Retorna itens de dimensão cuja contagem exclusiva não é igual ao valor inserido. |
| é maior que | Retorna itens de dimensão cuja contagem exclusiva é superior ao valor inserido. |
| é menor que | Retorna itens de dimensão cuja contagem exclusiva é inferior ao valor inserido. |
| é maior que ou igual a | Retorna itens de dimensão cuja contagem exclusiva é maior ou igual ao valor inserido. |
| é menor que ou igual a | Retorna itens de dimensão cuja contagem exclusiva é menor ou igual ao valor inserido. |

