---
description: Crie uma coorte e execute um relatório de análise de coorte no Analysis Workspace.
keywords: Analysis Workspace
title: Executar um relatório de análise de coorte
feature: Visualizations
role: User, Admin
exl-id: 523e6f62-b428-454b-9460-6b06e96742c3
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 100%

---

# Configurar uma tabela de coorte

Para criar e configurar uma [!UICONTROL tabela de coorte]:

1. Adicione uma visualização de ![TextNumered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL tabela de coorte]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Defina o **[!UICONTROL Critério de inclusão]**, os **[!UICONTROL Critérios de retorno]**, o **[!UICONTROL Tipo de coorte]** e as **[!UICONTROL Configurações]** de acordo com a tabela abaixo.

   ![Configurar uma tabela de coorte](assets/cohort-configure.png)

   | Elemento | Descrição |
   |--- |--- |
   | **[!UICONTROL Critérios de inclusão]** | É possível aplicar até 10 filtros de inclusão e até 3 métricas de inclusão. A métrica especifica a qual coorte um usuário pertence. Por exemplo, se a métrica de inclusão for Pedidos, apenas usuários que fizeram um pedido durante o intervalo de tempo da análise de coorte serão incluídos na coorte inicial.<br>O operador padrão entre métricas é AND, mas você pode alterá-lo para OR. Além disso, é possível adicionar filtros numéricos a essas métricas. Por exemplo: `Sessions >= 1`.</br> |
   | **[!UICONTROL Critérios de retorno]** | É possível aplicar até 10 filtros de retorno e até 3 métricas de retorno. A métrica indica se o usuário foi retido (retenção) ou não (churn). Por exemplo, se a métrica de retorno for Visualizações de vídeo, apenas usuários que visualizaram vídeos durante períodos subsequentes (após o período em que foram adicionados a uma coorte) serão representados como retidos. Outra métrica que quantifica a retenção é Sessões. |
   | **[!UICONTROL Granularidade]** | A granularidade de tempo Dia, Semana, Mês, Trimestre ou Ano. |
   | **[!UICONTROL Tipo]** | **[!UICONTROL Retenção]** (padrão): uma coorte de **[!UICONTROL retenção]** mede o desempenho de retorno das coortes de pessoas à sua propriedade ao longo do tempo. Uma coorte de retenção é a coorte padrão e indica os comportamentos de retorno e repetição de usuários. Uma cor verde indica uma coorte de [!UICONTROL retenção] na tabela.<br>**[!UICONTROL Churn ]**: uma coorte de**[!UICONTROL  churn ]**(também chamada de “atrito” ou “fallout”) mede como as coortes de pessoas saem de sua propriedade ao longo do tempo. Churn é o oposto de retenção: `Churn = 1 - Retention`. O [!UICONTROL churn] é excelente para medir a adesão, por mostrar a frequência com que os clientes não voltam. É possível usar o churn para analisar e identificar áreas de foco, ou seja, quais filtros de coorte precisariam de atenção. Uma cor vermelha indica uma coorte de [!UICONTROL churn] na tabela (similar ao fallout na visualização de**[!UICONTROL  fluxo ]**).</br> |
   | **[!UICONTROL Configurações]** | **[!UICONTROL Cálculo contínuo]**: calcule a retenção ou churn de acordo com a coluna anterior, em vez da coluna Incluído (padrão). O [!UICONTROL Cálculo contínuo] altera o método de cálculo para seus períodos de “retorno”. O cálculo normal encontra usuários que atendem aos critérios de retorno e faziam parte do período de inclusão. Independentemente de estarem ou não na coorte do período anterior. Em vez disso, o [!UICONTROL Cálculo contínuo] encontra usuários que atendem ao critério de “retorno” e faziam parte do período anterior. Portanto, o [!UICONTROL Cálculo contínuo] filtra os usuários que continuamente atendem ao critério de “retorno” ao longo do tempo. Os critérios de [!UICONTROL retorno] são aplicados a cada período até o período selecionado. </br><br>**[!UICONTROL Tabela de latência ]**: uma [!UICONTROL tabela de latência] mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. Uma [!UICONTROL tabela de latência] é ideal para uso nas análises prévias e posteriores. Por exemplo, você deseja lançar um produto ou campanha em breve e monitorar o comportamento antes e depois do lançamento. A [!UICONTROL tabela de latência] exibe os comportamentos anterior e posterior lado a lado para visualizar o impacto direto. As células de pré-inclusão na [!UICONTROL tabela de latência] calculam os usuários que atendem aos critérios de [!UICONTROL inclusão] no período de inclusão e aos critérios de [!UICONTROL retorno] em períodos anteriores ao de inclusão. Observe que a [!UICONTROL tabela de latência] e a [!UICONTROL coorte de dimensão personalizada] não podem ser usadas juntas.</br><br>**[!UICONTROL Coorte de dimensão personalizada]**: cria coortes com base na dimensão selecionada, em vez de coortes com base no tempo (padrão). Muitos usuários desejam analisar suas coortes segundo critérios que não sejam o tempo, por isso o novo recurso de Coorte de dimensão personalizada permite ter flexibilidade para criar coortes com base nas dimensões desejadas. Use dimensões como canal de marketing, campanha, produto, página, região ou outras no Adobe Analytics para visualizar como a retenção é alterada com base nos diferentes valores destas dimensões. A definição de filtro de coorte de [!UICONTROL dimensão personalizada] aplica o item de dimensão somente como parte do período de inclusão, não como parte da definição de retorno.</br><br>Após escolher a opção [!UICONTROL Coorte de dimensão personalizada], é possível arrastar e soltar qualquer dimensão que desejar na área de destino. Adicionar dimensões permite comparar itens de dimensões similares durante o mesmo período. Por exemplo, é possível comparar o desempenho de cidades lado a lado, produtos, campanhas etc. A tabela de coorte retorna os 14 itens de dimensão principais. No entanto, é possível usar um filtro ![Filtro](/help/assets/icons/Filter.svg) para exibir somente os itens de dimensão desejados. Não é possível usar uma [!UICONTROL coorte de dimensão personalizada] com o recurso de [!UICONTROL tabela de latência].</br> |

1. Clique em **[!UICONTROL Criar]**.
1. Para reconfigurar a [!UICONTROL tabela de coorte], selecione ![Editar](/help/assets/icons/Edit.svg).

1. (Opcional) Crie um segmento a partir de uma seleção.

   Selecione uma ou mais células (adjacentes ou não adjacentes), depois clique com o botão direito do mouse em > **[!UICONTROL Criar segmento a partir da seleção]**.


1. No [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md), faça mais edições no segmento, depois clique em **[!UICONTROL Salvar]**.

   O segmento salvo está disponível para uso no painel [!UICONTROL Segmento] no [!UICONTROL Analysis Workspace].

## Configurações 

É possível definir configurações específicas para uma [!UICONTROL tabela de coorte].

1. Selecione ![Configuração](/help/assets/icons/Setting.svg) para ajustar as configurações da [!UICONTROL tabela de coorte].

   | Configuração | Descrição |
   |---|---|
   | **Mostrar somente a porcentagem** | Remove o valor do número e mostra somente a porcentagem. |
   | **Arredondar porcentagem para o número inteiro mais próximo** | Arredonda o valor percentual para o número inteiro mais próximo em vez de mostrar o valor decimal. |
   | **Mostrar linha de porcentagem média** | Insere uma nova linha na parte superior da tabela e adiciona a média dos valores dentro de cada coluna. |


>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menu de contexto da visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

