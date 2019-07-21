---
description: A ferramenta Comparação de segmentos (QI de segmento) descobre as diferenças estatisticamente mais importantes entre um número ilimitado de segmentos por meio de uma análise automatizada de todas as métricas e dimensões que você já acessou. Ela descobre as principais características dos segmentos do público-alvo que estão liderando os KPIs da sua empresa e permite que você veja o nível de sobreposição entre quaisquer segmentos.
keywords: Analysis Workspace; IQ do segmento
seo-description: A ferramenta Comparação de segmentos (QI de segmento) descobre as diferenças estatisticamente mais importantes entre um número ilimitado de segmentos por meio de uma análise automatizada de todas as métricas e dimensões que você já acessou. Ela descobre as principais características dos segmentos do público-alvo que estão liderando os KPIs da sua empresa e permite que você veja o nível de sobreposição entre quaisquer segmentos.
seo-title: Visão geral do IQ do segmento
solution: Analytics
title: Visão geral do IQ do segmento
topic: Reports and Analytics
uuid: 80 b 8343 a -8 e 09-4234-9510-1 eecce 18567 f
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Visão geral do IQ do segmento

A ferramenta Comparação de segmentos (QI de segmento) descobre as diferenças estatisticamente mais importantes entre um número ilimitado de segmentos por meio de uma análise automatizada de todas as métricas e dimensões que você já acessou. Ela descobre as principais características dos segmentos do público-alvo que estão liderando os KPIs da sua empresa e permite que você veja o nível de sobreposição entre quaisquer segmentos.

Os analistas passam várias horas ou até mesmo dias buscando por diferenças relevantes entre segmentos das faixas amplas de métricas e dimensões da sua empresa. Essa análise, além de tediosa e demorada, não lhe dá a certeza de que você não deixou passar uma diferença importante sobre um segmento que faria uma grande diferença nos seus objetivos de marketing.

