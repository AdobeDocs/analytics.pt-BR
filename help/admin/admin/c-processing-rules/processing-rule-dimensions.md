---
description: As dimensões que você pode ler e escrever (salvo indicação ao contrário) usando as regras de processamento.
seo-description: As dimensões que você pode ler e escrever (salvo indicação ao contrário) usando as regras de processamento.
seo-title: Dimensões disponíveis para regras de processamento
solution: Analytics
subtopic: Regras de processamento
title: Dimensões disponíveis para regras de processamento
topic: Ferramentas administrativas
uuid: ba 73 ab 59-a 8 cf -491 c -8757-5 fb 03 d 6 b 0745
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Dimensões disponíveis para regras de processamento

As dimensões que você pode ler e escrever (salvo indicação ao contrário) usando as regras de processamento.

## Valores personalizados e dados de contexto {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Valor personalizado </p> </td> 
   <td colname="col2"> <p>Texto ou valores personalizados, digitados diretamente na ação de uma regra de processamento. Esses valores são disponibilizados em condições e regras subsequentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valor concatenado </p> </td> 
   <td colname="col2"> <p>Valores criados pela combinação de dois valores. Por exemplo, a categoria e o nome da página devem ser combinados para criar uma subcategoria. Esses valores são disponibilizados em condições e regras subsequentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valores modificados </p> </td> 
   <td colname="col2"> <p>Se o valor de uma variável é alterado usando as regras de processamento, o valor alterado é usado em condições e regras subsequentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variáveis de dados de contexto </p> </td> 
   <td colname="col2"> <p>Variáveis nomeadas que são enviadas com uma ocorrência. </p> <p>Observação: todos os dados contidos em uma Variável de dados de contexto devem ser copiados para uma variável do relatório para serem exibidos em um relatório. As Variáveis de dados de contexto não são visualizadas em qualquer interface de relatório, incluindo Feeds de dados de sequência de cliques. </p> <p> <a href="../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7" format="dita" scope="local"> Copiar uma variável de dados de contexto para uma eVar </a> </p> <p> <a href="../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md#concept_359B4E165ED442938A8EB6A55A725682" format="dita" scope="local"> Definir um evento usando uma variável de dados de contexto </a> </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables" format="http" scope="external"> Variáveis de dados de contexto</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis de tráfego {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hierarquia 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seção do site </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Atributos de ocorrência {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Atributo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID do conjunto de relatórios (somente leitura) </p> </td> 
   <td colname="col2"> <p>O conjunto de relatórios no qual a regra de processamento é executada. Não pode ser o conjunto de relatórios original especificado no AppMeasurement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome da página </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Observação: uma visualização de página é considerada em todas as ocorrências nas quais o nome da página não está vazio. Quando um link é rastreado, o servidor da coleção de dados remove o nome da página da ocorrência para que as visualizações de página não sejam contadas. Se você inserir novamente um nome de página nessas chamadas utilizando as regras de processamento, uma visualização de página será contada. Recomendamos verificar se o nome da página já está definido antes de modificá-lo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL da página </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> ou o URL da página atual, se <code>s.pageURL</code> não for especificado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parâmetro da sequência de caracteres de consulta </p> </td> 
   <td colname="col2"> <p>O valor de um parâmetro da sequência de caracteres de consulta especificado no URL atual, ou nulo se não houver nenhum parâmetro. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>Se você estiver executando o JavaScript AppMeasurement H.25.2 ou versão anterior, o URL da página talvez fique truncado após 255 caracteres. O JavaScript AppMeasurement H.25.3 (versão de janeiro de 2013) e versão posterior fornece o URL total para regras de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caminho da página </p> </td> 
   <td colname="col2"> <p>O caminho do URL da página. The path of the URL <b>https://www.example.com/news/a.html?cid=ad1</b> is <span class="syntax codeph"> news/a.html</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio de página </p> </td> 
   <td colname="col2"> <p>O nome do host completo, especificado no URL. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio raiz de página </p> </td> 
   <td colname="col2"> <p>As últimas duas seções do nome do host da página. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequência de caracteres de consulta de página </p> </td> 
   <td colname="col2"> <p>A string de consulta completa do URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referenciador* (somente leitura) </p> </td> 
   <td colname="col2"> <p>Referenciador de HTTP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parâmetro da string de consulta de referência (somente leitura) </p> </td> 
   <td colname="col2"> <p>O valor de um parâmetro da string de consulta especificado no URL de referência, ou nulo se não houver nenhum parâmetro. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>Se você estiver executando o JavaScript AppMeasurement H.25.2 ou versão anterior, o URL da página talvez fique truncado após 255 caracteres. O JavaScript AppMeasurement H.25.3 (versão de janeiro de 2013) e versão posterior fornece o URL total para regras de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio de referência (somente leitura) </p> </td> 
   <td colname="col2"> <p>O nome do host completo do referenciador. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio raiz de referência (somente leitura) </p> </td> 
   <td colname="col2"> <p>As últimas duas seções do nome do host do referenciador. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequência de caracteres de consulta de referência (somente leitura) </p> </td> 
   <td colname="col2"> <p>Parâmetros da string de consulta contidos no URL de referência. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Endereço IP (somente leitura) </p> </td> 
   <td colname="col2"> <p>Endereço IP, como relatado pelo navegador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agente de usuário (somente leitura) </p> </td> 
   <td colname="col2"> <p>Agente de usuário, como relatado pelo navegador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versão de código de AppMeasurement (somente leitura) </p> </td> 
   <td colname="col2"> <p>A versão da biblioteca do appMeasurement usada para fazer o pedido. Ao usar beacons de imagem, é possível preencher com um valor personalizado que é lido usando as regras de processamento. Esse valor aparece na seguinte posição no URL: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis de conversão {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code>evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de rastreamento de campanha </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de moeda </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variáveis de lista 1 - 3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> - <code>s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de compra </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID da transação </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado do visitante </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código postal/CEP do visitante </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eventos bem-sucedidos {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

As regras de processamento podem definir eventos mas não podem lê-los como condições.

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Evento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evento 1-1000 </p> <p>(Para clientes do SiteCatalyst 15, Evento 1-100.) </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code>event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>compra, scView, scAdd e outros eventos do carrinho </p> </td> 
   <td colname="col2"> <p>Eventos pré-definidos </p> </td> 
  </tr> 
 </tbody> 
</table>

