---
description: O Construtor de segmentos permite que você compare e restrinja valores com os operadores selecionados.
title: Operadores de comparação para segmentos
feature: Segmentation
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
source-git-commit: b53ef727adc563e05403c50d80bbd0c48bb8a054
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 51%

---

# Operadores de comparação para segmentos

O Construtor de segmentos permite que você compare e restrinja valores com os operadores selecionados. Existem três categorias de operadores: Padrão, Data Warehouse e Contagem distinta.

Dependendo do operador selecionado:

* Você pode inserir um valor
* Você pode inserir parte de um valor e selecionar em um menu suspenso (se disponível).
* Selecione imediatamente um valor no menu suspenso (se disponível).

Ao digitar um valor para um operador que valida os valores disponíveis, como **[!UICONTROL é igual a]**, e o valor não corresponde aos valores disponíveis para o componente, você verá um ícone ![AlertRed](/help/assets/icons/AlertRed.svg). Você pode selecionar um valor no menu suspenso ou pressionar **[!UICONTROL _Enter_]** para inserir o valor.

![Segmento igual a](assets/segment-operator-equals.png)

## Curingas

O único caractere curinga aceito para operadores que oferecem suporte a curingas é o asterisco: `*`. Se você precisar pesquisar pelo caractere &#42; específico, poderá utilizar uma barra invertida como escape, como `\*`.

Por exemplo, você tem um nome de página chamado *Meu produto divertido*.

* O **[!UICONTROL nome de página]** **[!UICONTROL correspondências]** `* product` da regra de segmento corresponderá ao nome de página acima.
* No entanto, a regra **[!UICONTROL Nome da página]** **[!UICONTROL corresponde]** `My \* product` corresponde somente ao nome da página *Meu * Produto*.

## Operadores padrão

