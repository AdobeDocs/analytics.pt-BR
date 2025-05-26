---
description: Como os totais do Workspace são calculados.
title: Totais do Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
source-git-commit: d9f95b12a43305cecff1190e6544334f3b48835d
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 81%

---

# Totais do Workspace {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Total geral"
>abstract="O total geral não é compatível com tabelas ou detalhamentos com linhas estáticas."

Nas Tabelas de forma livre, aparece uma linha total em cada nível de detalhamento, que pode mostrar dois totais:

![Tabela de forma livre destacando o total geral e o total da tabela.](assets/total-row.png)

* **[!UICONTROL Total da tabela]** ➊ - Normalmente esse total é uma parte do [!UICONTROL Total geral] ou igual a ele. O total reflete todos os filtros de tabela aplicados na tabela de forma livre, incluindo a opção [!UICONTROL Incluir nenhum].
* **[!UICONTROL Total geral]** (**[!UICONTROL de]** *número*) ➋ - Esse total representa todos os eventos que foram coletados. Quando um filtro é aplicado no nível do painel ou na tabela de forma livre, esse total é ajustado para refletir todos os eventos que correspondem aos critérios de filtro.




## Exibir totais

Em ![Configurações](/help/assets/icons/Setting.svg) **[!UICONTROL Configurações de coluna]**, há opções para **[!UICONTROL Mostrar totais]** e **[!UICONTROL Mostrar total geral]**. Se essas configurações não estiverem marcadas, os totais serão removidos da tabela, o que pode ser desejado em casos em que os totais não fazem sentido.


[Os totais de linha estática](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) se comportam de forma diferente e são controlados usando ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Configurações de linha]**.

| Opção | Descrição |
|---|---|
| **[!UICONTROL Mostrar a soma das linhas atuais como total]** | Exibe uma soma do lado do cliente das linhas na tabela. Este total **não** elimina a duplicação de métricas como sessões ou pessoas. |
| **[!UICONTROL Exibir total geral]** | Mostrar uma soma do lado do servidor. Esse total remove a duplicação de métricas como sessões ou pessoas. |

Consulte [Itens de dimensão dinâmicos vs. estáticos em tabelas de forma livre](column-row-settings/manual-vs-dynamic-rows.md).


## Perguntas frequentes

| Perguntas | Resposta |
|---|---|
| Em qual *total* as porcentagens da coluna cinza se baseiam? | Este *total* depende da seleção da configuração de **[!UICONTROL Porcentagens]** em **[!UICONTROL Configurações de linha]**:<ul><li>Calcular porcentagens por coluna. Esta configuração é a padrão. As porcentagens são baseadas no total da tabela.</li><li>Calcular porcentagens por linha: as porcentagens são baseadas no total geral.</li></ul> |
| Como a configuração **[!UICONTROL Incluir não especificado (Nenhum)]** afeta os totais? | Se a configuração Incluir não especificado (Nenhum) estiver desmarcada, a linha Nenhum/Não especificado será removida da tabela, do Total da tabela, e continuará para qualquer métrica calculada que use [ tipos de métricas &quot;Total&quot;](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md). |
| Quando os filtros de tabela personalizados são aplicados a uma tabela de forma livre, todas as minhas métricas calculadas e minha formatação condicional são consideradas para o filtro? | No momento não. **[!UICONTROL Incluir Não Especificado (Nenhum)]** é a conta para, mas os filtros de tabela personalizados não afetam os seguintes:<ul><li>O intervalo máximo/mínimo da coluna que a formatação condicional usa analisa todos os dados.</li><li>Métricas calculadas que alavancam os tipos de métricas **[!UICONTROL Total geral]**.</li><li>As métricas calculadas com funções que calculam várias linhas em uma tabela de forma livre: Soma da coluna, Máx. da coluna, Mín. da coluna, Contagem, Média, Mediana, Percentil, Quartil, Contagem de linhas, Desvio padrão, Variância, Cumulativo, Média cumulativa, Variantes de regressão, Pontuação T, Teste T, Pontuação Z e Teste Z.</li></ul> |
| Em Métricas calculadas, o que o tipo de métrica **[!UICONTROL Total geral]** reflete? | **[!UICONTROL Total geral]** continua a se referir ao **[!UICONTROL Total geral]** e não reflete filtros aplicados a uma tabela ou ao **[!UICONTROL Total da tabela]**. |
| Qual total é mostrado quando os dados são copiados e colados de uma tabela de forma livre ou baixados via CSV? | A linha total reflete apenas o **[!UICONTROL Total da tabela]** e respeita a configuração da coluna **[!UICONTROL Mostrar totais]**. |
