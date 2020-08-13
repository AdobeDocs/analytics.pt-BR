---
description: Use a visualização de linha para descrever conjuntos de dados com tendência (baseados em tempo)
title: Linha
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 78ed02b7bb7a4dc042c837817d36fc8ce30dce79
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 17%

---


# Linha

Esta visualização representa as métricas que usam uma linha para mostrar como os valores são alterados em um período de tempo. Um gráfico de linha pode ser usado apenas quando o horário for usado como uma dimensão.

## Configurações de visualização

>[!IMPORTANT]
>
> Algumas configurações de visualização de Linha, como Adicionar linha de tendência, estão atualmente em testes limitados. [Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/landing/an-releases.html).

Clique no ícone de engrenagem na parte superior direita da visualização de Linha para acessar as configurações [**de**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html#section_D3BB5042A92245D8BF6BCF072C66624B) Visualização disponíveis. As configurações são categorizadas em:

* Geral - configurações comuns em tipos de visualização
* Eixo - configurações que afetarão o eixo x ou y da visualização de linha
* Overlays - opções para adicionar contexto adicional à série mostrada na visualização da linha.

### Alterar granularidade

Uma opção suspensa de granularidade nas [configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B) permite alterar uma visualização com tendência (por exemplo, linha, barra) de diária para semanal, mensal etc.

### Adicionar uma sobreposição de linha de tendência

Em Configurações de **visualização > Sobreposições > Adicionar linha de tendência**, você pode optar por adicionar uma linha de tendência de regressão à sua série de linhas. As linhas de tendência ajudam a descrever um padrão mais claro nos dados.

Todos os modelos são adequados usando quadrados mínimos comuns:

| Modelo | Descrição |
|---|---|
| Linear | Cria uma linha reta de melhor ajuste para conjuntos de dados lineares simples e é útil quando os dados aumentam ou diminuem a uma taxa estável. Equação: y = a + b * x |
| Logarítmico | Cria uma linha curva de melhor ajuste e é útil quando a taxa de alteração nos dados aumenta ou diminui rapidamente e, em seguida, atinge o nível limite. Uma linha de tendência logarítmica pode usar valores negativos e positivos. Equação: y = a + b * log(x) |
| Exponencial | Cria uma linha curva e é útil quando os dados aumentam ou caem em taxas constantemente crescentes. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: y = a +<sup>eb * x |
| Alimentação | Cria uma linha curva e é útil para conjuntos de dados que comparam medidas que aumentam em uma taxa específica. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: y = a *<sup>xb |
| Quadrado | Encontra o melhor ajuste para um conjunto de dados em forma de parábola (côncavo para cima ou para baixo). Equação: y = a + b * x + c * x<sup>2 |
| Polinomial | Útil quando seu conjunto de dados flutua, como a análise de ganhos e perdas em um grande conjunto de dados. Equação: y = a + b * x + ... + k *<sup>xorder |