| Operador | A dimensão, o segmento ou o evento de métrica selecionado... |
|--- |--- |
| **[!UICONTROL igual]** | Retorna itens que possuem o mesmo valor numérico ou de sequência. Observação: se estiver usando caracteres curingas, use o operador **[!UICONTROL corresponde]**. |
| **[!UICONTROL não é igual]** | Retorna todos os itens que não contêm a correspondência exata do valor inserido.  Observação: se estiver usando caracteres curingas, use o operador **[!UICONTROL não corresponde]**. |
| **[!UICONTROL é igual a qualquer um de]** | Retorna itens que correspondem exatamente a qualquer valor no campo de entrada (até 500 itens). Por exemplo, inserir `Search Results, Homepage` para a dimensão **[!UICONTROL Nome da Página]** com este operador corresponderia a *Resultados da Pesquisa* e *Página Inicial* e contaria como 2 itens. O campo de entrada desse operador é delimitado por vírgulas. |
| **[!UICONTROL não é igual a qualquer um de]** | Identifica itens que correspondem exatamente a qualquer valor no campo de entrada (até 500 itens) e retorna apenas itens sem esses valores. Por exemplo, inserir `Search Results, Homepage` com este operador para a dimensão **[!UICONTROL Nome da Página]** identificaria os *Resultados da Pesquisa* e a *Página Inicial* e, em seguida, **os excluiria** dos itens retornados. Esse exemplo contaria como 2 itens. O campo de entrada desse operador é delimitado por vírgulas. |
| **[!UICONTROL contém]** | Retorna itens que se comparam às subsequências de caracteres dos valores inseridos. Por exemplo, se a regra for **[!UICONTROL Nome da Página]** **[!UICONTROL contém]** `Search`, ela corresponderá a qualquer página que tenha a subsequência de caracteres `Search` nela, incluindo *Resultados da Pesquisa*, *Pesquisa* e *Pesquisa*. A cláusula &quot;contains&quot; não diferencia maiúsculas de minúsculas no Adobe Analytics, mas faz isso no Customer Journey Analytics. |
| **[!UICONTROL não contém]** | Retorna o inverso da regra **[!UICONTROL contém]**. Especificamente, todos os itens que correspondem ao valor inserido serão excluídos dos valores inseridos. Por exemplo, se a regra for **[!UICONTROL Nome da Página]** **[!UICONTROL não contiver]** `Search`, ela não corresponderá a nenhuma página que tenha a subsequência de caracteres `Search` nela, incluindo *Resultados da Pesquisa*, *Pesquisa* e *Pesquisa*. Esses valores serão excluídos dos resultados. |
| **[!UICONTROL contém tudo]** | Retorna itens comparados às subsequências de caracteres, incluindo diversos valores unidos. Por exemplo, inserir `Search Results` com este operador para a dimensão **[!UICONTROL Nome da Página]** corresponderia a *Resultados da Pesquisa* e *Resultados da Pesquisa*, mas não a *Pesquisa* ou *Resultados* individualmente. A regra corresponderia a *Pesquisa* E *Resultados* encontrados juntos. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| **[!UICONTROL não contém todos os]** | Identifica itens comparados com subsequências de caracteres, incluindo vários valores agrupados, e retorna somente itens sem esses valores. Por exemplo, inserir `Search Results` com este operador para a dimensão **[!UICONTROL Nome da Página]** identificará *Resultados da Pesquisa* e *Resultados da Pesquisa* (mas não *Pesquisa* ou *Resultados* individualmente) e excluirá esses itens. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| **[!UICONTROL contém qualquer um dos]** | Retorna itens comparados às subsequências de caracteres, incluindo diversos valores unidos ou identificados de forma independente. Por exemplo, inserir `Search Results` com este operador corresponderia a *Resultados da Pesquisa*, *Resultados da Pesquisa*, *Pesquisa* e *Resultados*. Corresponderia a *Pesquisa* OU a *Resultados* encontrados juntos ou de forma independente. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| **[!UICONTROL não contém nenhum de]** | Identifica itens baseados em subsequências e retorna os valores que não contêm essas subsequências. Pode ter diversos valores reunidos ou valores identificados de maneira independente. Por exemplo, inserir `Search Results` para a dimensão **[!UICONTROL Nome da Página]** corresponderia a *Resultado da Pesquisa* s, *Resultados da Pesquisa* h*, *Pesquisa* e *Resultados* em que a *Pesquisa* ou o *Resultado* são encontrados juntos ou independentemente. Em seguida, os itens que possuíssem essas subsequências seriam excluídos. O campo de entrada desse operador é delimitado por espaços (100 palavras). |
| **[!UICONTROL iniciar com]** | Retorna itens que iniciam com o valor da cadeia de caracteres inserido. |
| **[!UICONTROL não inicia com]** | Retorna todos os itens que não iniciam com o valor da cadeia de caracteres inserido. Este é o inverso do operador **[!UICONTROL inicia com]**. |
| **[!UICONTROL termina com]** | Retorna itens que terminam com o valor da cadeia de caracteres inserido. |
| **[!UICONTROL não termina com]** | Retorna todos os itens que não terminam com o valor da cadeia de caracteres inserido. Este é o inverso do operador **[!UICONTROL termina com]**. |
| **[!UICONTROL corresponde]** | Retorna itens correspondentes com base no valor numérico ou de sequência. A cláusula **[!UICONTROL matches]** diferencia maiúsculas de minúsculas no Adobe Analytics e no Customer Journey Analytics. **Observação**: use este operador quando estiver usando recursos de curinga [3}. ](#wildcards) Exemplos de recurso de curinga:<ul><li>`a*e` corresponde a `ae`, `abcde`, `adobe` e `a whole sentence`</li><li>`adob*` corresponde a `adobe`, `adobe analytics` e `adobo recipe`</li><li>`*dobe` corresponde a `dobe`, `adobe` e `cute little dobe`</li></ul> |
| **[!UICONTROL não corresponde a]** | Retorna todos os itens que não contêm a correspondência exata do valor inserido. Observação: use este operador quando utilizar recursos de curinga [1}.](#wildcards) |
| **[!UICONTROL existe]** | Retorna o número de itens que existem. Por exemplo, se você avaliar a dimensão **[!UICONTROL Páginas não encontradas]** usando o operador **[!UICONTROL existe]**, o número de páginas de erro que existe é retornado. |
| **[!UICONTROL não existe]** | Retorna todos os itens que não existem. Por exemplo, se você avaliar a dimensão **[!UICONTROL Páginas não encontradas]** usando o operador **[!UICONTROL não existe]**, o número de páginas nas quais esse erro não existia é retornado. |

## Operadores de Data Warehouse

| Operador | A dimensão, o segmento ou o evento de métrica selecionado... |
| --- | --- |
| **[!UICONTROL é menor que]** | Retorna itens cuja contagem numérica é inferior ao valor inserido. |
| **[!UICONTROL é menor que ou igual a]** | Retorna itens cuja contagem numérica é inferior ou igual ao valor inserido. |
| **[!UICONTROL é maior que]** | Retorna itens cuja contagem numérica é superior ao valor inserido. |
| **[!UICONTROL é maior que ou igual a]** | Retorna itens cuja contagem numérica é superior ou igual ao valor inserido. |

## Operadores de contagem distinta

É possível segmentar em uma contagem distinta de itens em uma dimensão. Exemplos: “Visitantes que visualizaram mais de 5 produtos distintos”, ou “Visitas em que mais de 5 páginas distintas foram.”

| Operador | A dimensão, o segmento ou o evento de métrica selecionado... |
| --- | --- |
| **[!UICONTROL igual]** | Retorna itens de dimensão cuja contagem específica é igual ao valor inserido. |
| **[!UICONTROL não é igual]** | Retorna itens de dimensão cuja contagem específica não é igual ao valor inserido. |
| **[!UICONTROL é maior que]** | Retorna itens de dimensão cuja contagem específica é superior ao valor inserido. |
| **[!UICONTROL é menor que]** | Retorna itens de dimensão cuja contagem específica é inferior ao valor inserido. |
| **[!UICONTROL é maior que ou igual a]** | Retorna itens de dimensão cuja contagem específica é superior ou igual ao valor inserido. |
| **[!UICONTROL é menor que ou igual a]** | Retorna itens de dimensão cuja contagem específica é inferior ou igual ao valor inserido. |


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Distinct dimension counts](https://video.tv.adobe.com/v/27257?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]
