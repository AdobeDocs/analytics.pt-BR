---
description: Use a visualização de linha para descrever conjuntos de dados com tendência (de acordo com o tempo)
title: Linha
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: 5a35d2acd428d16afff3d8e85cfb084d6a6476c4
workflow-type: ht
source-wordcount: '532'
ht-degree: 100%

---

# Linha {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="Linha"
>abstract="Crie uma visualização de linha que mostre como os valores são alterados durante um período. Uma visualização de linha só pode ser usada quando o tempo é usado como uma dimensão."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo é sobre a visualização de linha no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte [Linha](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/line) para ver a versão do_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** deste artigo._

>[!ENDSHADEBOX]

A visualização de ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL linha]** representa as métricas usando uma linha para mostrar como os valores se alteram em um período. Só é possível usar a visualização de linha se o tempo for utilizado como uma dimensão.

![Visualização de linha](assets/line-viz.png)


## Configurações 

Como parte das [configurações de visualização](freeform-analysis-visualizations.md#settings), há configurações específicas de visualização de linha disponíveis.

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Granularidade]** | Selecione uma granularidade no menu suspenso para alterar uma visualização de tendência de diária para semanal, mensal etc. A granularidade também é atualizada na tabela da fonte de dados. |
| **[!UICONTROL Mostrar mínimo]** ou <br/>**[!UICONTROL Mostrar máximo ]** | É possível sobrepor um rótulo de valor mínimo e máximo para realçar os valores mínimos e máximos em uma métrica. Os valores mínimos e máximos são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores em uma dimensão.<br/>![Uma sobreposição com o rótulo de valor mínimo e máximo.](assets/min-max-labels.png) |
| **[!UICONTROL Mostrar linha de tendência]** | É possível optar por adicionar uma regressão ou linha de tendência de média móvel à sua série de linhas. As linhas de tendência ajudam a representar um padrão mais claro nos dados. Após selecioná-la, escolha um modelo da lista. Consulte [Modelos](#models) para obter uma visão geral e descrição dos modelos disponíveis.<br/>![Linha de tendência linear](assets/show-linear-trendline.png). |

>[!TIP]
>
>Recomenda-se aplicar linhas de tendência a dados que não incluam o dia de hoje (dados parciais) ou datas futuras. O dia de hoje ou datas no futuro distorcem a linha de tendência. No entanto, se você precisar incluir datas futuras, remova os zeros dos dados para evitar distorções nesses dias. Acesse a tabela de fonte de dados da visualização, escolha a coluna da métrica e habilite **[!UICONTROL Configurações de coluna]** > **[!UICONTROL Interpretar zero como nenhum valor]**.



### Modelos

Todas as linhas de tendência do modelo de regressão são ajustadas usando mínimos quadrados comuns:

| Modelo | Descrição |
| --- | --- |
| **[!UICONTROL Linear]** | Cria uma linha reta com o melhor ajuste para conjuntos de dados lineares simples; isso é útil quando os dados aumentam ou diminuem em um ritmo constante. Equação: `y = a + b * x` |
| **[!UICONTROL Logarítmico]** | Cria uma linha curva com melhor ajuste; isso é útil quando o ritmo de alteração dos dados aumenta ou diminui rapidamente e, em seguida, estabiliza. Uma linha de tendência logarítmica pode usar valores negativos e positivos. Equação: `y = a + b * log(x)` |
| **[!UICONTROL Exponencial]** | Cria uma linha curva; isso é útil quando os dados sobem ou descem constantemente e em um ritmo crescente. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a + e^(b * x)` |
| **[!UICONTROL Potência]** | Cria uma linha curva; isso é útil para conjuntos de dados que comparam medidas que aumentam em um ritmo específico. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a * x^b` |
| **[!UICONTROL Quadrático]** | Encontra o melhor ajuste para um conjunto de dados em forma de parábola (côncava para cima ou para baixo). Equação: `y = a + b * x + c * x^2` |
| **[!UICONTROL Média móvel]** | Cria uma linha de tendência suave com base em um conjunto de médias. Também conhecida como média contínua, a média móvel usa um número específico de pontos de dados (determinado pela seleção de [!UICONTROL Granularidade]), cria uma média deles e usa essa média como um ponto na linha. Os exemplos incluem uma média móvel de sete dias ou de quatro semanas. |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

