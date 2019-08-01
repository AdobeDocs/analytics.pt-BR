---
description: Lista identificadores de dimensão opcionais que podem ser fornecidos na Etapa 4 do assistente de integração da Adobe.
seo-description: Lista identificadores de dimensão opcionais que podem ser fornecidos na Etapa 4 do assistente de integração da Adobe.
seo-title: Dimensões personalizadas demandbase
title: Dimensões personalizadas demandbase
uuid: d 1621046-3 aa 2-46 b 9-a 536-4 a 8 fb 792 b 69 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

Lista identificadores de dimensão opcionais que podem ser fornecidos na Etapa 4 do assistente de integração da Adobe.

Se não tiver certeza da ID exata da API para entrar no assistente, consulte o representante do Demandbase.

>[!IMPORTANT]
>
>É altamente recomendável que VOCÊ NÃO inclua Endereço IP como uma dimensão personalizada. O número extremamente alto de valores únicos pode causar problemas de desempenho com relatórios. Além disso, o Endereço IP já está oferecido como uma opção de relatório por meio de relatórios do data warehouse da Adobe.

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensão </th> 
   <th colname="col2" class="entry"> IDs de API </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> Indica se a organização identificada está classificada como um ISP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alias de marketing </td> 
   <td colname="col2"> marketing_ alias </td> 
   <td colname="col3"> Nome da organização limpo e/ou encurtado (32 caracteres ou menos) para uso em anúncios, mensagens ou cópia de marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tags de Watch Watch </td> 
   <td colname="col2"> watch_ list (personalizado) </td> 
   <td colname="col3">Conjunto ilimitado de tags definidas por cliente que podem ser adicionadas aos dados de resposta da API, por organização. <p><b>Exemplo</b>: se você tiver uma Tag de observação chamada Q 4 Target, o campo API será </p> <code> watch_ list_ q 4_ target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_ 1000 </td> 
   <td colname="col3"> Indica se a organização está na lista da Fortune 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_ 2000 </td> 
   <td colname="col3"> Indica se a organização está na lista de Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contagem de funcionários </td> 
   <td colname="col2"> employee_ count </td> 
   <td colname="col3"> O número de pessoas empregadas na organização. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vendas anuais </td> 
   <td colname="col2"> annual_ sales </td> 
   <td colname="col3"> Para entidades públicas, a receita anual é baseada nos registros públicos reportados pela empresa para o HQ global em todos os locais. Para organizações privadas, baseia-se em estimativa de consenso para o número da receita anual de vendas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número de telefone </td> 
   <td colname="col2"> telefone </td> 
   <td colname="col3"> O número de telefone da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço Street </td> 
   <td colname="col2"> street_ address </td> 
   <td colname="col3"> O endereço street da organização identificado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cidade </td> 
   <td colname="col2"> cidade </td> 
   <td colname="col3"> A cidade da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estado </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> O estado da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código do país </td> 
   <td colname="col2"> country_ code </td> 
   <td colname="col3"> O código de país de dois caracteres ISO da organização identificado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome do país </td> 
   <td colname="col2"> country_ name </td> 
   <td colname="col3"> O nome do país de valor da string do país da organização identificado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CEP </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> O código postal do país/estado da organização identificado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Site </td> 
   <td colname="col2"> web_ site </td> 
   <td colname="col3"> O URL usado pela organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Banco de dados </td> 
   <td colname="col2"> stock_ ticker </td> 
   <td colname="col3"> O analisador de ações se a organização identificada for comercializada publicamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código SIC primário </td> 
   <td colname="col2"> primary_ sic </td> 
   <td colname="col3"> Código SIC de consenso atribuído para a organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> Latitude para a localização da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitude </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> Longitude da localização da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tráfego </td> 
   <td colname="col2"> tráfego </td> 
   <td colname="col3"> A quantidade de tráfego do site, estimada como baixa, média ou alta ou muito alta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indica que a empresa identificada vende principalmente para outras empresas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indica que a empresa identificada vende principalmente para consumidores ou indivíduos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Insight tecnológico </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Até 75 categorias de tecnologia definidas por clientes por categoria, fornecedor e produtos para uso de anúncios e/ou personalização de anúncios, mensagens ou cópia de marketing. </td> 
  </tr> 
 </tbody> 
</table>

