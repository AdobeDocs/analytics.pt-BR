---
title: Preferências do usuário
description: Saiba como definir preferências gerais e de projeto para usuários.
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
source-git-commit: 6cec1085093404235e29319db984d4389c68c31e
workflow-type: tm+mt
source-wordcount: '3461'
ht-degree: 79%

---

# Preferências do usuário

Você pode gerenciar as configurações do Analysis Workspace e seus componentes relacionados para todos os novos projetos ou painéis criados por você. Os projetos e painéis existentes não são afetados.


>[!BEGINSHADEBOX]

Confira ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gerenciar preferências](https://video.tv.adobe.com/v/3429987/?quality=12&learn=on&captions=por_br){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

## Atualizar preferências

Você pode atualizar suas preferências das seguintes maneiras:

- Selecione ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Editar preferências]** na interface principal do espaço de trabalho.
- Selecione **[!UICONTROL Projeto]** > **[!UICONTROL Preferências do usuário]** no menu ao trabalhar em um projeto do espaço de trabalho.
- Selecione **[!UICONTROL Componentes]** > **[!UICONTROL Preferências]** na barra de menu superior no Customer Journey Analytics (disponível somente para admins de produtos).

## Configurar preferências

Você pode configurar as seguintes preferências:


## Preferências gerais

Você pode personalizar as preferências gerais de todos os novos projetos criados no Analysis Workspace. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

| Preferência | Opções |
| --- | --- |
| Landing page | Escolha qual página é exibida como a página padrão ao acessar o Adobe Analytics: <ul><li>Lista de projetos (padrão)</li><li>Projeto em branco</li><li>Projeto específico selecionado em uma lista</li></ul> |
| Mostrar dicas | Exibe dicas em uma caixa azul na área inferior direita do Analysis Workspace. <p>Essa opção está ativada por padrão.</p> |
| Componentes exibidos em grupos do painel esquerdo | Escolha quantos de cada componente serão exibidos no menu Componentes no painel à esquerda. <p>Se você escolher 0, o componente não estará mais acessível no painel esquerdo dos espaços de trabalho.</p><p>Por padrão, 5 componentes são exibidos para cada um dos seguintes itens:</p> <ul><li>Dimensões</li><li>Métricas</li><li>Filtros</li><li>Intervalos de datas</li></ul> <p>Para obter mais informações sobre Componentes no Analysis Workspace, consulte [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).</p> |

## Preferências da empresa {#company-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Permitir compartilhamento apenas com usuários do espaço de trabalho"
>abstract="Quando habilitada, a opção **[!UICONTROL Compartilhar com qualquer pessoa]** não fica mais disponível para usuários que compartilham um projeto do Analysis Workspace. As pessoas que anteriormente receberam acesso a um projeto por meio dessa opção de compartilhamento não podem mais acessar o projeto."

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Exige autenticação da Experience Cloud"
>abstract="Quando habilitado, as pessoas que recebem acesso a um projeto da opção **[!UICONTROL Compartilhar com qualquer pessoa]** no Analysis Workspace devem se autenticar usando suas credenciais do Experience Cloud."

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="Permitir comentários em projetos"
>abstract="Quando habilitada, uma área de comentários fica disponível no painel direito de cada projeto no Analysis Workspace."


