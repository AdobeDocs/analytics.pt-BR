---
description: Data Warehouse refere-se à cópia dos dados do Analytics para fins de armazenamento e relatórios personalizados, que podem ser executados ao filtrar os dados. Você pode solicitar relatórios para exibir relações de dados avançadas a partir de dados brutos com base em suas perguntas exclusivas. Os relatórios de data warehouse são enviados por email ou enviados por FTP e podem demorar até 72 para serem processados. O tempo de processamento depende da complexidade da consulta e da quantidade de dados solicitada.
title: Visão geral do Data Warehouse
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visão geral do Data Warehouse

Data Warehouse refere-se à cópia dos dados do Analytics para fins de armazenamento e relatórios personalizados, que podem ser executados ao filtrar os dados. Você pode solicitar relatórios para exibir relações de dados avançadas a partir de dados brutos com base em suas perguntas exclusivas. Os relatórios de data warehouse são enviados por email ou enviados por FTP e podem demorar até 72 para serem processados. O tempo de processamento depende da complexidade da consulta e da quantidade de dados solicitada.

A Adobe ativa o Data Warehouse somente para usuários com nível de administrador, para conjuntos de relatórios específicos. (Pode ser habilitado para conjuntos de relatórios globais e secundários, mas não para conjuntos de relatórios de rollup). O administrador pode criar um grupo que tem acesso ao Data Warehouse e associá-lo a usuários que não tenham direitos administrativos.

O Data Warehouse compacta automaticamente todos os arquivos com mais de 1 MB. O tamanho máximo para o anexo de email é de 10 MB.

O Data Warehouse pode processar uma quantidade ilimitada de linhas em uma única solicitação para relatórios agendados e baixados.

> [!NOTE] O Data Warehouse relata o primeiro valor encontrado no período do relatório.

>[!IMPORTANT]
>
>Ao segmentar em valores classificados, a Analysis Workspace e o Data Warehouse tratam valores “não especificados” de maneira diferente. “Não especificado” na Analysis Workspace refere-se a valores que não estão classificados, enquanto “Não especificado” no Data Warehouse refere-se a valores que você classificou como “Não especificado”.

## Descrições de solicitações de Data Warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

Essa tabela descreve os campos e opções da guia [!UICONTROL Solicitação do Data Warehouse].

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nome da solicitação</span> </td> 
   <td colname="col2"> Identifica a solicitação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Data de relatório</span> </td> 
   <td colname="col2"> <p>A data e a granularidade da solicitação. </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Personalizado</span>: um intervalo de datas configurado por você no calendário. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Predefinição</span>: um intervalo predefinido. O intervalo predefinido é relativo à data do relatório. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularidade</span>: a granularidade do tempo. Os valores válidos são Nenhum, Hora, Dia, Semana, Mês, Trimestre e Ano. </li> 
    </ul> <p>O recurso de relatório do Data Warehouse para conjuntos de relatórios virtuais oferece suporte ao fuso horário alternativo configurado no conjunto de relatórios virtuais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Segmentos disponíveis</span> </td> 
   <td colname="col2"> <p>Permite selecionar a parte da população de visitantes que deseja examinar e gerar segmentos complexos. Você pode fazer upload de segmentos pré-configurados, criar novos segmentos e armazenar componentes de segmento em uma biblioteca para uso na construção de segmentos adicionais. </p> <p>Agora, é possível empilhar segmentos. Ao selecionar vários segmentos, a área de visualização, o Gerenciador de solicitação e o pop-up Detalhes da solicitação mostram uma lista de nomes separada por vírgulas (ex: Segmento1, Segmento2). </p> <p>Consulte o <a href="/help/components/c-segmentation/seg-home.md">Guia de segmentação do </a> para obter mais informações. </p> <p>Observação: não é possível incluir um filtro de segmentos e um detalhamento no mesmo segmento, no mesmo relatório de Data Warehouse. Essa ação resultará em um erro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Detalhamentos</span> </td> 
   <td colname="col2"> <p>Permite categorizar os dados por meio de detalhamentos. A diferença de segmentos e detalhamentos é que uma filtra de segmentos dados de um conjunto de dados, enquanto um detalhamento distribui dados em todos os valores válidos para o detalhamento. </p> Também é possível detalhar um relatório por um ou mais segmentos. No entanto, não é possível incluir um filtro de segmentos e um detalhamento no mesmo segmento, no mesmo relatório de Data Warehouse. Essa ação resultará em um erro. <p> Por exemplo, use segmentos para remover um gênero do conjunto de dados e use um detalhamento para visualizar os dados separados por gênero. </p> <p>Quando uma solicitação de Data Warehouse é enviada com várias dimensões multivalor (ou seja, vários Relatórios móveis), é possível gerar um número exponencial de linhas a partir de uma única ocorrência. O limite do número de linhas que podem ser geradas a partir de uma única ocorrência é de 100 (antigamente 1000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Métricas</span> </td> 
   <td colname="col2">Permite adicionar métricas sobre as quais você deseja criar relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Classificação de métricas</span> </td> 
   <td colname="col2">Oferece relatórios classificados e detalhados, organizados pelo valor de métrica decrescente, similares ao conteúdo exibido na interface do usuário do Reports &amp; Analytics, Data Workbench, etc. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Mais...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Agendar entrega</span> </td> 
   <td colname="col2"> <p>Permite agendar solicitações para a entrega automática em intervalos selecionados, ou como um relatório único. Se você usar o formato padrão, o relatório chega em um email como um arquivo .csv. </p> <p>Para adicionar o intervalo de datas, inclua <span class="filepath">%R</span> no nome do arquivo. Este valor representa os valores de data solicitados no relatório. Por exemplo, se você solicitar dados de 01 de maio de 2013 até 07 de maio de 2013, o <span class="filepath">R%</span> mostra um nome de arquivo incluindo o intervalo de datas de 20130501-20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

