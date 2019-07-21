---
description: As configurações de linha variam de acordo como qual componente foi arrastado para a tabela.
seo-description: As configurações de linha variam de acordo como qual componente foi arrastado para a tabela.
seo-title: Configurações de linha
title: Configurações de linha
uuid: f 30 c 31 d 5-1 fd 4-4 b 93-94 c 3-ca 441099 fe 2 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configurações de linha

As configurações de linha variam de acordo como qual componente foi arrastado para a tabela.

É possível, também, usar as [ações de clique com o botão direito](../../../../analyze/analysis-workspace/visualizations/freeform-table.md#concept_0D2E24FCCBAF4194AA941448860E422F) para gerenciar a(s) linha(s) selecionada(s).

Para acessar as configurações das linhas da tabela, clique o ícone de Configuração próximo a uma dimensão, segmento, métrica, período de tempo ou um detalhamento em cada uma dessas:

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração da linha </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> Comparações de datas</a> </p> </td> 
   <td colname="col2"> <p><b>Alinhar as datas de cada coluna para que todas iniciem na mesma linha. </b> </p> <p>Ao escolher alinhas das datas, por exemplo, em uma comparação de mês por mês entre outubro e setembro de 2016, a coluna da esquerda iniciará em 1° de outubro e a coluna da direita em 1° de setembro: </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>Desabilitado por padrão </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porcentagens </p> </td> 
   <td colname="col2"> <p><b>Calcular os percentuais por linha</b> </p> <p>Força a tabela de forma livre a calcular as porcentagens de célula na linha, e não na coluna. Essa configuração é útil para porcentagens de tendência. Está ativada por padrão ao usar o ícone <span class="uicontrol">Visualizar</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totais de colunas </p> </td> 
   <td colname="col2"> <p>Estas configurações aparecem apenas com <a href="../../../../analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md#concept_C50E7DFBC0504C72A973123192F487D8" format="dita" scope="local"> linhas manuais (estática)</a> (quando seleciona um conjunto limitado de itens), não com linhas dinâmicas (quando solta em uma dimensão que mostra todos os itens). <p>Observação: para <i>métrica</i> de linhas manuais, a configuração é desativada, uma vez que não faz sentido somar qualquer métrica além das linhas atuais de uma tabela. </p> </p> <p><b>Calcule as somas resumindo os valores que estão atualmente em cada coluna (habilitada por padrão):</b> </p> <p>Esta opção calcula somente as linhas que estão atualmente no gráfico. (Cálculo do lado do cliente) </p> <p><b>Calcule as somas baseadas em todas as linhas para cada métrica (desabilitada por padrão)</b> </p> <p>Esta opção inclui todos os itens de dimensão para esta dimensão, até mesmo aqueles que não estão listados no gráfico. (Cálculo do lado do servidor) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detalhamentos </p> </td> 
   <td colname="col2"> <p><b>Detalhamento por posicionamento:</b> </p> <p>Você pode executar detalhamentos baseados em uma localização fixa em uma tabela de Forma livre. Por exemplo, você pode especificar que as sete primeiras fileiras superiores devam sempre estar detalhadas. </p> <p>(Anteriormente, a lista de valores no detalhamento era “bloqueada”. Esse problema levou a uma situação em que, por exemplo, caso detalhasse <span class="term">Data</span> por <span class="term">Página</span>, você obteria uma lista das 50 páginas principais para o intervalo de datas selecionado. Se salvasse o relatório e o executasse um mês depois, seria provável que as 50 páginas tivessem mudado. Entretanto, a Analysis Workspace usaria os resultados do detalhamento original e retornaria as mesmas páginas, porém com o mês atual como o intervalo de data.) </p> <p>Para executar detalhamentos baseados em um local fixo: </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">Detalhar algumas linhas da tabela. </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">Clicar o ícone Configurações (engrenagem) próximo à linha da tabela que você deseja em um local fixo. </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">Checar a caixa de seleção próxima ao <span class="uicontrol">Detalhamento por posição</span>. </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">Mudar a ordem de classificação ou o intervalo de data e observar que os detalhamentos estão agora vinculados à posição da linha e não às linhas embutidas em código. </li> 
    </ol> <p>Desabilitado por padrão </p> </td> 
  </tr> 
 </tbody> 
</table>

