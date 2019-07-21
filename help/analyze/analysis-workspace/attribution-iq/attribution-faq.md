---
description: 'null'
seo-description: 'null'
seo-title: Perguntas frequentes sobre o Attribution IQ
title: Perguntas frequentes sobre o Attribution IQ
uuid: 90961172-869 d -4 ed 3-aba 5-52374 e 53 b 603
translation-type: tm+mt
source-git-commit: ab2cda6d10bfeee13262581578bcdb4746112296

---


# Perguntas frequentes sobre o Attribution IQ

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: Por que o item de linha “Nenhuma” às vezes recebe mais crédito do que o esperado quando eu uso os novos modelos de atribuição?</b> </p> </td> 
   <td colname="col2"> <p>R: O motivo pode ser a janela de relatório que você escolheu conforme descrito <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A" format="dita" scope="local">aqui </a>. Isso geralmente acontece quando sua janela de relatório tem início no primeiro dia do mês e você usa um lookback de Visitante (janela de relatório). Para capturar lookbacks de atribuição adicionais (e reduzir o item de linha “Nenhuma”), tente incluir um intervalo de tempo maior em sua janela de relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Às vezes, vejo datas que não estão incluídas na minha janela de relatório serem exibidas em meu relatório ao usar modelos de atribuição. Por quê?</b> </p> </td> 
   <td colname="col2"> <p>R: Essas datas adicionais são um artifato da janela de lookback de relatório de visitante descrita <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md" format="dita" scope="local">aqui </a>. O artigo <a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html" format="html" scope="external">Dados sendo exibidos fora da janela de lookback</a> explica a razão para isso. O Adobe Analytics filtrará essas linhas adicionais em uma versão futura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Posso usar uma janela de lookback personalizada com meus modelos de atribuição?</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html" format="html" scope="external"> Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Quando devo usar um lookback de atribuição de “visita” e quando devo usar um lookback de atribuição de “visitante”?</b> </p> </td> 
   <td colname="col2"> <p>R: A escolha do lookback de atribuição depende do seu caso de uso. Se sua conversão geralmente tem um ciclo de consideração mais longo (com duração maior que uma única visita), recomendamos usar um lookback de visitante, ou criar um Conjunto de relatórios virtual com uma visita maior que reflita o clclo de consideração com mais precisão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Modelos de atribuição estão disponíveis em Feeds de dados ou no Data Warehouse?</b> </p> </td> 
   <td colname="col2"> <p>R: Não. Uma vez que modelos de atribuição são calculados no momento do relatório usando <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">Processamento de tempo de relatório</a>, não é possível refleti-los em Feeds de dados ou no Data Warehouse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Os modelos de atribuição são disponibilizados somente ao usar um Conjunto de relatórios virtual com o Processamento de tempo de relatório habilitado?</b> </p> </td> 
   <td colname="col2"> <p>R: Não, apesar de modelos de atribuição aproveitarem o <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">Processamento de tempo de relatório</a> no backend, nós os disponibilizamos para tanto Conjuntos de relatórios virtuais quando conjuntos de relatórios de base, para fins de conveniência. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: O Attribution IQ na Analysis Workspace dá suporte a um modelo de atribuição impulsionado por dados ou de algoritmos?</b> </p> </td> 
   <td colname="col2"> <p>R: Esse recurso ainda não está disponível na Analysis Workspace, mas estamos trabalhando para disponibilizá-lo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Há métricas ou dimensões que não são compatíveis com o Attribution IQ?</b> </p> </td> 
   <td colname="col2"> <p>A: O IQ da atribuição é suportado em todas as dimensões.</p> 
    <p>Métricas que <u>não</u> são compatíveis (principalmente porque não fariam sentido): </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> Visitantes únicos </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">Visitas </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">Ocorrências </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> Exibições de página </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">Métricas do A4T </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">Métricas de tempo gasto </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">Devoluções </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">Taxa de rejeição </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">Entradas </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">Saídas </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">Páginas não encontradas </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">Pesquisas </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">Visitas únicas à página </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">Acesso único </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Como o Attribution IQ difere da atribuição no Data Workbench?</b> </p> </td> 
   <td colname="col2"> <p>R: O Data Workbench incrementalmente oferece: </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">A habilidade de atribuir entre mais fontes de dados no nível do visitante, como impressões de anúncios e ponto de venda. </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">Modelo de algoritmo (<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html" format="html" scope="external">mais adequado</a>). O Attribution IQ inclui somente modelos com base em regras. </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">Visualizações adicionais, como <a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html" format="html" scope="external">tabelas de latência </a>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: O Attribution IQ é compatível com fontes de dados?</b> </p> </td> 
   <td colname="col2"> <p>R: No momento, o Attribution IQ é compatível com fontes de dados que não são fontes de dados de resumo. </p> <p> A atribuição avançada não é possível, uma vez que fontes de dados de resumo não são vinculadas a um identificador de visitante do Analytics. Fontes de dados de ID de transação também são compatíveis, a menos que sejam usadas em um Conjunto de relatórios virtual com <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">processamento de tempo de relatório</a> habilitado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: O Attribution IQ é compatível com a integração do <a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html" format="html" scope="external">Advertising Analytics</a>?</b> </p> </td> 
   <td colname="col2"> <p>A: As métricas integradas, (que incluem impressões, custo, cliques, posição média e pontuação média de qualidade) são fontes de dados de resumo, e portanto não são compatíveis com o Attribution IQ. Entretanto, as dimensões de metadados (por exemplo, tipo de correspondência e palavra-chave) são compatíveis com a atribuição quando usadas com métricas ou eventos padrão do Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

