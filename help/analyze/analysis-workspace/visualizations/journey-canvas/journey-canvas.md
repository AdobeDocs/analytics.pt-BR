---
description: Saiba como usar a tela de jornada no Analysis Workspace.
title: Visão geral da tela da jornada
feature: Visualizations
hide: true
role: User, Admin
source-git-commit: 035723a8a1dcdee96c9be9a2ee7a0b2e98a8f56e
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 88%

---

# Visão geral da tela da jornada {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="Tela de jornada"
>abstract="Mostra como as pessoas avançam ou abandonam uma série de pontos de contato. Use para jornadas com vários pontos de entrada e caminhos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="Tela de jornada"
>abstract="Analise como as pessoas avançam ou abandonam uma jornada definida. Gere análises de jornadas do usuário criando um gráfico flexível de nós e setas para representar qualquer combinação de eventos, itens de dimensão e segmentos. Arraste os nós na tela para reorganizar os eventos e as condições da jornada. À medida que você faz isso, os dados são atualizados de acordo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button2"
>title="Tela de jornada"
>abstract="Mostra como as pessoas avançam ou abandonam uma série de pontos de contato. Use para jornadas com vários pontos de entrada e caminhos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel2"
>title="Tela de jornada"
>abstract="Analise como as pessoas avançam ou abandonam uma jornada definida. Gere análises de jornadas do usuário criando um gráfico flexível de nós e setas para representar qualquer combinação de eventos, itens de dimensão e segmentos. Arraste os nós na tela para reorganizar os eventos e as condições da jornada. À medida que você faz isso, os dados são atualizados de acordo."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artigo documenta a visualização da tela de Jornada no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**.<br/><br/>_ Consulte a [visão geral da tela de Jornada](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas) da versão _![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)_**Customer Journey Analytics**deste artigo._

>[!ENDSHADEBOX]

{{release-limited-testing}}

A Visualização de tela da jornada permite analisar e obter insights profundos sobre as jornadas fornecidas aos usuários e clientes. Ela permite definir uma jornada e, em seguida, ver como as pessoas saíram (caíram) ou continuaram (caíram) na jornada.

Você pode [criar análises de jornadas do usuário](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) usando qualquer combinação de eventos, itens de dimensão, segmentos e intervalos de datas para criar nós de jornada. Conecte os nós para criar o fluxo da jornada e incluir vários caminhos e pontos de decisão. Arraste os nós na tela para reorganizar os eventos e as condições da jornada. Atualizações de dados em tempo real à medida que você faz alterações.

[Os nós estão conectados](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) como um &quot;caminho eventual&quot;, o que significa que os visitantes são contados enquanto eventualmente se movem de um nó para outro, independentemente de quaisquer eventos que ocorram entre os dois nós. O tempo alocado para que os usuários percorram o caminho é determinado pela configuração do container.

![Tela da jornada](assets/journey-canvas.png)

## Recursos principais

Os recursos principais da Visualização de tela da jornada incluem:

* Análise profunda de fallout e fallthrough que acomoda as jornadas de usuário mais complexas.

* Uma tela para mapear e visualizar os vários pontos de entrada, nós e caminhos de uma jornada de usuário.

* Interações de arrastar e soltar para adicionar componentes à tela e para reposicionar nós existentes.

## Possíveis insights

A tela da jornada fornece insights acionáveis para as jornadas mais complexas.

### Caminho com a taxa de conversão mais alta {#conversion-rate-caption}

O insight mais proeminente na tela da jornada é mostrado como uma legenda na parte superior da tela.

Esta legenda resume qual caminho, de todos os caminhos na jornada, tem a taxa de conversão mais alta.

Quando a jornada contém vários nós iniciais, a legenda tem esta aparência:

![Legenda de insight da tela da jornada](assets/journey-canvas-caption.png)

Quando a jornada contém um único nó inicial, a legenda tem esta aparência:

![Nó de início único da legenda de insight da tela da jornada](assets/journey-canvas-caption-singlestart.png)

Considere o seguinte ao interpretar esta legenda:

* Um _caminho_ é definido como um nó inicial que é conectado por setas a um nó final, com qualquer número de nós conectados entre eles.

* O cálculo da taxa de conversão depende do tipo de jornada (o número de nós iniciais e finais contidos na jornada e se os caminhos se cruzam entre eles).

  A tabela a seguir descreve como as taxas de conversão são calculadas com base no tipo de jornada:

  | Tipo de jornada | Cálculo da taxa de conversão | Exemplo |
  |---------|----------|---------|
  | **Um único nó inicial e um único nó final** | A taxa de conversão é calculada dividindo o número do nó final pelo do nó inicial. | ![Jornada com vários inícios que convergem em um nó comum](assets/journey-canvas-single-path.png) |
  | **Um único nó inicial e vários nós finais** | A taxa de conversão é calculada localizando o nó final com o número mais alto e dividindo esse número pelo do nó inicial. | ![Jornada com vários inícios que convergem em um nó comum](assets/journey-canvas-singlestart-multiend.png) |
  | **Vários caminhos independentes, com cada caminho contendo um único nó inicial e um único nó final** | A taxa de conversão é calculada dividindo o número do nó final pelo do nó inicial. O caminho com a taxa de conversão mais alta está descrito na legenda. | ![Jornada com vários inícios que convergem em um nó comum](assets/journey-canvas-multi-start-separate.png) |
  | **Vários nós iniciais que em qualquer ponto da jornada convergem em um nó comum** | A taxa de conversão é calculada localizando o nó final com o número mais alto e dividindo esse número pelo do nó inicial com o número mais baixo. | ![Jornada com vários inícios que convergem em um nó comum](assets/journey-canvas-multi-start-converge.png) |

### Fallthrough, Fallout e outros

A seguir estão alguns exemplos de outros insights que a tela da jornada pode ajudar a fornecer. Você pode escolher se esses insights são baseados em todas as pessoas no conjunto de relatórios, todas as pessoas que iniciaram a jornada ou todas as pessoas do nó anterior da jornada.

#### Falha

* O número e a porcentagem de pessoas que concluíram a jornada (chegou ao nó final)

* O número e a porcentagem de pessoas que chegaram a um determinado nó da jornada

* A etapa mais comum que veio antes ou após um determinado nó da jornada

#### Fallout

* Os nós da jornada em que mais frequentemente as pessoas a abandonam (nunca chegam a nenhum dos nós seguintes imediatos)

#### Dados adicionais para cada nó

* Adicione uma dimensão de detalhamento em qualquer nó da jornada para visualizar dados adicionais desse nó específico

## Escolha entre as Visualizações de tela da jornada, fallout ou fluxo.

A Visualização de tela da jornada é semelhante à [Visualização de fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) e à [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), mas possui diferenças importantes.

### Entenda as diferenças

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quando usar a tela da jornada

A tela da jornada é essencial para:

* Análise de fallout envolvendo jornadas com vários pontos de entrada e caminhos.

* Jornadas não lineares com vários pontos de entrada e caminhos, com uma sequência predefinida de páginas.

* Análise ad hoc exploratória baseada em uma jornada predefinida.

* Análise que requer uma métrica principal diferente de Sessão, Pessoa ou Ocorrências.

Use [a tabela acima](#understand-the-differences) para entender as diferenças entre as Visualizações de tela da jornada, fallout e fluxo.

## Criar análises na tela de jornada

Você pode criar análises na tela de jornada com base em qualquer dimensão ou métrica disponível no Analysis Workspace. Para  mais informações, consulte [Configurar uma visualização da tela de jornada](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


>[!MORELIKETHIS]
>
> * [Guia para visualização da tela de jornada no Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

