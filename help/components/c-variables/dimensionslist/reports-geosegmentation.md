---
description: Exibe dados sobre a localização do visitante. Relatórios de segmentação geográfica incluem Países, Regiões, Estados Unidos, e a DMA (digital marketing area - área de marketing digital) dos EUA. Relatórios de GeoSegmentation estão habilitados para todos os clientes.
title: GeoSegmentation
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# GeoSegmentation

Exibe dados sobre a localização do visitante. Relatórios de segmentação geográfica incluem Países, Regiões, Estados Unidos, e a DMA (digital marketing area - área de marketing digital) dos EUA. Relatórios de GeoSegmentation estão habilitados para todos os clientes.

Todas as métricas que estão disponíveis em outro lugar no Reports &amp; Analytics são incluídas automaticamente nos relatórios de Países, Regiões, Cidades, Estados dos EUA, e DMA: métricas com base em visitas, assim como em métricas calculadas. Para obter mais informações, consulte essa postagem no [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) da Adobe.

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
   <td colname="col2"> <p> Uma área geográfica menor do que um país e maior do que uma cidade. Em alguns países, uma região é um estado, ou município. Em outras áreas, é um país constituinte, departamento ou região metropolitana. Ao lado direito de cada região mostrada, o país da região também é exibido entre parênteses. </p> <p>No detalhe da tabela, clique em Executar um relatório de cidades para esta região (lente de aumento) para executar um relatório que exibe como as cidades na região selecionada em comparação com outras cidades na região. </p> <p>Consulte <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > Utilização de regiões de segmentação geográfica e código postal por país</a> para visualizar quais países utilizam regiões. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cidades </td> 
   <td colname="col2"> <p> A menor divisão geográfica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estados dos EUA </td> 
   <td colname="col2"> <p> Um mapa de mercado que mostra os visitantes de cada estado dos EUA. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DMA EUA </td> 
   <td colname="col2"> <p> (Digital marketing area - Área de marketing digital) divisões de marketing de mídia de rádio e televisão em todo os Estados Unidos. Você pode filtrar o relatório para exibir somente as áreas de marketing em um estado específico. Os dados são fornecidos por uma parceria entre a Adobe e Nielsen Media Research, Inc. </p> <p>Observação: a entrada não especificada no relatório de DMA EUA indica visitantes que não foram associados a uma DMA específica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Precisão do relatório </td> 
   <td colname="col2"> <p>A Adobe fez parceria com a Digital Envoy, uma fornecedora líder de soluções de inteligência e autenticação de IP, para oferecer GeoSegmentation, uma capacidade de medição geográfica baseada nos endereços de IP de usuários finais. Enquanto a precisão em conjuntos de dados individuais pode variar, a Digital Envoy geralmente oferece 99% de precisão a nível de país, em relação aos 97% de precisão a nível de região, e em relação aos 90% de precisão a nível de cidade. </p> <p>Observação: esses números presumem que [a configuração] (/help/admin/admin/general-acct-settings-admin.md) para remover o último octeto do endereço IP NÃO está ativada. </p> <p>Os endereços IP são mapeados de acordo com o código postal e cada cidade é definida pelos códigos postais que a "autoridade local" definir como parte dela. Por exemplo, o subúrbio de Berlim não está incluso na definição de Berlim, mas cada cidade é listada separadamente, considerando que os endereços IP podem ser mapeados precisamente de acordo com o código postal das cidades. </p> <p>Alguns fatores que podem influenciar os dados de GeoSegmentation do incluem: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Endereços de IP que representam procurações corporativas. Esses endereços podem aparecer como tráfego vindo através da rede corporativa do usuário, que pode ser um local realmente diferente se o usuário estiver trabalhando remotamente. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Endereços de IP móveis. Trabalhos de segmentação de IP móvel a níveis variáveis dependendo do local e da rede. Um número de transmissores faz a conexão ponto-a-ponto do tráfego de IP através de POPs centralizados ou regionais. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Endereços de IP pertencentes aos usuários de satélite ISPs. Identificar a localização específica desses usuários é difícil, uma vez que geralmente eles aparentam vir da localização do uplink. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">IPs militares e do governamentais. Isso geralmente representa pessoal viajando pelo globo e entrando através da localização de sua casa, em vez de entrar da base ou do escritório onde estão atualmente estacionadas. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Nossos dados de GeoSegmentação/IP são fornecidos por um fornecedor terceirizado e são atualizados regularmente com base nas informações fornecidas pelos ISPs e outras fontes em rede. Pesquisas de IP são inerentemente voláteis, pois eles são comprados e vendidos constantemente em todo o mundo. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

