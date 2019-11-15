---
description: Como os totais da Workspace são calculados.
title: Totais da área de trabalho
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
| Quando os filtros de tabela personalizados são aplicados a uma tabela de forma livre, todas as minhas métricas calculadas e formatação condicional são consideradas para o filtro? | No momento não. **[!UICONTROL Incluir não especificado (Nenhum)]** será contabilizado, mas os filtros de tabela personalizados não afetarão o seguinte:<ul><li>O intervalo máximo/mínimo da coluna que a formatação condicional usa será exibido em todos os dados.</li><li>Métricas calculadas que aproveitam os tipos de métricas **[!UICONTROL Total]** Geral.</li><li>Métricas calculadas com funções que calculam entre linhas em uma tabela de forma livre - ou seja, Soma da coluna, Máximo da coluna, Mín. da coluna, Contagem, Média, Média, Percentual, Quartil, Contagem de linhas, Desvio padrão, Variação, Cumulativo, Média Cumulativa, Variantes de regressão, Pontuação T, Teste Z, Teste Z.</li></ul> |
| Em Métricas calculadas, o que o tipo de métrica **[!UICONTROL Total]** geral reflete? | **[!UICONTROL Total]** geral continua se referindo ao Total **** geral e não reflete os filtros aplicados a uma tabela ou ao Total **[!UICONTROL da]** tabela. |
| Qual total é mostrado quando os dados são copiados e colados de uma tabela de forma livre ou baixados via CSV? | A linha total refletirá somente o Total **[!UICONTROL da]** tabela e respeita a configuração da coluna **[!UICONTROL Mostrar totais]** . |