[Comparação de segmentos no youtube](https://www.youtube.com/watch?v=fO3PNB93U_w&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=38) (4:46)

Aqui estão alguns dos novos conceitos, visualizações e gráficos mais importantes que foram apresentados com a ferramenta Comparação de segmentos:

## “Everyone else” segment {#section_30AEE8181E5D46D9AB27F7CA3815D0CD}

Para conveniência, adicionamos o segmento «todos os outros» para que não seja necessário criá-lo manualmente. Por exemplo, use o público-alvo Compradores. Não é necessário criar um segmento não Compradores, já que ele já está incluído no segmento «todos os outros» e pode ser removido rapidamente se você preferir adicionar um segmento diferente para comparação.

## Size and overlap {#section_885A71EE458C43189A77B8F552CA346A}

A visualização Tamanho e sobreposição ilustra os tamanhos comparativos de cada segmento selecionado e o nível de sobreposição de cada um. Você pode passar o mouse sobre o visual para ver quantos visitantes estavam em cada sobreposição ou na seção de não sobreposição. Você também pode clicar com o botão direito do mouse na sobreposição para criar um novo segmento para uma análise futura. Se dois segmentos não se sobrepõem (por exemplo, se estiver usando o segmento «todos os outros»), você também verá isso refletido neste visual.

![](assets/size-overlap.png)

## Population summaries {#section_21F2B66C60184A71B89E2982A6FB945D}

À direita do visual Tamanho e cruzamento, a ferramenta Comparação de segmentos mostra uma contagem de visitante único em cada segmento e a população da sobreposição.

![](assets/population_summaries.png)

## Top metrics {#section_E4A38516424949B79A559DC8793071F2}

>[!NOTE]
>
>Os itens de linha aplicados após a comparação de segmentos não recebem uma Pontuação de diferença; a tabela carregará somente os dados de métrica para os dois segmentos que estão sendo comparados

O gráfico de métricas superior mostra as métricas estatisticamente mais distintas entre dois segmentos que você selecionou. Cada linha neste gráfico representa uma métrica diferenciada, classificada pelo grau de diferença de cada segmento. As métricas também são exibidas com base nos visitantes, logo, se a opção “Visitantes” aparece no gráfico, os números correspondentes neste gráfico representam o número médio de visitas por visitante em cada segmento. Também oferecemos uma pontuação diferente indicando o quão diferente essa métrica é destes dois segmentos. Uma pontuação igual a 1 representa uma grande diferença estatística, e uma pontuação igual a 0 significa que não há diferença estatística.

Para obter mais detalhes sobre como são calculadas as diferentes pontuações de cada gráfico, consulte [Testes estatísticos usados na comparação entre segmentos](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4).

O gráfico Principais métricas é similar a qualquer outro gráfico que você usa na Analysis Workspace. Arraste qualquer métrica que você esteja interessado para o gráfico e mostraremos a comparação.

Você pode personalizar o gráfico da forma que desejar. Também adicionamos um novo ícone de “criar visual” em cada linha do gráfico. Ao clicar nesse ícone, são criados um novo gráfico e um novo visual acima da Ferramenta de comparação entre segmentos se você não quiser aglomerar o Gráfico de métricas principais e preferir continuar com uma análise mais profunda em um novo gráfico. Se essa métrica não for relevante, clique no “X” para removê-la do gráfico. Por fim, assim como em outros Gráficos de forma, você pode paginar a lista de métricas exibidas ou exibir as 10, 20, 50 mais importantes, se quiser ver mais do que os cinco itens de linhas exibidos por padrão.

![](assets/top-metrics.png)

À direita do gráfico de métricas há uma visualização vinculada. Por padrão, a Ferramenta de comparação entre segmentos exibirá a métrica principal no gráfico dos últimos 30 dias para cada segmento. Se você quiser visualizar outra métrica no gráfico Principais métricas, basta selecioná-la e a visualização à direita será atualizada e mostrará a métrica selecionada.

![](assets/linked-viz.png)

## Top dimension items {#section_439C1782B153427CB4FB85E177146EC0}

>[!NOTE]
>
>Os itens de linha aplicados após a comparação de segmentos não recebem uma Pontuação de diferença; a tabela carregará somente os dados de métrica para os dois segmentos que estão sendo comparados

Assim como o gráfico Principais métricas, a Ferramenta comparação entre segmentos possui um gráfico Principais itens de dimensão ilustrando os itens de dimensão mais diferenciados em todas as suas dimensões. Cada linha mostra a porcentagem de cada segmento que exibe este item de dimensão.

Por exemplo, se estiver comparando o “Segmento A” com o “Segmento B”, o gráfico Principais itens de dimensão pode revelar que 100% dos visitantes no “Segmento A” tinham o item de dimensão Tipo de navegador: Google, enquanto apenas 19.6% dos visitantes do “Segmento B” tinham este item de dimensão.

![](assets/top-dimension-item1.png)

À direita do gráfico Principais itens de dimensão, a Ferramenta comparação entre segmentos destaca o principal item de dimensão selecionado junto com outros itens de dimensão principais a partir daquela dimensão para comparação:

![](assets/top-dimension-item.png)

## Top segments table {#section_6A0C39F930564240AF7A157005C7A80B}

>[!NOTE]
>
>Os itens de linha aplicados após a comparação de segmentos não recebem uma Pontuação de diferença; a tabela carregará somente os dados de métrica para os dois segmentos que estão sendo comparados

O gráfico Principais segmentos é um gráfico útil que mostra quais segmentos (em vez de dois segmentos selecionados para comparação) se sobrepõem de maneira muito diferente em relação a dois segmentos selecionados. Por exemplo, ao comparar o Segmento A com o Segmento B, o gráfico Principais segmentos pode mostrar que um terceiro segmento, “Repetir visitantes” sobrepõe de maneira intensa com o Segmento A mas que não sobrepõe com o Segmento B.

![](assets/top-segments.png)

Além disso, o segmento adicional de diferenciação principal é exibido em um visual de sobreposição à direita do gráfico:

![](assets/segment-overlap.png)

O visual de sobreposição indica graficamente a diferença na sobreposição entre todos os três segmentos e, assim como outros visuais vinculados, ao clicar em cada segmento adicional no gráfico, o visual será atualizado para que corresponda ao segmento selecionado.

Clique aqui para obter mais informações sobre os [testes estatísticos](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4) usados na comparação de segmentos.
