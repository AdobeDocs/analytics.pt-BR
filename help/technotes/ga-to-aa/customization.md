---
title: Personalização de relatórios no Adobe Analytics
description: Saiba como personalizar relatórios no Adobe Analytics
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Personalizar relatórios

Em plataformas de terceiros, como o Google Analytics, há várias opções de personalização disponíveis. Essas personalizações permitem que um usuário crie painéis, relatórios personalizados, relatórios salvos e alertas personalizados. Como a Analysis Workspace permite que os usuários criem relatórios a partir de uma tela em branco, a maioria das personalizações são criadas diretamente na ferramenta.

Esta página considera que o usuário tem um conhecimento básico sobre como usar a Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Painéis

A arquitetura da Analysis Workspace é similar ao conceito de widgets de painel. Os projetos na Analysis Workspace são equivalentes aos painéis no Google Analytics. As visualizações na Analysis Workspace são equivalentes a widgets no Google Analytics.

### Adicionar conteúdo a um projeto

1. Clique no ícone Visualizações à esquerda e arraste a visualização desejada para a área de trabalho.
2. Clique no ícone Componentes à esquerda e arraste as dimensões e métricas desejadas para a visualização para preenchê-la com dados.
3. Arraste as bordas da visualização para redimensioná-la e arraste o título da visualização para movê-la.

Todos os widgets do Google Analytics estão disponíveis na Analysis Workspace:

* The **Metric widget** is approximately equal to the Summary Number visualization.
* The **Timeline widget** is approximately equal to the Line visualization.
* The **Geomap widget** is approximately equal to the Map visualization.
* The **Table widget** is approximately equal to the Freeform Table visualization.
* The **Pie widget** is approximately equal to the Donut visualization.
* The **Bar widget** is approximately equal to the Bar visualization.

A Analysis Workspace inclui várias mais opções de visualização para apresentar os dados de uma forma melhor se ajusta às suas necessidades de relatórios. See [Visualizations in Analysis Workspace](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### Compartilhamento de projetos

Depois de terminar a adição de conteúdo a um projeto, você pode compartilhá-lo.

* Para compartilhar o projeto com seus colegas, vá para Compartilhar &gt; Compartilhar projeto. Os destinatários são outros usuários em sua organização com contas do Adobe Analytics.
* Para compartilhar seu projeto por um link, vá para Compartilhar &gt; Obter link do projeto. Observe que isso ainda requer um logon para o Adobe Analytics em sua organização.

### Exportação de projetos

Além do PDF, a Analysis Workspace oferece uma exportação de CSV.

1. Click *[!UICONTROL Share]* &gt; *[!UICONTROL Send File Now]*, which opens a modal window.
2. Especifique o tipo de arquivo e os destinatários.
3. Click [!UICONTROL Send Now].

## Relatórios personalizados

Ao criar um relatório personalizado no Google Analytics, os campos necessários são semelhantes ao fluxo de trabalho na criação de uma visualização na área de trabalho. As definições de dimensões, métricas e filtros são semelhantes entre plataformas. Na Analysis Workspace, em vez de selecionar dimensões e métricas de uma lista, as dimensões e métricas são arrastadas para uma tabela de forma livre.

### Métricas calculadas em relatórios personalizados

Relatórios personalizados são uma das poucas áreas do Google Analytics que permitem o uso de métricas calculadas. Como a Analysis Workspace opera como uma tela, as métricas calculadas funcionam retroativamente e em qualquer contexto.

Para criar uma métrica calculada:

1. Click the **+** icon near the metric list to open the Calculated Metric Builder.
2. Dê um nome à sua métrica calculada e especifique um formato.
3. Arraste os componentes da métrica para a área de definição e use as quedas entre cada componente para designar um operador.
4. Depois que a métrica calculada contiver a fórmula desejada, clique em Salvar para voltar para a área de trabalho.
5. Arraste a métrica calculada recém-definida para a área de trabalho.

   Learn more about [Calculated Metrics](../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

## Alertas personalizados

Os alertas estão disponíveis em ambas as plataformas. In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* &gt; *[!UICONTROL Alerts]*. See [Intelligent Alerts](../../components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.
