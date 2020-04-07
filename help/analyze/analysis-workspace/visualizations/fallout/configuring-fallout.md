---
description: 'null'
title: Configurar uma visualização de fallout
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: 2cd9872ed5052b9569d03a07d5171221b9e0af29

---


# Configurar uma visualização de fallout

Você pode especificar os pontos de contato para criar uma sequência de fallout multidimensional. Geralmente, um ponto de contato é uma página do site. No entanto, os pontos de contato não estão limitados às páginas. Por exemplo, você pode adicionar eventos, como unidades, visitantes únicos e visitas de retorno. Também é possível adicionar dimensões, como uma categoria, tipo de navegador ou termo de pesquisa interno.

Você pode até mesmo adicionar segmentos em um ponto de contato. Por exemplo, você pode querer comparar segmentos, como usuários de iOS e Android. Arraste os segmentos desejados para a parte superior do fallout e as informações sobre esses segmentos são adicionadas ao relatório de fallout. Se quiser mostrar apenas esses segmentos, você pode remover a linha de base Todas as visitas.

Não há limitação no número de etapas que você pode adicionar ou no número de dimensões usadas.

É possível definir caminho em eVars, incluindo eVars de comercialização e [listVars](https://marketing.adobe.com/resources/help/pt_BR/sc/implement/listN.html) (variáveis que podem ter vários valores por ocorrência, como produtos, listVars, eVars de comercialização e props de lista). Por exemplo, suponha que alguém esteja pesquisando sapatos e camisetas em uma página e camisetas e meias em outra. O próximo relatório de fluxo do produto para sapatos será camisetas e meias, e NÃO camisetas.

1. Arraste uma [!UICONTROL Fallout] visualização do menu suspenso Visualizações para um [!UICONTROL Freeform Table].

1. Drag the Page dimension into the Freeform Table and from there, drag a page (in this case, Home - JJEsquire) into the **[!UICONTROL Add TouchPoint]** field as the first touchpoint.

   ![](assets/fallout1.png)

   Passe o mouse sobre um ponto de contato para ver o fallout e outras informações sobre o nível, como o nome do ponto de contato e o número de visitantes no ponto, e ver a taxa de sucesso do ponto de contato (bem como para comparar a taxa de sucesso com outros pontos de contato).

   Os números circulados na parte cinza da barra mostram o fallout entre pontos de contato (não o fallout geral até esse ponto). A % de ponto de contato mostra o fallthrough bem-sucedido da etapa anterior para a etapa atual no relatório de fallout.

   Você também pode adicionar uma única página ao relatório de fallout, em vez da dimensão inteira. Clique na seta para a direita &quot;>&quot; na dimensão da página para selecionar a página específica a ser adicionada ao relatório de fallout.

1. Continue adicionando pontos de contato até que a sequência seja concluída.

   Você pode **combinar vários pontos de contato** arrastando um ou mais pontos adicionais até um ponto de contato.

   >[!NOTE]
   >
   >Quando são vários segmentos, eles são ligados com AND, mas quando são vários itens (como itens de dimensão e métricas), são ligados com OR.

   ![](assets/multiple_obj_touchpoint.png)

1. You can also **constrain individual touchpoints to the next hit** (as opposed to &quot;eventually&quot;) within the path. Abaixo de cada ponto de contato, há um seletor com as opções &quot;Caminho eventual&quot; e &quot;Próxima ocorrência&quot;, como mostrado aqui:

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caminho eventual </p> <p>(Padrão) </p> </td> 
   <td colname="col2"> <p>São contados Visitantes que "eventualmente" serão direcionados para a próxima página no caminho, mas não necessariamente na próxima ocorrência. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Próxima ocorrência </p> </td> 
   <td colname="col2"> <p>São contados Visitantes que chegarão na próxima página no caminho na próxima ocorrência. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configurações de fallout {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Configuração | Descrição |
|--- |--- |
| Container de fallout <ul><li>Visita</li><li>Visitante.</li></ul> | Permite alternar entre Visita e Visitante para analisar a definição do caminho do visitante. O padrão é Visitante.  Essas configurações ajudam você a entender o envolvimento no nível dos visitantes (ao longo das visitas) ou restringir a análise a uma só visita. |
| Mostrar “Todos os visitantes” como primeiro ponto de contato | Você pode desmarcar isso se não quiser ter “Todos os visitantes” como primeiro ponto de contato. |

Quando você **clicar com o botão direito em um ponto de contato**, as seguintes opções são exibidas:

| Opção | Descrição |
|--- |--- |
| Tendência do ponto de contato | Consulte os dados de tendência de um ponto de contato em um gráfico de linha, com alguns dados de detecção de anomalias pré-criados. |
| Ponto de contato de tendência (%) | Executa a tendência da porcentagem total de fallout. |
| Analisar a tendência de todos os pontos de contato (%) | Executa a tendência de todas as porcentagens de ponto de contato no fallout (exceto &quot;Todas as visitas&quot;, se incluído), no mesmo gráfico. |
| Analisar fallthrough neste ponto de contato | Visualização o que os visitantes fizeram entre dois pontos de contato (este ponto de contato e o próximo ponto de contato) se continuaram até o próximo ponto de contato. Isso cria uma tabela de forma livre mostrando suas dimensões. É possível substituir dimensões e outros elementos da tabela. |
| Analisar fallout neste ponto de contato | Visualização o que as pessoas que não passaram pelo funil fizeram imediatamente após a etapa selecionada. |
| Criar segmento a partir do ponto de contato | Crie um novo segmento a partir do ponto de contato selecionado. |
