---
description: Use a visualização de linha para descrever conjuntos de dados com tendência (baseados em tempo)
title: Linha
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 3ace7c4fc42e578b621433860ae3f0dba6be06fd
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 12%

---


# Linha

A visualização de Linha representa as métricas que usam uma linha para mostrar como os valores mudam ao longo de um período de tempo. Um gráfico de linha pode ser usado apenas quando o horário for usado como uma dimensão.

![Visualização de linha](assets/line-viz.png)

>[!IMPORTANT]
>
>Algumas configurações de visualização de Linha, como [!UICONTROL Mostrar linha de tendência], estão atualmente em testes limitados. [Saiba mais](/help/landing/an-releases.md)

Clique no ícone de engrenagem na parte superior direita da visualização de Linha para acessar as configurações [**de**](freeform-analysis-visualizations.md) Visualização disponíveis. As configurações são categorizadas em:

* **Geral**: Configurações comuns em tipos de visualização
* **Eixo**: Configurações que afetam o eixo x ou y da visualização de linha
* **Sobreposições**: Opções para adicionar contexto adicional à série mostrada na visualização de linha.

![Configurações de visualização](assets/viz-settings-modal.png)

## Alterar granularidade

Uma opção suspensa de granularidade nas [configurações de visualização](freeform-analysis-visualizations.md) permite alterar uma visualização com tendência (por exemplo, linha, barra) de diária para semanal, mensal etc. A granularidade também é atualizada na tabela da fonte de dados.

## Mostrar mín. ou máx.

Em Configurações **[!UICONTROL de]** visualização > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar mín/máx]**, você pode sobrepor um rótulo de valor mínimo e máximo para realçar rapidamente os picos e vales em uma métrica.

![Mostrar mín/máx](assets/min-max-labels.png)

## Mostrar sobreposição de linha de tendência

Em Configurações **[!UICONTROL de]** visualização > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar linha de tendência]**, você pode optar por adicionar uma linha de tendência de regressão à sua série de linhas. As linhas de tendência ajudam a descrever um padrão mais claro nos dados.

![Linha de tendência linear](assets/show-linear-trendline.png)

Todos os modelos são adequados usando quadrados mínimos comuns:

| Modelo | Descrição |
|---|---|
| Linear | Cria uma linha reta de melhor ajuste para conjuntos de dados lineares simples e é útil quando os dados aumentam ou diminuem a uma taxa estável. Equação: `y = a + b * x` |
| Logarítmico | Cria uma linha curva de melhor ajuste e é útil quando a taxa de alteração nos dados aumenta ou diminui rapidamente e, em seguida, atinge o nível limite. Uma linha de tendência logarítmica pode usar valores negativos e positivos. Equação: `y = a + b * log(x)` |
| Exponencial | Cria uma linha curva e é útil quando os dados aumentam ou caem em taxas constantemente crescentes. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a + e^(b * x)` |
| Alimentação | Cria uma linha curva e é útil para conjuntos de dados que comparam medidas que aumentam em uma taxa específica. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a * x^b` |
| Quadrado | Encontra o melhor ajuste para um conjunto de dados em forma de parábola (côncavo para cima ou para baixo). Equação: `y = a + b * x + c * x^2` |
