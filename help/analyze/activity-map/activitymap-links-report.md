---
description: O Relatório de links relata os links que foram encontrados na página atual. Ele não relata todos os links que foram coletados para essa página.
title: Relatório de links
topic: Activity map
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
translation-type: tm+mt
source-git-commit: 6b27755178d156b1eaf159640d466bd84659983d

---


# Relatório de links

O Relatório de links relata os links que foram encontrados na página atual. Ele não relata todos os links que foram coletados para essa página.

O Relatório de links na página oferta uma visualização tabular dos links. Às vezes, talvez você queira ver os cliques em links (ou outras métricas) classificados em uma única visualização. Isso permite comparar melhor um link com outro. Crie o Relatório de links na página, incluindo uma lista classificada de todos os links da página (por ID do link), as informações de clique (# e %) e a região da página. Clique no botão Links na página na barra de ferramentas Mapa de Atividades.

The **[!UICONTROL Links On Page]** report opens below the browser frame in the Activity Map dashboard.

## Modo padrão {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

No modo Padrão, o Relatório &quot;Links na Página&quot; mostra os dados do link, de um único dia a vários dias, agregados ao longo do intervalo de datas completo. As seguintes informações serão mostradas para cada link:

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Coluna </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Classificação </td> 
   <td colname="col2"> Classificação na página. No modo Padrão, o valor da classificação permanece o mesmo, independentemente da coluna em que você clica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID do link </td> 
   <td colname="col2">The link's primary ID (for more information on how primary ID is defined by the <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">New Link Tracking Methodology</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cliques </td> 
   <td colname="col2"> O número de cliques brutos de um link especificado e sua porcentagem do total de cliques na página. Se o usuário escolher uma métrica diferente na barra de ferramentas, o Relatório de link reportará sobre essa métrica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> específica </td> 
   <td colname="col2"> Representa a região na página onde o link está localizado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilidade </td> 
   <td colname="col2">Relaciona-se ao status de visibilidade do link. Dois valores são possíveis: 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>Oculto</b>: o link está atualmente na página, mas não é visível para o usuário final (como um submenu em um Menu de navegação que se torna visível somente se o usuário estiver na parte superior do Menu pai) </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>Exibido</b>: o link é exibido na página. No entanto, ele pode ser exibido abaixo da dobra: o usuário precisaria rolar a página para vê-la. </li>
    </ul><p>Observação: se um link for definido como “Oculto”, as sobreposições para ele não serão exibidas. </p></td> 
  </tr> 
 </tbody> 
</table>

**Filtragem de dados**

When you want to zero in on a specific link, you can search for a related term in the **[!UICONTROL Filter Data]** field. Somente os links que correspondem à pesquisa terão sobreposições. Sem um filtro, as sobreposições especificadas nas Configurações [do mapa de](/help/analyze/activity-map/activitymap-overlay-settings.md) Atividades serão exibidas.

## Modo online {#section_AC1967217B5A4532ACB01D33636F6770}

No modo Online, o Relatório de links na página mostra os dados de tendência que abrangem vários minutos.

![](assets/links_on_page.png)

<table id="table_61D1FB0F02894055A1AB394DE4FE4742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Coluna </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Classificação </td> 
   <td colname="col2"> Classificação na página. No caso de uma sobreposição de gradiente ou em bolha, o valor da classificação permanece o mesmo, independentemente da coluna em que você clica. No caso de uma sobreposição de ganhadores/perdedores, esse valor de classificação muda com base nos links que mais ganharam/perderam. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID do link </td> 
   <td colname="col2">A ID primária do link. Para obter mais informações sobre como a ID primária é definida pela Nova metodologia <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> de rastreamento de</a>links. </td>
  </tr> 
  <tr> 
   <td colname="col1"> Cliques em links </td> 
   <td colname="col2"> Total de cliques para o período de tempo selecionado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % Alterar </td> 
   <td colname="col2"> % de alteração entre as métricas de link do período atual e do período anterior. A variação negativa em % é mostrada em vermelho, positiva em verde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tendência </td> 
   <td colname="col2"> Um gráfico de linhas para todos os períodos coletados. O período selecionado no momento é indicado por um marcador verde. O período de pairamento atual é indicado por um marcador vermelho. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> específica </td> 
   <td colname="col2"> Representa a região na página onde o link está localizado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilidade </td> 
   <td colname="col2">Relaciona-se ao status de visibilidade do link. Dois valores são possíveis: 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">Oculto: no momento, o link está na página, mas não é visível para você (por exemplo, qualquer link exibido depois que a página é carregada). </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">Exibido: no momento, o link é exibido na página. No entanto, ele pode ser exibido abaixo da dobra: você teria que rolar a página para vê-la. </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Classificação e filtragem {#section_4B8E8233C21247CAA70DAEC2156548AD}

Às vezes, é necessário analisar apenas os resultados de uma região de página específica (por exemplo, o painel esquerdo) para decidir como organizar o conteúdo dessa região específica da página da Web.

Para essa finalidade, criamos uma funcionalidade de classificação e filtragem para links no Relatório de links na página. A filtragem está disponível no campo de filtro e o termo de pesquisa será aplicado à coluna ID do link e Região do link. A classificação está disponível ao clicar nas chamadas (Classificação, ID do link, Cliques, Mudanças ao longo do tempo, Região, Visibilidade) e pode ser crescente ou decrescente. As sobreposições desaparecem do site quando os links são filtrados do Relatório de links na página.
