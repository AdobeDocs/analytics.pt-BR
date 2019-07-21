---
description: Uma tabela comparativa de APIs em relatórios do Analytics. São fornecidos links para a documentação de apoio.
seo-description: Uma tabela comparativa de APIs em relatórios do Analytics. São fornecidos links para a documentação de apoio.
seo-title: Comparação de APIs em relatórios do Analytics
solution: Analytics
title: Comparação de APIs em relatórios do Analytics
uuid: fa 533 a 8 e -33 c 0-42 f 4-a 294-cabee 0258 c 8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comparação de APIs em relatórios do Analytics

Uma tabela comparativa de APIs em relatórios do Analytics. São fornecidos links para a documentação de apoio.

>[!NOTE]
>
>Quanto à latência, o Analytics for Target (A 4 T) combina os dados do Analytics e do Target na mesma ocorrência para relatórios integrados. Como as chamadas do Analytics e do Target ocorrem em momentos diferentes, as ocorrências são armazenadas antes de qualquer processamento para a coleta de dados de ambas as soluções. Este processo adiciona de **7 a 10 minutos** à latência para todos os pontos de verificação.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de API </th> 
   <th colname="col2" class="entry"> Completamente processados </th> 
   <th colname="col3" class="entry"> Tempo real </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Descrição</b> </td> 
   <td colname="col2"> Dados completamente processados e finalizados, disponíveis em todas as interfaces do Analytics. </td> 
   <td colname="col3"> Métricas parcialmente processadas e limitadas, disponíveis em segundos de coleta. </td> 
   <td colname="col4"> Dados de ocorrências parcialmente processadas, disponíveis em segundos de coleta. </td> 
   <td colname="col5"> Dados completamente processados e finalizados, usados para extrair grandes exportações de dados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf" format="https" scope="external"> Latência</a> </p> </td> 
   <td colname="col2"> 30 a 90 minutos </td> 
   <td colname="col3"> * Segundos -10 minutos </td> 
   <td colname="col4"> Segundos -10 minutos </td> 
   <td colname="col5"> 90 minutos + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conclusão do processamento</b> </td> 
   <td colname="col2"> Máximo </td> 
   <td colname="col3"> Parcial </td> 
   <td colname="col4"> Parcial </td> 
   <td colname="col5"> Máximo </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/" format="https" scope="external"> Interfaces de relatórios</a> </td> 
   <td colname="col2"> Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col3"> Relatório em tempo real em Reports &amp; Analytics, Report Builder, API </td> 
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
   <td colname="col1"> <b>Processamento do perfil do visitante</b> </td> 
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
   <td colname="col5"> Sim (mas somente se compatíveis com o Data Warehouse) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>SKU do Analytics</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Premium Complete ou Predictive Intelligence </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentação</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B" format="https" scope="external"> Serviços Web</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time" format="https" scope="external"> Relatórios em tempo real</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B" format="https" scope="external"> Visão geral do Livestream</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html" format="https" scope="external"> Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ajuda relacionada**

* [Adobe/IO](https://www.adobe.io/) - Aqui você encontra uma ampla documentação técnica e as ferramentas necessárias para integrar as tecnologias Adobe em seus aplicativos.
* [API de consulta da Data Workbench](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

