---
description: Como os totais do Workspace são calculados.
title: Totais do Workspace
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Totais do Workspace

Nas Tabelas de forma livre, aparece uma linha total em cada nível de detalhamento, que pode mostrar dois totais:

* **[!UICONTROL Grand Total]** (número &quot;fora de&quot; cinza) - esse total representa todas as ocorrências que foram coletadas, às vezes chamadas de &quot;total do conjunto de relatórios&quot;. Quando um segmento é aplicado no nível do painel ou na tabela de forma livre, esse total é ajustado para refletir todas as ocorrências que correspondem aos critérios do segmento.
* **[!UICONTROL Table Total]** (número preto) - esse total é tipicamente igual ou um subconjunto do [!UICONTROL Grand Total]. It reflects any table filters applied within the freeform table, including the [!UICONTROL Include None] option.

![](assets/total-row.png)

## Exibir configuração total

Em **[!UICONTROL Column Settings]**, há opções para **[!UICONTROL Show Totals]** e **[!UICONTROL Show Grand Total]**. Se essas configurações estiverem desmarcadas, os totais serão removidos da tabela. Isso pode ser desejado nos casos em que os totais não fazem sentido, por exemplo, em determinados cenários [Métrica calculada](https://docs.adobe.com/content/help/pt-BR/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html).

![](assets/column-settings-total.png)

## Configurações do Total de linhas estáticas

[Os totais das linhas](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) estáticas comportam-se de forma diferente e são controlados em **[!UICONTROL Row Settings]**.

* **[!UICONTROL Show sum of current rows as the total]** - isso mostra uma soma das linhas do lado do cliente na tabela, o que significa que o total **não** removerá métricas de duplicado, como visitas ou visitantes.
* **[!UICONTROL Show Grand Total]** - isso mostra uma soma do lado do servidor, o que significa que o total removerá métricas de duplicado, como visitas ou visitantes.

![](assets/static-rows.png)

## Perguntas frequentes

| Perguntas | Resposta |
|---|---|
| Em qual “total” as porcentagens da coluna cinza se baseiam? | Isso depende da **[!UICONTROL Percentages]** configuração selecionada em **[!UICONTROL Row Settings]**:<ul><li>Calcular porcentagens por coluna: essa é a configuração padrão. As porcentagens serão baseadas no Total da tabela.</li><li>Calcular porcentagens por linha: as porcentagens serão baseadas no Total Geral.</li></ul> |
| Como a **[!UICONTROL Include Unspecified (None)]** configuração afeta os totais? | If the **[!UICONTROL Include Unspecified (None)]** setting is unchecked, the None/Unspecified row will be removed from the table, the Table Total, and will carry through to any calculated metrics that use [&#39;Total&#39; metric types](https://docs.adobe.com/content/help/pt-BR/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| Quando os filtros de tabela personalizados são aplicados a uma tabela de forma livre, todas as minhas métricas calculadas e minha formatação condicional são consideradas para o filtro? | No momento não. **[!UICONTROL Include Unspecified (None)]** serão contabilizados, mas os filtros de tabela personalizados não afetarão o seguinte:<ul><li>O intervalo máximo/mínimo da coluna da formatação condicional pesquisa em todos os dados.</li><li>Métricas calculadas que aproveitam tipos de **[!UICONTROL Grand Total]** métricas.</li><li>As métricas calculadas com funções que calculam várias linhas em uma tabela de forma livre (ou seja, Soma da coluna, Máximo da coluna, Mín. da coluna, Contagem, Média, Média, Percentual, Quartil, Contagem de linhas, Desvio padrão, Variação, Cumulativo, Média Cumulativa, Variantes de regressão, Pontuação T, Teste T, Pontuação Z, Teste Z).</li></ul> |
| In Calculated Metrics, what does the **[!UICONTROL Grand Total]** metric type reflect? | **[!UICONTROL Grand Total]** continua referindo-se ao **[!UICONTROL Grand Total]** e não reflete os filtros aplicados a uma tabela ou ao **[!UICONTROL Table Total]**. |
| Qual total é mostrado quando os dados são copiados e colados de uma tabela de forma livre ou baixados via CSV? | A linha total refletirá a **[!UICONTROL Table Total]** única e respeitará a configuração da coluna **[!UICONTROL Show Totals]** . |

