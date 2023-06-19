---
description: Os componentes do Analysis Workspace consistem em dimensões, métricas, segmentos e intervalos de datas que você pode arrastar e soltar em um projeto.
title: Visão geral dos componentes
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: c64b4199d93443b14e2012459a4d33fdd847eca1
workflow-type: ht
source-wordcount: '1190'
ht-degree: 100%

---

# Visão geral dos componentes

Os componentes do Analysis Workspace consistem em dimensões, métricas, segmentos e intervalos de datas que você pode arrastar e soltar em um projeto.

Para acessar o menu Componentes, clique no ícone **[!UICONTROL Componentes]** no painel esquerdo. Você pode alternar entre [Painéis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=pt-BR), [Visualizações](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=pt-BR) e Componentes nos ícones do painel esquerdo ou usando [teclas de atalho](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

Você também pode ajustar a opção [Exibir configurações de densidade](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=pt-BR) para que o projeto veja mais valores no painel à esquerda ao mesmo tempo em **[!UICONTROL Projeto > Informações e configurações do projeto > Exibir densidade]**.

## Dimensões {#dimensions}

[**Dimensões**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html?lang=pt-BR) são atributos de texto que descrevem o comportamento do visitante e podem ser visualizadas, analisadas e comparadas na análise. Elas podem ser encontradas no painel Componente à esquerda (seção laranja) e normalmente são aplicadas como linhas de uma tabela.

Os exemplos de dimensões incluem [!UICONTROL Nome da página], [!UICONTROL Canais de marketing], [!UICONTROL Tipo de dispositivo] e [!UICONTROL Produtos]. As dimensões são fornecidas pela Adobe e são capturadas por meio de implementação personalizada (eVar, Props, classificações etc.).

Cada dimensão também contém **itens de dimensão**. Os itens de dimensão podem ser encontrados no painel Componente esquerdo clicando na seta para a direita ao lado de qualquer nome de dimensão (os itens são amarelos).

Os exemplos de itens de dimensão incluem [!UICONTROL Página inicial] (dentro da dimensão [!UICONTROL Página]), [!UICONTROL Pesquisa paga] (dentro da dimensão [!UICONTROL Canal de marketing]), [!UICONTROL Tablet] (dentro da dimensão [!UICONTROL Tipo de dispositivo móvel]) e assim por diante.

![](assets/dimensions.png)

## Métricas {#metrics}

[**Métricas**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html?lang=pt-BR) são medidas quantitativas sobre o comportamento do visitante. Elas podem ser encontradas no painel Componente à esquerda (seção verde) e normalmente são aplicadas como colunas de uma tabela.

Os exemplos de métricas incluem [!UICONTROL Visualizações de página], [!UICONTROL Visitas], [!UICONTROL Pedidos], [!UICONTROL Tempo médio gasto] e [!UICONTROL Receita/Pedido]. As métricas são fornecidas pela Adobe ou capturadas por meio de implementação personalizada ([!UICONTROL Eventos bem-sucedidos]), ou criadas usando o [Criador de métrica calculada](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=pt-BR).

![](assets/metrics.png)

## Segmentos {#segments}

[**Segmentos**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=pt-BR) são filtros de audiência aplicados à análise. Eles podem ser encontrados no painel Componente à esquerda (seção azul) e normalmente são aplicados na parte superior de um painel ou nas colunas de métrica acima em uma tabela.

Os exemplos de segmentos incluem [!UICONTROL Visitantes de dispositivo móvel], [!UICONTROL Visitas de email] e [!UICONTROL Ocorrências autenticadas]. Os segmentos são fornecidos pela Adobe, criados no [painel suspenso](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=pt-BR) ou criados usando o [Construtor de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=pt-BR).

![](assets/segments.png)

## Intervalos de datas {#date-ranges}

[**Intervalos de datas**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html?lang=pt-BR) são o intervalo de datas em que você faz a análise. Eles podem ser encontrados no painel Componente à esquerda (seção roxa) e normalmente são aplicados no calendário de cada painel.

É possível tornar os componentes do intervalo de datas relativos ao calendário do painel. Para obter informações adicionais, consulte [Sobre intervalos de datas relativos ao painel](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates).

Exemplos de intervalos de datas incluem julho de 2019, [!UICONTROL Últimas 4 semanas] e [!UICONTROL Este mês]. Os intervalos de datas são fornecidos pela Adobe, são aplicados no [calendário do painel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=pt-BR) ou são criados usando o [Criador de intervalo de datas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=pt-BR).

![](assets/date-ranges.png)


## Gerenciamento de componentes {#actions}

É possível gerenciar componentes diretamente no painel esquerdo.

1. Clique com o botão direito do mouse em um componente.

   Ou

   Selecione um componente e, em seguida, clique no ícone de **Ação** (3 pontos) na parte superior da lista de componentes.

   >[!TIP]
   >
   >   Você pode selecionar vários componentes mantendo a tecla Shift pressionada ou mantendo a tecla Command (no Mac) ou Ctrl (no Windows) pressionada.


   ![](assets/component-actions.png)

   | Ação de componente | Descrição |
   |--- |--- |
   | [!UICONTROL **Tag**] | Organize ou gerencie componentes aplicando tags. Em seguida, você pode pesquisar por tag no painel esquerdo clicando no filtro ou digitando #. As tags também atuam como filtros nos gerenciadores de componentes. |
   | [!UICONTROL **Adicionar aos favoritos**] | Adicione o componente à sua lista de favoritos. Como tags, você pode pesquisar por Favoritos no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
   | [!UICONTROL **Aprovar**] | Marque os componentes como Aprovado para avisar aos usuários que o componente é aprovado pela organização. Como tags, você pode pesquisar por Aprovado no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
   | [!UICONTROL **Compartilhar**] | Compartilhe componentes com usuários em sua organização. Essa opção está disponível somente para componentes personalizados, como segmentos ou métricas calculadas. |
   | [!UICONTROL **Excluir**] | Exclua componentes que não são mais necessários. Essa opção está disponível somente para componentes personalizados, como segmentos ou métricas calculadas. |

Os componentes personalizados também podem ser gerenciados por meio de seus respectivos Gerenciadores de componentes. Por exemplo, o [Gerenciador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md).

## Pesquisar, filtrar e classificar a lista de componentes

Pesquise, filtre e classifique a lista de componentes no painel esquerdo do Analysis Workspace para localizar rapidamente um componente específico.

### Pesquisar a lista de componentes

1. Selecione o ícone de **Componentes**, ![Ícone de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg), no painel esquerdo.

2. No campo de pesquisa, comece a digitar o nome do componente que deseja usar em seu projeto.

   O tipo de componente pode ser identificado tanto por cor como ícone. **Dimensões** e ![Ícone de dimensão](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranjas, **Segmentos** e ![Ícone de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, **Intervalos de datas** e ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e **Métricas** e ![Ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone da Adobe indica um modelo de métrica calculada ou um modelo de segmento e o ícone de calculadora, ![Ícone de Calculadora](assets/calculated-metric-icon-created.png), indica uma métrica calculada que foi criada por um administrador do Analytics em sua organização.

3. Selecione o componente quando ele aparecer na lista suspensa.

### Filtragem da lista de componentes

1. Selecione o ícone de **Componentes**, ![Ícone de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg), no painel esquerdo.

2. Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg).

   Ou

   Digite o sinal de libra (#) no campo de pesquisa.

3. Selecione qualquer uma das seguintes opções de filtro para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. |
   | [!UICONTROL **Segmentos**] | Mostrar somente componentes que são segmentos. <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |

4. (Opcional) Para aprimorar ainda mais a lista, é possível classificar a lista de componentes, conforme descrito em [Classificação da lista de componentes](#sort-the-component-list).

### Classificação da lista de componentes

{{release-limited-testing-section}}

1. (Opcional) Aplique filtros à lista de componentes, conforme descrito em [Filtragem da lista de componentes](#filter-the-component-list).

2. Selecione o ícone de **Componentes**, ![Ícone de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg), no painel esquerdo.

3. Selecione o ícone de **Classificação** ![Ícone de classificação de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), em seguida, selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

   {{components-sort-options}}
