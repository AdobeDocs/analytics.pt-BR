---
description: Compara a terminologia e a as tarefas da Ad Hoc Analysis com o Analysis Workspace.
title: Comparação entre Analysis Workspace e Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '966'
ht-degree: 100%

---


# Comparação entre Analysis Workspace e Ad Hoc Analysis

>[!IMPORTANT]
>
>A Adobe está encaminhando o Ad Hoc Analysis para o fim da sua vida útil em 1º de março de 2021. [Saiba mais](https://adobe.ly/discoverworkspace)

Compara a terminologia e a as tarefas da Ad Hoc Analysis com o Analysis Workspace.

O Analysis Workspace traz muito da funcionalidade da Ad Hoc Analysis para o fluxo de trabalho do navegador. Enquanto a terminologia e os recursos continuam os mesmos dentre os produtos, há alguns termos e abordagens novas no Analysis Workspace.

Para uma comparação técnica dos principais recursos e requisitos de sistema entre estes dois produtos, clique [aqui](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/analytics-product-comparison.html?lang=pt-BR).

## Comparação da terminologia principal {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| Projeto | Workspace ou projeto |
| Workspace | Painel |
| Relatório | Tabela de forma livre |
| Tabela/Gráfico | Visualização |
| Hierarquia: Projeto > Workspace > Relatórios | Hierarquia: Projeto > Painéis > Tabelas |
| Modelos classificados, com tendência e de relatórios de totais | Visualização de tabela de forma livre |
| Modelo de fluxo | Visualização de fluxo |
| Fallout | Visualização da fallout |

## Comparação de tarefas principais {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysis Tarefa </th> 
   <th colname="col2" class="entry"> Tarefa de análise do Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adicionar dimensões e segmentos às colunas métricas </p> </td> 
   <td colname="col2"> <p>É possível adicionar itens dimensionais ou segmentos como cabeçalhos da coluna para criar facilmente exibições comparativas de métrica. <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html"  > Vídeo: Adicionar dimensões e métricas ao seu projeto no Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aplicar segmentos </p> </td> 
   <td colname="col2"> <p>Os segmentos estão disponíveis no menu de componente de Segmento e pode ser aplicado a 3 lugares no Analysis Workspace: </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">No <b>nível do painel</b>, que se aplica a diversas visualizações no painel. É semelhante a aplicar um segmento a um Workspace na Ad Hoc. </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">Como <b>linhas em uma tabela</b>. É semelhante a adicionar segmentos à seção “Linhas/Detalhamentos” do Criador de tabelas na Ad Hoc. </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">Como <b>colunas de uma tabela</b>. É semelhante a adicionar segmentos à seção “Colunas” do Criador de tabelas na Ad Hoc Analysis, ou a aplicar um segmento ao nível de relatório na Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/applying-segments-to-your-analysis-workspace-project.html?lang=pt-BR"  > Vídeo: Usar segmentos no Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/panel-level-segments.html"  > Vídeo: Aplicar segmentos a um painel</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criar segmentos temporários (“ad-hoc”) </p> </td> 
   <td colname="col2"> <p>Você pode <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >criar segmentos instantâneos (“ad-hoc”)</a> no Analysis Workspace ao arrastar os itens de dimensão até a área de soltar segmentos no topo do painel. Além disso, filtros suspensos podem ser adicionados na zona suspensa do painel para criar muitos segmentos temporários ao mesmo tempo, permitindo interações controladas do projeto. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/ad-hoc-temporary-segments.html?lang=pt-BR"  > Vídeo: Segmentos ad-hoc no Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-drop-down-filters.html"  > Vídeo: Filtros suspensos no Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escolher intervalos de data e granularidades </p> </td> 
   <td colname="col2"> <p>Os intervalos de data e granularidades estão disponíveis no menu de componente de hora e pode ser usado de 3 formas: </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">Os intervalos de datas podem ser aplicados a colunas/linhas e substituir o intervalo de data do painel selecionado. É semelhante aos intervalos de data do nível de relatório. </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">“Aplicar” aplica um intervalo de datas a todas as visualizações dentro do painel. É semelhante ao intervalo de data da Workspace na Ad Hoc Analysis. </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">“Aplicar a todos os painéis” aplica um intervalo de data a todos os painéis dentro do projeto do Workspace. É semelhante a um intervalo de data do projeto na Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=pt-BR"  > Vídeo: Trabalhar com datas no Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/creating-custom-date-ranges-in-analysis-workspace.html?lang=pt-BR"  > Vídeo: Intervalos de data personalizados</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usar o fallout e os funis de conversão </p> </td> 
   <td colname="col2"> <p>As <a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  >Visualizações de fallout</a> estão disponíveis no Analysis Workspace sob o menu de componentes Visualização. Tal como a Ad Hoc Analysis: </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">O fallout pode abranger uma visita ou um visitante, e “Todas as visitas” pode ser incluído opcionalmente. O fallout pode rapidamente ser colocado em tendência por meio do menu que é aberto ao clicar com o botão direito do mouse. </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">Os itens dimensionais podem ser conectados por um operador OR (similar aos grupos) e os eventos podem ser utilizados no funil. </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">As próxima etapas de fallthrough e fallout também podem ser renderizadas por meio do menu do botão direito do mouse. </li> 
    </ol> <p>Além disso, o fallout no Analysis Workspace permite <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  > dimensões variadas</a> nas etapas, um aprimoramento na Ad Hoc Analysis. As dimensões variadas das etapas são tratadas por um operador AND. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html?lang=pt-BR"  > Vídeo: Visualização de fallout</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/multi-dimensional-fallout.html?lang=pt-BR"  > Vídeo: Utilizar dimensões de fallout múltiplas</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/comparing-segments-in-fallout.html?lang=pt-BR"  > Vídeo: Comparar segmentos no fallout</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Examinar fluxo (caminhos) </p> </td> 
   <td colname="col2"> <p>As <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  >visualizações do Fluxo</a> estão disponíveis no Analysis Workspace sob o menu de componentes Visualização. Tal como a Ad Hoc Analysis: </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">O fluxo pode abranger uma visita ou visitante. </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">As principais estatísticas são apresentadas em termos de % de visualizações de caminho. </li> 
    </ul> <p>Além disso, o fluxo permite <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > dimensões variadas</a> e a capacidade de clicar com o botão direito do mouse e criar um segmento, uma melhoria em relação à Ad Hoc Analysis. </p> <p>Atualmente, o fluxo no Analysis Workspace <b>não</b> permite que os usuários escolham um evento bem-sucedido. </li> 
    </ul> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization.html?lang=pt-BR"  > Vídeo: Visão geral da visualização do fluxo</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow.html?lang=pt-BR"  > Vídeo: Fluxo multidimensional</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/expanding-on-flow-visualization.html?lang=pt-BR"  > Vídeo: Criar segmentos do Fluxo</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Executar detalhamentos infinitos </p> </td> 
   <td colname="col2"> <p>O Analysis Workspace permite detalhar em níveis infinitos no navegador. Os segmentos e as dimensões podem estar misturados. Vários itens de dimensão podem ser detalhados de uma vez, selecionando vários e arrastando-os para uma dimensão de detalhamento. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/dimension-breakdown-by-position.html"  > Vídeo: Detalhamentos aprimorados</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Colocar dados em tendência rapidamente </p> </td> 
   <td colname="col2"> <p>Os dados podem ser visualizados rapidamente ao clicar no ícone de gráfico na linha do relatório. Além disso estas visualizações rápidas serão vinculadas à tabela de origem tornando possível clicar de um valor ao outro na tabela e veja a atualização do gráfico automaticamente. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/dimension-graph-live-linking.html?lang=pt-BR"  > Vídeo: Vinculação online do gráfico de dimensão</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Selecionar os conjuntos de relatórios </p> </td> 
   <td colname="col2"> <p>Vários conjuntos de relatórios podem ser adicionados a um único projeto no Analysis Workspace.  </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace.html?lang=pt-BR"  > Vídeo: Vários conjuntos de relatórios no Workspace</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p>O <a href="/help/analyze/analysis-workspace/attribution/overview.md"  >Attribution IQ</a> no Analysis Workspace permite adicionar vários tipos novos de modelos de atribuição a Tabelas de forma livre, Visualizações e Métricas calculadas. Ele inclui mais de 10 modelos algorítmicos e baseados em regras. </p>  <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables.html?lang=pt-BR"  > Vídeo: Attribution IQ em tabelas de forma livre</a> </p> </td> 
  </tr>  
 </tbody> 
</table>

