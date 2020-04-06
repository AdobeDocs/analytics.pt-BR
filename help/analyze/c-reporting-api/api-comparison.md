---
description: Uma tabela de comparação para APIs de relatórios do Analytics. São fornecidos links para a documentação de suporte.
title: Comparação de APIs em relatórios do Analytics
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Comparação de APIs em relatórios do Analytics

Uma tabela de comparação para APIs de relatórios do Analytics. São fornecidos links para a documentação de suporte.

>[!NOTE] No que diz respeito à latência, o Analytics para Target (A4T) combina dados do Analytics e do Target na mesma ocorrência, favorecendo a geração de relatórios integrados. Como as chamadas do Analytics e do Público alvo ocorrem em momentos diferentes, as ocorrências são armazenadas antes de qualquer processamento para coletar dados de ambas as soluções. Esse processo adiciona **uma latência adicional de 7 a 10 minutos** a todos os pontos de verificação.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de API </th> 
   <th colname="col2" class="entry"> Totalmente processado </th> 
   <th colname="col3" class="entry"> Tempo Real </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Descrição</b> </td> 
   <td colname="col2"> Dados totalmente processados e finalizados que estão disponíveis em todas as interfaces do Analytics. </td> 
   <td colname="col3"> Métricas parcialmente processadas e limitadas disponíveis em segundos de coleta. </td> 
   <td colname="col4"> Dados de ocorrência parcialmente processados disponíveis em segundos de coleta. </td> 
   <td colname="col5"> Dados totalmente processados e finalizados usados para extrair grandes exportações de dados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > Latência</a> </p> </td> 
   <td colname="col2"> 30 a 90 minutos </td> 
   <td colname="col3"> * Segundos -10 minutos </td> 
   <td colname="col4"> Segundos - 10 minutos </td> 
   <td colname="col5"> 90 minutos + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conclusão de processamento</b> </td> 
   <td colname="col2"> Máxima </td> 
   <td colname="col3"> Parcial </td> 
   <td colname="col4"> Parcial </td> 
   <td colname="col5"> Máxima </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/pt_BR/reference/"  > Interfaces de relatórios</a> </td> 
   <td colname="col2"> Relatórios e análises, Construtor de relatórios, API </td> 
   <td colname="col3"> Relatório em tempo real em Relatórios e análises, Construtor de relatórios, API </td> 
   <td colname="col4"> Somente API </td> 
   <td colname="col5"> Data Warehouse e API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Granularidade de dados</b> </td> 
   <td colname="col2"> Resumo </td> 
   <td colname="col3"> Resumo </td> 
   <td colname="col4"> Nível de ocorrência </td> 
   <td colname="col5"> Resumo </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processamento de Perfis Visitantes</b> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Não </td> 
   <td colname="col5"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Suporta segmentos</b> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Não </td> 
   <td colname="col5"> Sim (mas somente segmentos compatíveis com o Data Warehouse) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>SKU do Analytics</b> </td> 
   <td colname="col2"> Padrão+ </td> 
   <td colname="col3"> Padrão+ </td> 
   <td colname="col4"> Premium completo ou Inteligência preditiva </td> 
   <td colname="col5"> Padrão+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentação</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Serviços Web</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > Relatórios em tempo real</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Visão geral do Livestream</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/pt_BR/reference/data_warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ajuda relacionada**

* [Adobe/IO](https://www.adobe.io/) - uma fonte abrangente para a documentação técnica e as ferramentas necessárias para integrar as tecnologias da Adobe aos seus aplicativos.
* [API de Query do Análise de big data](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

