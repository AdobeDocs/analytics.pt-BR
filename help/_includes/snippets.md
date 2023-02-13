---
source-git-commit: d8442f1ec8f35fbcda98b35070936677813ce330
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 16%

---
# Trechos

## Anúncio do fim da vida útil do Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>Leia mais sobre o [Anúncio do fim da vida útil](https://express.adobe.com/page/6WnF8JK6IRDhf/) do Reports &amp; Analytics.

## Critérios do filtro do Dicionário de dados {#dd-filter-criteria}

1. (Opcional) Selecione o **Filtro** ícone ![Ícone do Filtro do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/assets/data-dictionary-filter-icon.png)e, em seguida, selecione qualquer uma das seguintes opções de filtro para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são Dimension. (Essa opção também está disponível na variável [!UICONTROL **Filtros rápidos**] ao acessar o Dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são Métricas. (Essa opção também está disponível na variável [!UICONTROL **Filtros rápidos**] ao acessar o Dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Segmentos**] | Mostrar somente componentes que são Segmentos. (Essa opção também está disponível na variável [!UICONTROL **Filtros rápidos**] ao acessar o Dicionário de dados pela primeira vez.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na variável [!UICONTROL **Filtros rápidos**] ao acessar o Dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores do . |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não estão marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem análise e aprovação. Essa opção está disponível somente para administradores do . |
   | [!UICONTROL **Descrição ausente**] | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição . Essa opção está disponível somente para administradores do . |
   | [!UICONTROL **Mostrar duplicatas**] | Mostrar somente componentes que têm o mesmo rótulo ou a mesma descrição de outro componente no Conjunto de relatórios selecionado. Rótulos ou descrições devem ser correspondências exatas para serem mostradas como duplicatas. Essa opção está disponível somente para administradores do . |
   | [!UICONTROL **Sem dados recentes**] | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores do . |
   | [!UICONTROL **Criado pelo Adobe**] <!-- I don't see this option--> | Mostrar somente componentes que foram criados pelo Adobe. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style=&quot;table-layout:auto&quot;}

## Informações sobre o componente do Dicionário de dados {#dd-component-information}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Aprovado**] | Indica que o componente foi revisado e aprovado pelo administrador. Os administradores veem um [!UICONTROL **Aprovação necessária**] para componentes não aprovados. Selecionar essa opção marca como Aprovado. |
| [!UICONTROL **Descrição**] | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente usado com**] | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Segmento e Intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados. <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Semelhante a**] | <p>Mostra componentes com rótulos semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Segmento e Intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Todos os componentes duplicados em seu conjunto de relatórios serão exibidos aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md). <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
| [!UICONTROL **Tipo de componente**] | Lista o tipo de componente, seja um Dimension, uma métrica, um segmento ou um intervalo de datas. |
| [!UICONTROL **Criado por**] | Exibe o nome do usuário que criou o componente. |
| [!UICONTROL **Visualizar**] | Mostra uma visualização de como o componente é exibido no Analysis Workspace. |
| [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida durante a visualização de Segmentos, Métricas calculadas e Intervalos de datas. <!--for CJA, it is displayed for all components--> |

{style=&quot;table-layout:auto&quot;}

## Teste limitado da fase de lançamento {#release-limited-testing}

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está na fase Teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Adobe Analytics](/help/release-notes/releases.md).

## Seção Teste limitado da fase de lançamento {#release-limited-testing-section}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção está na fase Teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Adobe Analytics](/help/release-notes/releases.md).

