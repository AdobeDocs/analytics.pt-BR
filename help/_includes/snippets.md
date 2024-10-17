---
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 89%

---
# Trechos

## Report Builder herdado {#legacy-arb}

>[!IMPORTANT]
>
>Um novo e simplificado [Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) foi lançado em 16 de outubro de 2024. Ele é compatível com Mac, Windows e navegadores da Web.
>Esta versão herdada do complemento de Report Builder ainda funciona. Você pode [converter suas pastas de trabalho herdadas](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks) para o novo Report Builder.

## Anúncio do fim da vida útil do Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>A partir de **17 de janeiro de 2024**, o Adobe descontinuou o Reports &amp; Analytics e os relatórios e recursos que o acompanham. Naquele momento, o Reports &amp; Analytics e todos os seus relatórios e agendamentos pararam de funcionar. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o Reports &amp; Analytics não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do Reports &amp; Analytics está disponível no Analysis Workspace. Para obter informações sobre como usar relatórios no Analysis Workspace, consulte [Usar relatórios pré-criados](/help/analyze/analysis-workspace/reports/use-reports.md).
> 
>Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do Reports &amp; Analytics foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. Este aviso explica o processo do fim da vida útil.
>
>Leia mais sobre o [Anúncio do fim da vida útil](https://www.adobe.com/go/analytics_rnaeol_br) do Reports &amp; Analytics.

## Critérios de filtro do dicionário de dados {#dd-filter-criteria}

1. (Opcional) Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e, em seguida, selecione qualquer uma das seguintes opções para filtrar a lista de componentes:

| Opção | Função |
|---------|----------|
| [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
| [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
| [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
| [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
| [!UICONTROL **Segmentos**] | Mostrar somente componentes que são segmentos. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) <!--this is Filters in Customer Journey Analytics--> |
| [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
| [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
| [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |
| [!UICONTROL **Descrição ausente**] | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
| [!UICONTROL **Mostrar duplicatas**] | <p>Mostrar somente componentes que tenham o mesmo nome ou a mesma definição de outro componente no conjunto de relatórios selecionado. Nomes ou definições precisam ser correspondências exatas para serem mostradas como duplicatas.</p><p>Essa opção está disponível somente para administradores.</p><p>**OBSERVAÇÃO:** para definições, isso inclui os componentes criados por você assim como os fornecidos pela Adobe. Para os nomes, isso atualmente inclui apenas os componentes criados por você e não os fornecidos pela Adobe. A exibição de nomes duplicados para componentes fornecidos pela Adobe será adicionada em uma versão posterior.</p> |
| [!UICONTROL **Sem dados recentes**] | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
| [!UICONTROL **Criado por Adobe**] <!-- I don't see this option--> | Mostrar somente componentes que foram criados pela Adobe. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

{style="table-layout:auto"}

## Informações sobre o componente do dicionário de dados {#dd-component-information}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Aprovado**] | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Depois que um componente é aprovado, os administradores podem remover a aprovação clicando no botão **Aprovado**.</p> |
| [!UICONTROL **Aprovação necessária**] | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Aprovar**]. Selecionar essa opção marca o componente como “Aprovado” para os usuários.</p> |
| [!UICONTROL **Descrição**] | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente usado com**] | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não estão sendo compartilhados com você.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Semelhante a**] | <p>Mostra componentes com nomes semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Qualquer componente duplicado em seu conjunto de relatórios também será exibido aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não estão sendo compartilhados com você.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBSERVAÇÃO:** atualmente, a seção **Semelhante a** inclui apenas componentes criados por você e não os fornecidos pela Adobe. Os componentes fornecidos pela Adobe serão adicionados em uma versão posterior.</p> |
| [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
| [!UICONTROL **Tipo de componente**] | Lista o tipo de componente, seja uma dimensão, uma métrica, um segmento ou um intervalo de datas. |
| [!UICONTROL **Criado por**] | Mostra o nome do usuário que criou o componente. |
| [!UICONTROL **Pré-visualizar**] | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
| [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida durante a visualização de segmentos, métricas calculadas e intervalos de datas. |

{style="table-layout:auto"}

## Opções de classificação de componentes {#components-sort-options}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Recomendado**] | Classifica componentes com aqueles recomendados no topo da lista. Os componentes usados com mais frequência e mais recentemente por você ou outras pessoas em sua organização são mostrados em uma posição superior na lista. |
| [!UICONTROL **Ordem alfabética**] | Classifica os componentes em ordem alfabética. |
| [!UICONTROL **Categórico**] | Classifica componentes de acordo com o tipo de componente (dimensão, métrica, segmento, intervalo de datas). |

{style="table-layout:auto"}

## Fase de teste limitado da versão {#release-limited-testing}

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Adobe Analytics](/help/release-notes/releases.md).

## Seção Fase de teste limitado da versão {#release-limited-testing-section}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Adobe Analytics](/help/release-notes/releases.md).


## Aviso de isenção de responsabilidade do plug-in {#plug-in}

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com a Equipe de conta da Adobe de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.


## Disponível somente para clientes existentes {#available-existing-customers}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção só está disponível para clientes existentes que já têm uma licença para a funcionalidade. A funcionalidade não é mais oferecida como um complemento para clientes existentes ou novos.
>
