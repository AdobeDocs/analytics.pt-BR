---
description: Como os totais da Workspace são calculados.
seo-description: Saiba como os totais da Workspace são calculados.
seo-title: Como os totais da Workspace são calculados.
title: Totais da área de trabalho
translation-type: tm+mt
source-git-commit: b2e76715a2bab0931b1ddf8c612c29eea530ce6c

---


# Totais da área de trabalho

Nas tabelas de forma livre, uma linha total aparece em cada nível de detalhamento e pode mostrar dois totais:

* **[!UICONTROL Total]** geral (número "fora de" cinza) - esse total representa todas as ocorrências que foram coletadas, às vezes chamadas de "total do conjunto de relatórios". Quando um segmento é aplicado no nível do painel ou na tabela de forma livre, esse total se ajusta para refletir todas as ocorrências que correspondem aos critérios do segmento.
* **[!UICONTROL Total]** da tabela (número preto) - esse total é normalmente igual ou um subconjunto do Total geral. Ele reflete todos os filtros de tabela aplicados na tabela de forma livre, incluindo a opção [!UICONTROL Incluir nenhum] .

![](assets/total-row.png)

## Exibir configuração total

Em Configurações **[!UICONTROL de]** coluna, há opções para **[!UICONTROL Mostrar totais]** e **[!UICONTROL Mostrar total]** geral. Se essas configurações estiverem desmarcadas, os totais serão removidos da tabela. Isso pode ser desejado nos casos em que os totais não fazem sentido, por exemplo, em determinados cenários [de Métrica](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)calculada.

![](assets/column-settings-total.png)

## Configurações de Total de linhas estáticas

[Os totais de linhas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) estáticas comportam-se de forma diferente e são controlados em Configurações **[!UICONTROL de]** linha.

* **[!UICONTROL Mostrar a soma das linhas atuais como o total]** - mostra uma soma do lado do cliente das linhas na tabela, o que significa que o total **não** removerá a duplicação de métricas como visitas ou visitantes.
* **[!UICONTROL Mostrar Total]** Geral - mostra uma soma do lado do servidor, o que significa que o total removerá a duplicação de métricas como visitas ou visitantes.

![](assets/static-rows.png)

## Perguntas frequentes

| Perguntas | Resposta |
|---|---|
| Em qual "total" as porcentagens de coluna cinza se baseiam? | Isso depende da seleção da configuração **[!UICONTROL Porcentagens]** em Configurações **** de linha:<ul><li>Calcular porcentagens por coluna - Essa é a configuração padrão. As porcentagens serão baseadas no Total da tabela.</li><li>Calcular porcentagens por linha - As porcentagens serão baseadas no Total Geral.</li></ul> |
| Como a configuração **[!UICONTROL Incluir não especificado (Nenhum)]** afeta os totais? | Se a configuração **[!UICONTROL Incluir não especificado (Nenhum)]** estiver desmarcada, a linha Nenhum/Não especificado será removida da tabela, o Total da tabela e continuará para qualquer métrica calculada que use tipos de métricas ['Total'](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| Quando os filtros de tabela personalizados são aplicados a uma tabela de forma livre, todas as minhas métricas calculadas e formatação condicional são consideradas para o filtro? | No momento não. **[!UICONTROL Incluir não especificado (Nenhum)]** será contabilizado, mas os filtros de tabela personalizados não afetarão o seguinte:<ul><li>The column max/min range that conditional formatting uses will look across all data.</li><li>Calculated metrics that leverage Grand Total metric types.****</li><li>Calculated metrics with functions that calculate across rows in a freeform table - i.e. Column Sum, Column max, Column min, Count, Mean, Median, Percentile, Quartile, Row Count, Standard Deviation, Variance, Cumulative, Cumulative Average, Regression variants, T-Score, T-Test, Z-Score, Z-Test.</li></ul> |
| In Calculated Metrics, what does the **[!UICONTROL Grand Total]** metric type reflect? | **[!UICONTROL Grand Total continues to refer to the Grand Total, and does not reflect filters applied to a table or the Table Total.]********** |
| What total is shown when data is either copied and pasted from a freeform table or downloaded via CSV? | The total row will reflect the Table Total only and respects the column Show Totals setting.******** |

