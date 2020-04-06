---
description: Data Warehouse refere-se à cópia dos dados do Analytics para fins de armazenamento e relatórios personalizados, que podem ser executados ao filtrar os dados. Você pode solicitar relatórios para exibir relações de dados avançadas a partir de dados brutos com base em suas perguntas exclusivas. Os relatórios do data warehouse são enviados por email ou enviados via FTP e podem levar até 72 horas para serem processados. O tempo de processamento depende da complexidade do query e da quantidade de dados solicitados.
title: Visão geral do Data Warehouse
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral do Data Warehouse

O Data Warehouse se refere à cópia dos dados do Analytics para relatórios personalizados e de armazenamento, que podem ser executados filtrando os dados. Você pode solicitar relatórios para exibir relações de dados avançadas a partir de dados brutos com base em suas perguntas exclusivas. Os relatórios do data warehouse são enviados por email ou enviados via FTP e podem levar até 72 horas para serem processados. O tempo de processamento depende da complexidade do query e da quantidade de dados solicitados.

A Adobe ativa o Data Warehouse somente para usuários com nível de administrador, para conjuntos de relatórios específicos. (Ele pode ser ativado para conjuntos de relatórios globais e secundários, mas não para conjuntos de relatórios de rollup.) O administrador pode criar um grupo que tenha acesso ao Data Warehouse e, em seguida, associar usuários de nível não administrativo a esse grupo.

O Data Warehouse compacta automaticamente qualquer arquivo que exceda 1 MB. O tamanho máximo do anexo de email é de 10 MB.

O Data Warehouse pode processar um número ilimitado de linhas em uma única solicitação para relatórios individuais programados e baixados.

>[!NOTE] O Data Warehouse relata o primeiro valor encontrado no período do relatório.

>[!IMPORTANT]
>
>Ao segmentar em valores classificados, a Analysis Workspace e o Data Warehouse tratam valores “não especificados” de maneira diferente. “Não especificado” na Analysis Workspace refere-se a valores que não estão classificados, enquanto “Não especificado” no Data Warehouse refere-se a valores que você classificou como “Não especificado”.

## Descrições de solicitações de Data Warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

Esta tabela descreve os campos e as opções na [!UICONTROL Data Warehouse Request] guia.

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
    </ul> <p>O relatórios do Data Warehouse em conjuntos de relatórios virtuais suporta o fuso horário alternativo configurado no conjunto de relatórios virtual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Segmentos disponíveis</span> </td> 
   <td colname="col2"> <p>Permite selecionar a parte da população do visitante que deseja examinar e gerar segmentos complexos. Você pode carregar segmentos pré-configurados, criar novos segmentos e armazenar componentes de segmentos em uma biblioteca para usar na construção de segmentos adicionais. </p> <p>Agora é possível empilhar segmentos. Ao selecionar vários segmentos, a área de pré-visualização, o Gerenciador de solicitações e o pop-up Detalhes da solicitação mostram uma lista de nomes separada por vírgulas (por exemplo, Segmento1, Segmento2). </p> <p>Consulte o <a href="/help/components/c-segmentation/seg-home.md">Guia de segmentação do </a> para obter mais informações. </p> <p>Observação: não é possível incluir um filtro de segmentos e um detalhamento no mesmo segmento, no mesmo relatório de Data Warehouse. Essa ação resultará em um erro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Detalhamentos</span> </td> 
   <td colname="col2"> <p>Permite categorizar dados usando detalhamentos. Os segmentos e detalhamentos diferem na medida em que um segmento filtros dados de um conjunto de dados, enquanto um detalhamento compartimentaliza os dados em todos os valores válidos para o detalhamento. </p> Também é possível detalhar um relatório por um ou mais segmentos. No entanto, não é possível incluir um filtro de segmento e um detalhamento no mesmo segmento, no mesmo relatório do Data Warehouse. Essa ação resultará em um erro. <p> Por exemplo, use segmentos para remover um gênero do conjunto de dados e use um detalhamento para ver os dados separados por gênero. </p> <p>Quando uma solicitação do Data Warehouse é enviada com várias dimensões de vários valores (por exemplo, vários Relatórios móveis), um número exponencial de linhas pode ser gerado de uma única ocorrência. O número de linhas que podem ser geradas a partir de uma única ocorrência é limitado a 100 (anteriormente 1.000). </p> </td> 
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
   <td colname="col2"> <p>Permite agendar solicitações de delivery automático em intervalos selecionados ou como um relatório único. Se você usar o formato padrão, o relatório chegará em um email como um arquivo .csv. </p> <p>Para adicionar o intervalo de datas, inclua <span class="filepath">%R</span> no nome do arquivo. Este valor representa os valores de data solicitados no relatório. Por exemplo, se você solicitar dados de 01 de maio de 2013 até 07 de maio de 2013, o <span class="filepath">R%</span> mostra um nome de arquivo incluindo o intervalo de datas de 20130501-20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