Você pode atualizar as preferências da empresa que se aplicam a todos os usuários e projetos em sua organização. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Guia Modelos** | | |
|  | Ocultar guia de modelos | Oculta a guia Modelos para todos os usuários em sua organização. |
| **Compartilhamento de projeto** | | |
| | Permitir compartilhamento apenas com usuários do espaço de trabalho | Quando esta opção está habilitada, os usuários da sua organização não podem ver a opção **[!UICONTROL Compartilhar com qualquer pessoa]** no menu **[!UICONTROL Compartilhar]**. Os usuários não podem compartilhar projetos com pessoas que não têm uma conta da Analysis Workspace em sua organização, conforme descrito em [Compartilhar um projeto com qualquer pessoa (sem logon necessário)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).<br/>Essa opção é desabilitada por padrão para todas as organizações, exceto para clientes que possuem o Healthcare Shield licenciado. <p>Considere o seguinte ao habilitar ou desabilitar essa opção:<ul><li>Ao habilitá-la, as pessoas que anteriormente receberam acesso a um projeto por meio da opção **[!UICONTROL Compartilhar com qualquer pessoa]** não poderão mais acessar o projeto.</li><li>Se esta opção for habilitada (para permitir o compartilhamento somente com usuários do espaço de trabalho) e depois desabilitada (para permitir o compartilhamento com qualquer pessoa), as pessoas que receberam acesso a um projeto anteriormente por meio da opção **[!UICONTROL Compartilhar com qualquer pessoa]** não recuperarão automaticamente o acesso ao projeto. Nesse caso, o usuário que compartilhou o projeto deve habilitar a opção [!UICONTROL **O link está ativo**], disponível ao compartilhar um projeto com qualquer **([!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com qualquer um]**), conforme descrito em [Compartilhar um projeto com qualquer pessoa (sem logon necessário)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>**Para clientes com uma licença do Healthcare Shield:** essa opção está habilitada por padrão e não pode ser desabilitada. Antes de desabilitar esta opção para que os usuários possam usar a opção **[!UICONTROL Compartilhar com qualquer pessoa]**, você primeiro precisa adicionar a permissão [!UICONTROL Compartilhar links de projeto com qualquer pessoa] (localizada em [!UICONTROL Ferramentas de relatórios]) no Adobe Admin Console. Após adicionar a permissão, você poderá desabilitar essa opção e, em seguida, aceitar o aviso legal resultante. Para obter informações sobre como adicionar uma permissão no Admin Console, consulte [Gerenciar permissões de produto no Admin Console](https://helpx.adobe.com/br/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Exige autenticação da Experience Cloud | Quando esta opção está habilitada, as pessoas que recebem acesso a um projeto da opção **[!UICONTROL Compartilhar com qualquer pessoa]** no Analysis Workspace devem se autenticar usando suas credenciais do Experience Cloud.<p>Após habilitar essa opção, sempre que um usuário compartilhar um projeto usando **[!UICONTROL Compartilhar com qualquer pessoa]**, a opção **[!UICONTROL Exigir autenticação da Experience Cloud]** será habilitada na caixa de diálogo de compartilhamento e não poderá ser desabilitada pelo usuário que está compartilhando o projeto. Para obter informações sobre como os usuários podem compartilhar projetos com qualquer pessoa, consulte [Compartilhar um projeto com qualquer pessoa (sem logon necessário)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link). <p> <p>Considere o seguinte ao habilitar essa opção: <ul><li>Ao habilitar esta opção, todos os projetos que foram compartilhados anteriormente com a opção **[!UICONTROL Compartilhar com qualquer pessoa]** sem habilitar [!UICONTROL Exigir autenticação da Experience Cloud] serão desativados.<p>Se esta opção for habilitada (para exigir autenticação da Experience Cloud) e depois desabilitada (para permitir que qualquer pessoa com o link acesse o projeto), as pessoas que receberam acesso a um projeto anteriormente por meio da opção **[!UICONTROL Compartilhar com qualquer pessoa]** não recuperarão automaticamente o acesso ao projeto. Nesse caso, o usuário que compartilhou o projeto deve habilitar a opção [!UICONTROL O link está ativo], disponível ao compartilhar um projeto com qualquer um **([!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com qualquer um]** > **[!UICONTROL O link está ativo]**), conforme descrito em [Compartilhar um projeto com qualquer um (sem logon necessário)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>Essa opção só estará disponível se o recurso de logon único (SSO) estiver implementado em sua organização. Para obter informações sobre como admins de sistema podem habilitar o SSO na sua organização, consulte [Configuração de identidade e logon único](https://helpx.adobe.com/br/enterprise/using/set-up-identity.html).</p><p>Se o SSO estiver configurado na sua organização, verifique se há algum tipo de criação automática de contas implementado no console. Normalmente, isso é configurado por um(a) admin de sistema, conforme descrito em [Habilitar criação automática de conta](https://helpx.adobe.com/br/enterprise/using/automatic-account-creation.html).</li><li>Se sua organização tiver uma licença do Healthcare Shield, essa opção será habilitada por padrão e não poderá ser desabilitada.</li></ul> |

{style="table-layout:auto"}

## Preferências de projetos e análises {#project-analyses-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Paleta categórica"
>abstract="Aplicado a muitas visualizações no Analysis Workspace e em análises guiadas. Cada cor representa um valor categórico diferente."

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Paleta divergente"
>abstract="Aplicado à tabela de coorte no Analysis Workspace e em análises guiadas de crescimento de usuários. Esta paleta possui um significado numérico com dois extremos e uma linha de base no meio."

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Paleta sequencial"
>abstract="Aplicado à análise guiada de tendências de frequência (barras empilhadas). Esta paleta possui um significado numérico que vai do claro ao escuro."

Você pode personalizar as preferências do projeto para todos os novos projetos criados no Analysis Workspace. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

Algumas dessas mesmas preferências também podem ser personalizadas para projetos individuais, conforme descrito na [Visão geral dos projetos](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

Clique nos títulos de preferência vinculados para obter mais informações e contexto sobre cada preferência.

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Exibir** | | |
|  | [Densidade da exibição](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | Escolha quanto conteúdo será exibido na tela, reduzindo o preenchimento vertical do painel à esquerda, em tabelas de forma livre e de coorte. <ul><li>Compacto</li><li>Confortável</li><li>Expandido (padrão)</li></ul> |
| | [Paleta de cores](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) | Escolha as paletas de cores de visualização usadas no Analysis Workspace.<ul><li>**Paleta categórica**: aplicada a muitas visualizações no Analysis Workspace. Cada cor representa um valor categórico distinto. Escolha entre as opções fornecidas pela Adobe ou insira uma paleta personalizada definida por valores hexadecimais delimitados por vírgulas.</li><li>**Paleta divergente**: aplicada à tabela de coorte no Analysis Workspace. Esta paleta contém um significado numérico com dois extremos e uma linha de base no meio.</li><li>**Paleta sequencial**: aplicada à análise guiada de Tendências de frequência (barra empilhada). Esta paleta contém um significado numérico do claro para o escuro.</li></ul> |
| **Dados** | | |
|  | [Conjunto de relatórios](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/panels) | Escolha de onde as tabelas e as visualizações derivam seus dados. <ul><li>Mais recente (padrão)</li><li>Conjunto de relatórios específico selecionado em uma lista</li></ul> |
|  | [Calendário](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/panels) | Selecione de uma lista de: <ul><li>Intervalos fornecidos pela Adobe (o padrão é Este mês)</li><li>Intervalos definidos pelo cliente</li></ul> |
|  | [Tipo de painel](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/panels) | <ul><li>Forma livre (padrão)</li><li>Em branco</li><li>Insights rápidos</li></ul> |
|  | Contar instâncias repetidas | Especifica se as instâncias repetidas devem ser contadas nos relatórios. Por exemplo, essa configuração (quando ativada) trata várias exibições de página consecutivas para a mesma página como várias exibições de página. Com essa opção desativada, eles contam como uma única visualização de página. <p>**Observação:** essa configuração afeta apenas determinadas métricas (como Visitas de página única) e não se aplica a visualizações de Fluxo ou Fallout.</p> |
|  | Formato de número | <ul><li>1.000,00 (padrão)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Caractere separador do CSV | <ul><li>Vírgula (padrão)</li><li>Ponto e vírgula</li><li>Dois-pontos</li><li>Estágio</li><li>Ponto</li><li>Espaço</li><li>Tabulação</li></ul> |
|  | Mostrar anotações | Escolha se as anotações estão visíveis em seus projetos. Para obter mais informações sobre anotações, consulte [Visão geral de anotações](/help/analyze/analysis-workspace/components/annotations/overview.md). |

## Preferências da tabela de forma livre {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Mostrar anomalias"
>abstract="Selecionar **[!UICONTROL Mostrar anomalias]** executa automaticamente a detecção de anomalias na primeira coluna de métrica adicionada a uma visualização de tabela de forma livre de série temporal."

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Mostrar previsão"
>abstract="Selecionar **[!UICONTROL Mostrar previsão]** prevê automaticamente a primeira coluna de métrica adicionada a uma visualização de tabela de forma livre de série temporal."


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Métrica de tabela padrão"
>abstract="Selecione a métrica padrão para usar em tabelas de forma livre. Se a visualização de dados selecionada não contiver a métrica padrão selecionada, a tabela alternará automaticamente para outra métrica primária."


Você pode personalizar as preferências da tabela de forma livre para todos os novos projetos criados no Analysis Workspace. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

Algumas dessas mesmas preferências também podem ser personalizadas para tabelas individuais.

Clique nos títulos da seção vinculada para obter mais informações e contexto sobre as preferências disponíveis.

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Tabela** | | |
| | Tipo de tabela | <ul><li>Forma livre</li><li>Construtor de tabelas</li></ul> |
| | Métrica de tabela padrão | <ul><li>Ocorrências</li><li>Visitantes únicos</li><li>Visitas</li></ul> |
| | Dimensão padrão da tabela | Escolha de Minuto, Hora, Dia, Semana, Mês, Trimestre ou Ano. |
| | Alinhar datas | Selecione essa opção para alinhar as datas de cada coluna para que todas iniciem na mesma linha. |
| **[Coluna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Quebrar linha do texto do cabeçalho | Permite a quebra de linha do texto de cabeçalho em tabelas de forma livre para torná-lo mais legível e facilitar o compartilhamento de tabelas. Essa quebra de linha é útil para renderização de PDF e para métricas com nomes longos. Ativado por padrão. |
| | Exibir totais | Normalmente este total é uma parte do [!UICONTROL Total geral] ou igual a ele. Ele reflete todos os filtros de tabela aplicados na tabela de forma livre, incluindo a opção [!UICONTROL Não incluir]. |
| | Mostrar totais gerais | Esse total representa todas as ocorrências que foram coletadas, às vezes chamadas de *total do conjunto de relatórios*. Quando um segmento é aplicado no nível do painel ou na tabela de forma livre, esse total é ajustado para refletir todas as ocorrências que correspondem aos critérios do segmento. O total geral não é compatível com tabelas e detalhamentos com [linhas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Mostrar minigráfico | Mostrar ou ocultar gráficos de linha na parte inferior do gráfico. Quando oculta, a legenda será alterada para não mais fazer referência visual às linhas. |
| | Número | Determina se uma célula exibe ou oculta o valor numérico para a métrica. Por exemplo, se a métrica for exibições de página, o valor numérico será o número de exibições de página para o item da linha. |
| | Porcentagem | Determina se uma célula exibe ou oculta o valor percentual para a métrica. Por exemplo, se a métrica for “visualizações de página”, o valor percentual será o número de visualizações de página do item da linha dividido pelo total de visualizações de página da coluna.  Observação: para ser mais preciso: porcentagens maiores que 100% são exibidas. O limite superior é movido para 1.000% para garantir que as colunas possam aumentar em largura. |
| | Mostrar anomalias | Determina se a detecção de anomalias é executada nos valores desta coluna. |
| | Interpretar o zero como valor inexistente | Para células com valor 0, determina se exibirá um 0 ou uma célula em branco. Isso é útil para observar dados diários de um mês que ainda não tenha terminado.  Em vez de mostrar 0 para as datas futuras, pode-se exibir células em branco. Os gráficos respeitam essa configuração também (ou seja, não mostram uma linha ou barra com valores 0 quando essa configuração está marcada). |
| | Histórico | Determina se uma célula exibe ou oculta todas as formatações de célula, incluindo o gráfico de barras e a formatação condicional <ul><li>Gráfico de barras</li> Um gráfico de barras horizontal que representa o valor da célula relativo ao total da coluna. <li>Formatação condicional</li>Para obter mais informações sobre formatação condicional, consulte “Formatação condicional” em [Configurações de coluna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Visualização da célula | Uma visualização de como cada célula é exibida com as opções de formatação atualmente selecionadas aplicadas. |
| **[Linha](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Detalhamento por posição | Selecione essa opção se desejar que o detalhamento permaneça com a posição do item em vez do próprio item. Para obter mais informações sobre detalhamentos, consulte [Analisar dimensões](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md). |
| | Cálculo percentual | <ul><li>Coluna</li><li>Linha</li></ul> |
| | Totais de coluna (somente linhas estáticas) | <ul><li>Exibir soma das linhas: mostra a soma dos itens de linha individuais </li><li>Exibir total geral: mostra a soma de linhas desduplicadas.</li></ul> |

## Preferências de visualizações

É possível atualizar as preferências de visualização para todos os novos projetos criados no Analysis Workspace. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

Algumas dessas mesmas preferências também podem ser personalizadas para visualizações individuais.

Clique nos títulos da seção vinculada para obter mais informações e contexto sobre as preferências disponíveis.

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Padrões gerais** | | |
| | Porcentagens | Exibe valores em porcentagens para todas as visualizações. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para todas as visualizações. |
| | Limite máximo de itens | Reduz o número de itens no eixo X para todas as visualizações. Isso pode ser útil se você tiver um conjunto de dados grande. |
| | Exibir eixo duplo (quando aplicável) | Aplicável somente se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direita (para a outra métrica). Essa configuração é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Normalização (quando aplicável) | Força as métricas em proporções iguais. Essa configuração é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Ancorar o eixo Y em zero | Se todos os valores plotados no gráfico estiverem consideravelmente acima de zero, o padrão do gráfico tornará a parte inferior do eixo Y DIFERENTE DE ZERO. Se você marcar essa caixa, o eixo y será forçado a zero (e ele desenha novamente o gráfico). |
| | Permitir que as anomalias dimensionem o eixo Y | Se você tiver várias métricas em um gráfico, é necessário passar o mouse sobre cada anomalia para ver a faixa de confiança para essa métrica. Para tornar a visualização mais legível, o intervalo de confiança da Detecção de anomalias não dimensiona automaticamente o eixo y. Essa opção permite que o intervalo de confiança dimensione a visualização. <p>Para obter mais informações, consulte [Exibir anomalias no Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| **[Linha](/help/analyze/analysis-workspace/visualizations/line.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações de linha. |
| | Legenda visível | Ocultar o texto detalhado da legenda para a visualização de Linha. |
| | Limite máximo de itens | Reduz o número de itens no eixo X na visualização de linha. Essa configuração é útil se você tiver um conjunto de dados grande. |
| | Exibir eixo duplo (quando aplicável) | Aplicável somente se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direita (para a outra métrica). Essa configuração é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Normalização (quando aplicável) | Força as métricas em proporções iguais. Essa configuração é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Mostrar eixo X | Exibe o eixo x no gráfico de linha. |
| | Mostrar eixo Y | Exibe o eixo y no gráfico de linha. |
| | Âncora do eixo Y | Se todos os valores plotados no gráfico estiverem consideravelmente acima de zero, o padrão do gráfico tornará a parte inferior do eixo Y DIFERENTE DE ZERO. Se você marcar essa caixa, o eixo y será forçado a zero (e ele desenha novamente o gráfico). |
| | Mostrar mín. | Sobrepõe um rótulo de valor mínimo para destacar rapidamente os vales em uma métrica. Observação: os valores mín. são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores em uma dimensão. |
| | Mostrar máx. | Sobrepõe um rótulo de valor máximo para destacar rapidamente os picos em uma métrica. Observação: os valores máx. são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores em uma dimensão. |
| | Mostrar linha de tendência | Mostrar uma regressão ou uma linha de tendência média móvel para a sua série de linhas. As linhas de tendência ajudam a descrever um padrão mais claro nos dados. |
| **[Coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Granularidade | Para visualizações de tendências, você pode alterar a granularidade de tempo (dia, semana, mês, trimestre ou ano). Essa alteração também se aplica à tabela de fontes de dados. |
| | Mostrar somente a porcentagem | Remove o valor do número e mostra somente a porcentagem. |
| | Arredondar porcentagem ao inteiro mais próximo | Arredonda o valor percentual para o inteiro mais próximo em vez de mostrar o valor decimal. |
| | Mostrar linha de porcentagem média | Insere uma nova linha na parte superior da tabela e adiciona a média para os valores dentro de cada coluna. |
| | Visualização de coorte | Uma visualização de como a paleta de cores aparece na visualização de coorte. |
| | Paleta de coorte | A paleta de cores usada na visualização de coorte. |
| **[Gráficos de combinação](/help/analyze/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Mostrar eixo X | Exibe o eixo x no gráfico de combinação. |
| | Mostrar eixo Y | Exibe o eixo y no gráfico de combinação. |
| | Exibir barras nas linhas | Mostrar barras em linhas nos gráficos de combinação. |
| **[Resumo da métrica principal](/help/analyze/analysis-workspace/visualizations/key-metric.md)** | | |
| | Tipo de exibição de resumo | <ul><li>Enfatizar a variação percentual</li><li>Enfatizar o valor do número</li></ul> |
| | Mostrar linhas cintilantes | Mostrar ou ocultar gráficos de linha na parte inferior do gráfico. Quando oculta, a legenda será alterada para não mais fazer referência visual às linhas. |
| | Mostrar máximo e mínimo em sparklines | Mostrar valores mínimos e máximos em gráficos de linha primários e de comparação. |
| | Mostrar comparação | Mostrar dados de comparação. Quando ocultos, o gráfico de linhas de comparação e os objetos de alteração de resumo não aparecem na visualização. |
| | Opções de valor numérico | Na seção [!UICONTROL **Resumo das métricas principais**] <ul><li>Mostrar variação percentual</li><li>Mostrar diferença bruta</li>Diferença bruta entre o valor total da métrica no intervalo de datas principal e o intervalo de datas secundário</ul> |
| **[Fallout](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Container | Alternar entre Visita e Visitante para analisar a definição do caminho do visitante. O padrão é Visitante. Essas configurações ajudam você a entender o envolvimento no nível dos visitantes (ao longo das visitas) ou restringir a análise a uma só visita. <p>As opções disponíveis são as seguintes:</p> <ul><li>Visita</li><li>Visitante</li></ul> |
| **[Fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Contêiner | Na seção [!UICONTROL **Fluxo**] <ul><li>Visita</li><li>Visitante</li></ul> |
| | Rótulos de quebra de linha | Normalmente, os rótulos nos Elementos de fluxo são truncados para não poluir visualmente a tela, mas é possível tornar todos os rótulos visíveis ao selecionar esta caixa. Padrão = desmarcado. |
| | Incluir instâncias repetidas | As visualizações de fluxo são baseadas em instâncias de uma dimensão. Essa configuração oferece a opção de incluir ou excluir instâncias repetidas, por exemplo, recarregamentos de página. No entanto, as repetições não podem ser removidas das Visualizações de fluxo que incluem dimensões com vários valores, como listVars, listProps, s.product, eVars de merchandising etc. Padrão = desmarcado. |
| | Mostrar dicas de ferramentas | Determina se as dicas de ferramenta, que contêm dados de nó, são exibidas quando você passa o mouse sobre nós individuais em uma visualização de fluxo. |
| | Número de colunas | Determina quantas colunas você deseja incluir no diagrama de Fluxo. |
| | Itens expandidos por coluna | Quantos itens você deseja em cada coluna. |
| **Gráficos empilhados** | | |
| | 100% empilhada | Essa configuração de visualizações de área empilhada, barra empilhada ou barra horizontal empilhada transforma o gráfico em uma visualização “100% empilhada”.  <p>Para obter mais informações, consulte [Barra e barras empilhadas](/help/analyze/analysis-workspace/visualizations/bar.md).</p> |
| **[Histograma](/help/analyze/analysis-workspace/visualizations/histogram.md)** | | |
| | Número de grupos | Escolha o número de intervalos de dados (grupos) na visualização. O número máximo de grupos é 50. <p>Para obter mais informações, consulte [Histograma](/help/analyze/analysis-workspace/visualizations/histogram.md).</p> |
| | Método de contagem | Escolha entre as seguintes opções: <ul><li>Ocorrência</li><li>Visita</li><li>Visitante</li></ul> <p>Por exemplo, quando usado com exibições de página, você pode escolher exibições de página por visitante, exibições de página por visita ou exibições de página por ocorrência. Para ocorrências, “Ocorrências” é usada como a métrica do eixo “y” na tabela de forma livre.</p> |
| **[Mapa](/help/analyze/analysis-workspace/visualizations/map-visualization.md)** | | |
| | Dimensão da plotagem | <ul><li>Latitude/longitude móvel</li><li>Dimensão geográfica</li></ul> |
| | Tipo de mapa | <ul><li>Propagações</li><li>Mapa de calor</li></ul> |
| | Tema de cores | Escolha entre Coral, Vermelhos, Verdes, Azuis, Mapa de calor e Positivo/Negativo. |
| | Estilo do mapa | Escolha entre Básico, Ruas, Brilhante, Claro, Escuro e Satélite. |
| **[Alteração de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valor | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Mudança percentual</li><li>Diferença bruta</li></ul> |
| | Porcentagens | Exibe valores em porcentagens para as visualizações do Resumo de alterações. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização Resumo da alteração. |
| | Abreviar valor | Quando selecionado, especifique o número de casas decimais. |
| **[Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações do Número de resumo. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização Número de resumo. |
| | Valor de resumo por | Escolha entre Máx., Mín., Média, Mediana e Soma. |
| | Abreviar valor | Quando selecionado, especifique o número de casas decimais. |
| **[Mapas de árvore](/help/analyze/analysis-workspace/visualizations/treemap.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações do Mapa de árvore. |
| | Limite máximo de itens | Reduz o número de itens no eixo X na visualização do Mapa de árvore. Isso pode ser útil se você tiver um conjunto de dados grande. |
| **[Venn](/help/analyze/analysis-workspace/visualizations/venn.md)** | | |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização de Venn. |
| **[Dispersão](/help/analyze/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações de dispersão. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização de dispersão. |
| | Limite máximo de itens | Reduz o número de itens no eixo X na visualização de dispersão. Isso pode ser útil se você tiver um conjunto de dados grande. |
| | Ancorar o eixo Y em zero | Se todos os valores plotados no gráfico estiverem consideravelmente acima de zero, o padrão do gráfico tornará a parte inferior do eixo Y DIFERENTE DE ZERO. Se você marcar essa caixa, o eixo y será forçado a zero (e ele desenha novamente o gráfico). |

## Restaurar preferências padrão

Você pode restaurar todas as preferências do usuário para os padrões do sistema. Esta opção não afeta as preferências do administrador na guia **[!UICONTROL Empresa]**. Esta ação não pode ser desfeita.

1. No Adobe Analytics, selecione [!UICONTROL **Componentes**] **>** [!UICONTROL **Preferências**] no menu superior. Ou selecione **[!UICONTROL Projeto]** > **[!UICONTROL Configurações de usuário]** no menu do espaço de trabalho.

1. No canto superior direito, selecione **[!UICONTROL Restaurar padrões]**.

1. Selecione **[!UICONTROL Restaurar padrões]** em **[!UICONTROL Restaurar configurações padrão do sistema]**.

## [!UICONTROL Tema escuro]

Se preferir ter um fundo escuro para a interface de usuário do Customer Journey Analytics, é possível alternar para [!UICONTROL Tema escuro].

1. Clique no ícone de usuário da Experience Cloud na parte superior direita.

   ![tema escuro](assets/dark-theme.png)

1. Habilite o **[!UICONTROL Tema escuro]**.

