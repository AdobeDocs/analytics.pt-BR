---
description: Exibe dados sobre a localização do visitante. Os relatórios de segmentação geográfica incluem Países, Regiões, Cidades, Estados dos EUA e DMA (digital marketing area, área de marketing digital) dos EUA. Os relatórios de Segmentação geográfica são ativados para todos os clientes.
title: GeoSegmentation
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# GeoSegmentation

Exibe dados sobre a localização do visitante. Os relatórios de segmentação geográfica incluem Países, Regiões, Cidades, Estados dos EUA e DMA (digital marketing area, área de marketing digital) dos EUA. Os relatórios de Segmentação geográfica são ativados para todos os clientes.

Todas as métricas que estão disponíveis em outros lugares do Relatórios e análises são incluídas automaticamente nos relatórios de Países, Regiões, Cidades, Estados dos EUA e DMA: métricas baseadas em visitas e conversão, bem como métricas calculadas. For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Relatório </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Países </td> 
   <td colname="col2"> <p> A maior divisão geográfica. Além das exibições padrão (Classificado e com Tendência) disponíveis na maioria dos relatórios, há também a exibição do Mapa que marca os países com cores de acordo com sua contribuição relativa para o tráfego total. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Regiões </td> 
   <td colname="col2"> <p> Uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, uma província ou uma prefeitura. Em outras áreas, é um país constituinte, departamento ou região metropolitana. À direita de cada região mostrada, o país da região também aparece entre parênteses. </p> <p>No detalhe da tabela, clique em Executar um relatório de cidades para essa região (a lente de aumento) para executar um relatório que mostra como as cidades de uma região selecionada tiveram desempenho em comparação com outras cidades da região. </p> <p>See <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cidades </td> 
   <td colname="col2"> <p> A menor divisão geográfica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estados dos EUA </td> 
   <td colname="col2"> <p> Um mapa de calor mostrando visitantes para cada estado dos Estados Unidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DMA EUA </td> 
   <td colname="col2"> <p> (Digital marketing area - Área de marketing digital) divisões do mercado de mídia para rádio e televisão em todos os Estados Unidos. Você pode filtrar o relatório para mostrar somente as áreas de marketing em um estado específico. Esses dados são fornecidos por meio de uma parceria entre a Adobe e a Nielsen Media Research, Inc. </p> <p>Observação: a entrada não especificada no relatório de DMA EUA indica visitantes que não foram associados a uma DMA específica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Precisão do relatório </td> 
   <td colname="col2"> <p>A Adobe estabeleceu parceria com a Digital Envoy, um provedor líder de soluções de inteligência e autenticação de IP, para a oferta da GeoSegmentation, um recurso de medição geográfica baseado nos endereços IP dos usuários finais. Embora a precisão com base em conjuntos de dados individuais possa variar, a Digital Envoy geralmente oferta mais de 99% de precisão no nível do país, mais de 97% de precisão no nível da região e mais de 90% de precisão no nível da cidade. </p> <p>Note: These numbers assume that <a href="/help/admin/admin/general-acct-settings-admin.md">the setting</a> to remove the last octet of the IP address is NOT enabled. </p> <p>Os endereços IP são mapeados de acordo com o código postal e cada cidade é definida pelos códigos postais que a "autoridade local" definir como parte dela. Por exemplo, o subúrbio de Berlim não está incluso na definição de Berlim, mas cada cidade é listada separadamente, considerando que os endereços IP podem ser mapeados precisamente de acordo com o código postal das cidades. </p> <p>Alguns fatores que podem influenciar os dados de GeoSegmentation incluem: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Endereços IP que representam proxies corporativos. Eles podem aparecer como tráfego vindo pela rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Endereços IP móveis. A definição de metas de IP móvel funciona em níveis variados, dependendo da localização e da rede. Várias operadoras fazem a conexão retroativa do tráfego de IP por meio de POPs centralizados ou regionais. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Endereços IP pertencentes a usuários de ISPs de satélite. Identificar a localização específica desses usuários é difícil, pois eles geralmente parecem vir da localização do uplink. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">IPs militares e governamentais. Isso frequentemente representa pessoal viajando pelo globo e entrando pelo local de sua casa, em vez da base ou escritório onde eles estão estacionados. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Nossos dados de GeoSegmentation/IP são fornecidos por um fornecedor terceirizado e são atualizados regularmente com base nas informações fornecidas pelos ISPs e outras fontes de rede. Pesquisas de IP são inerentemente voláteis, porque são compradas e vendidas frequentemente em todo o mundo. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

