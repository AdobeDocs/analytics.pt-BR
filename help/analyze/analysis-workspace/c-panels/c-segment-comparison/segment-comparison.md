---
title: Visão geral do painel de comparação de segmentos
description: Saiba como usar o painel de comparação de segmentos, parte do QI do segmento na Analysis Workspace.
keywords: Analysis Workspace;IQ do segmento
solution: Analytics
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# Visão geral do painel de comparação de segmentos

O painel de comparação de segmentos é uma ferramenta do QI [do](../../segment-iq.md) segmento que descobre as diferenças estatisticamente mais significativas entre um número ilimitado de segmentos. O recurso é repetido por meio de uma análise automatizada de todas as dimensões e métricas a que você tem acesso. Ela descobre automaticamente as principais características dos segmentos de público-alvo que estão liderando os KPIs de sua empresa e permite que você veja o quanto qualquer segmento se sobrepõe.

## Criação de um painel de comparação de segmentos

1. Faça logon em [experience.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
1. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
1. Na barra de navegação superior, clique em Espaço de trabalho.
1. Clique no botão 'Criar novo projeto'.
1. No pop-up modal, verifique se "Projeto em branco" está selecionado e clique em Criar.
1. Clique no botão Painéis à esquerda e arraste o painel Comparação de segmentos acima ou abaixo do painel de tabela de forma livre criado automaticamente.

   ![Comparar painel](assets/seg-compare-panel.png)

1. Selecione segmentos para deseja comparar e arraste-os para o painel.

   ![Comparar públicos-alvo](assets/compare-audiences.png)

   Depois de arrastar um segmento para o painel, o Analytics cria automaticamente um segmento [!UICONTROL 'Todos os outros'] que inclui todos os que NÃO estão no segmento escolhido. É um segmento frequentemente usado no painel de comparação, mas você pode removê-lo e comparar um segmento diferente de escolha.

   ![Todos os outros](assets/everyone-else.png)

1. Depois de determinar quais dois segmentos serão comparados, clique em [!UICONTROL Criar].

   Esta ação inicia um processo de backend que busca diferenças estatísticas entre os dois segmentos selecionados e todas as dimensões, métricas e outros segmentos. Uma barra de progresso na parte superior do painel indica o tempo restante até que cada métrica e dimensão sejam analisadas. As métricas, dimensões e segmentos usados com mais frequência são priorizados para serem executados primeiro para que os resultados mais relevantes sejam retornados em tempo hábil.

## Excluir componentes da comparação

Às vezes, é necessário excluir algumas dimensões, métricas ou segmentos das comparações de segmentos. Por exemplo, você deseja comparar o segmento "Usuários do US Mobile" com "Usuários do German Mobile". A inclusão de dimensões relacionadas à geografia não faria sentido, já que esses segmentos já implicam essas diferenças.

1. Depois que os dois segmentos desejados estiverem no painel, clique em [!UICONTROL 'Mostrar opções avançadas'].
1. Drag and drop components you want to exclude into the [!UICONTROL Excluded Components] panel.

   ![Componentes excluídos](assets/excluded-components.png)

Clique em [!UICONTROL 'Definir como padrão'] para excluir automaticamente seus componentes atuais em todas as comparações de segmentos futuras. Se quiser editar componentes excluídos, clique em um tipo de componente e, em seguida, clique no 'X' ao lado de um componente para reincluí-lo na análise. Clique em 'Limpar tudo' para incluir novamente todos os componentes na comparação de segmentos.

![Dimensões excluídas](assets/excluded-dimensions.png)

## Exibindo um relatório de comparação de segmentos

Quando a Adobe terminar de analisar os dois segmentos desejados, mostrará seus resultados por meio de várias visualizações:

![Visualizações 1](assets/new-viz.png)

![Visualizações 2](assets/new-viz2.png)

### Tamanho e sobreposição

Ilustra os tamanhos comparativos de cada segmento selecionado e o quanto eles se sobrepõem entre si usando um diagrama venn. Você pode passar o mouse sobre o visual para ver quantos visitantes estavam em cada sobreposição ou na seção de não sobreposição. Você também pode clicar com o botão direito do mouse na sobreposição para criar um novo segmento para uma análise futura. Se os dois segmentos forem mutuamente exclusivos, nenhuma sobreposição será mostrada entre os dois círculos (normalmente visto com segmentos usando um contêiner de ocorrência).

![Tamanho e sobreposição](assets/size-overlap.png)

### Resumos populacionais

À direita da visualização Tamanho e sobreposição, a contagem total de visitantes únicos em cada segmento e sobreposição é mostrada.

![Resumos populacionais](assets/population_summaries.png)

### Principais métricas

Exibe as métricas estatisticamente mais significativas entre os dois segmentos. Cada linha neste gráfico representa uma métrica diferenciada, classificada pelo grau de diferença de cada segmento. Uma pontuação de diferença de 1 significa que é estatisticamente significativa, enquanto uma pontuação de diferença de 0 significa que não há significância estatística.

Essa visualização é semelhante às tabelas de forma livre na Analysis Workspace. Se for desejada uma análise mais profunda em uma métrica específica, passe o mouse sobre um item de linha e clique em "Criar visual". Uma nova tabela é criada para analisar essa métrica específica. Se uma métrica for irrelevante para sua análise, passe o mouse sobre o item de linha e clique no X para removê-la.

> [!NOTE] As métricas adicionadas a esta tabela após a conclusão da comparação de segmentos não recebem uma Pontuação de diferença.

![Principais métricas](assets/top-metrics.png)

### Métrica ao longo do tempo por segmento

À direita do gráfico de métricas há uma visualização vinculada. Você pode clicar em um item de linha na tabela à esquerda, e essa visualização é atualizada para mostrar a tendência da métrica ao longo do tempo.

![Linha de métricas principais](assets/linked-viz.png)

### Dimensões principais

Mostra os valores de dimensão mais significativos estatisticamente em todas as dimensões. Cada linha mostra a porcentagem de cada segmento que exibe esse valor de dimensão. Por exemplo, esta tabela pode revelar que 100% dos visitantes em 'Segmento A' tinham o item de dimensão 'Tipo de navegador: Google, enquanto apenas 19,6% do "Segmento B" tinha esse item de dimensão. Uma pontuação de diferença de 1 significa que é estatisticamente significativa, enquanto uma pontuação de diferença de 0 significa que não há significância estatística.

Essa visualização é semelhante às tabelas de forma livre na Analysis Workspace. Se desejar uma análise mais profunda em um valor de dimensão específico, passe o mouse sobre um item de linha e clique em "Criar visual". Uma nova tabela é criada para analisar esse valor de dimensão específico. Se um valor de dimensão for irrelevante para sua análise, passe o mouse sobre o item de linha e clique no 'X' para removê-lo.

> [!NOTE] Os valores de dimensão adicionados a esta tabela após a conclusão da comparação de segmentos não recebem uma Pontuação de diferença.

![Dimensões principais](assets/top-dimension-item1.png)

### Itens de dimensão por segmento

À direita da tabela de dimensões há uma visualização de gráfico de barras vinculado. Mostra todos os valores de dimensão exibidos em um gráfico de barras. Clicar em um item de linha na tabela à esquerda atualiza a visualização à direita.

![Gráfico de barras das principais dimensões](assets/top-dimension-item.png)

### Principais segmentos

Mostra quais outros segmentos (diferentes dos dois segmentos selecionados para comparação) têm sobreposição estatisticamente significativa. Por exemplo, esta tabela pode mostrar que um terceiro segmento, "Repetir visitantes", sobrepõe-se fortemente ao "Segmento A", mas não se sobrepõe ao "Segmento B". Uma pontuação de diferença de 1 significa que é estatisticamente significativa, enquanto uma pontuação de diferença de 0 significa que não há significância estatística.

Essa visualização é semelhante às tabelas de forma livre na Analysis Workspace. Se for desejada uma análise mais profunda em um segmento específico, passe o mouse sobre um item de linha e clique em "Criar visual". Uma nova tabela é criada para analisar esse segmento específico. Se um segmento for irrelevante para sua análise, passe o mouse sobre o item de linha e clique no X para removê-lo.

> [!NOTE] Os segmentos adicionados a esta tabela após a conclusão da comparação de segmentos não recebem uma Pontuação de diferença.

![Principais segmentos](assets/top-segments.png)

### Sobreposição de segmentos

À direita da tabela de segmentos está uma visualização de diagrama venn vinculado. Ele mostra o segmento mais significativo estatisticamente aplicado aos seus segmentos comparados. Por exemplo, "Segmento A" + "Segmento estatisticamente significativo" vs. 'Segmento B' + 'Segmento estatisticamente significativo'. Clicar em um item de linha de segmento na tabela à esquerda atualiza o diagrama venn à direita.

![Principais segmentos em diagrama](assets/segment-overlap.png)
