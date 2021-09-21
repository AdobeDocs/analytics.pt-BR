---
description: Use a visualização de linha para descrever conjuntos de dados com tendência (de acordo com o tempo)
title: Linha
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: 804cf43f2e5f1270e04644affd629c06583816ec
workflow-type: ht
source-wordcount: '521'
ht-degree: 100%

---

# Linha

A visualização de [!UICONTROL linha] representa as métricas usando uma linha para mostrar como os valores são alterados em um período. Um gráfico de [!UICONTROL linha] pode ser usado apenas quando o horário é usado como uma dimensão.

![Visualização de linha](assets/line-viz.png)

Clique no ícone de engrenagem na parte superior direita da visualização de [!UICONTROL linha] para acessar as [**Configurações de visualização**](freeform-analysis-visualizations.md) disponíveis. As configurações são categorizadas em:

* **Geral**: configurações comuns em tipos de visualização
* **Eixo**: configurações que afetam o eixo x ou y da visualização de linha
* **Sobreposições**: opções para adicionar contexto adicional à série mostrada na visualização de linha.

![Configurações de visualização](assets/viz-settings-modal.png)

## Alterar granularidade

Uma opção suspensa de granularidade nas [configurações de visualização](freeform-analysis-visualizations.md) permite alterar uma visualização com tendência (por exemplo, linha, barra) de diária para semanal, mensal etc. A granularidade também é atualizada na tabela da fonte de dados.

## Mostrar mín. ou máx.

Em **[!UICONTROL Configurações de visualização]** > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar mín/máx]**, você pode sobrepor um rótulo de valor mínimo e máximo para realçar rapidamente os picos e vales em uma métrica. Observação: os valores mín./máx. são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores em uma dimensão.

![Mostrar mín/máx](assets/min-max-labels.png)

## Mostrar sobreposição de linha de tendência

Em **[!UICONTROL Configurações de visualização]** > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar linha de tendências]**, você pode adicionar uma regressão ou linha de tendência de média móvel à sua série de linhas. As linhas de tendência ajudam a descrever um padrão mais claro nos dados.

Este é um vídeo sobre como adicionar linhas de tendência às visualizações de linha:

>[!VIDEO](https://video.tv.adobe.com/v/330176/?quality=12)

>[!TIP]
>
>Recomenda-se que linhas de tendência sejam aplicadas a dados que não incluem hoje (dados parciais) ou datas futuras, pois elas distorcerão a linha de tendência. No entanto, se você precisar incluir datas futuras, remova zeros dos dados para evitar distorções nesses dias. Para fazer isso, vá para a tabela de fonte de dados da visualização, escolha a coluna de métrica e ative **[!UICONTROL Configurações de coluna]** > **[!UICONTROL Interpretar zero como nenhum valor]**.

![Linha de tendência linear](assets/show-linear-trendline.png)

Todas as linhas de tendência do modelo de regressão são ajustadas usando mínimos quadrados comuns:

| Modelo | Descrição |
| --- | --- |
| Linear | Cria uma linha reta de melhor ajuste para conjuntos de dados lineares simples e é útil quando os dados aumentam ou diminuem a uma taxa estável. Equação: `y = a + b * x` |
| Logarítmico | Cria uma linha curva de melhor ajuste e é útil quando a taxa de alteração nos dados aumenta ou diminui rapidamente e, em seguida, nivela. Uma linha de tendência logarítmica pode usar valores negativos e positivos. Equação: `y = a + b * log(x)` |
| Exponencial | Cria uma linha curva e é útil quando os dados aumentam ou caem em taxas constantemente crescentes. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a + e^(b * x)` |
| Potência | Cria uma linha curva e é útil para conjuntos de dados que comparam medidas que aumentam a uma taxa específica. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a * x^b` |
| Quadrático | Encontra o melhor ajuste para um conjunto de dados em forma de parábola (côncavo para cima ou para baixo). Equação: `y = a + b * x + c * x^2` |
| Média móvel | Cria uma linha de tendências suave com base em um conjunto de médias. Também conhecida como média variável, a média móvel usa um número específico de pontos de dados (determinado por sua seleção de &#39;Períodos&#39;), calcula a média deles e usa a média como um ponto na linha. Os exemplos incluem média móvel de sete dias ou média móvel de quatro semanas. |
