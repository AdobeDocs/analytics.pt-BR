---
description: Lista identificadores de dimensão opcionais que podem ser fornecidos na Etapa 4 do assistente de integração da Adobe.
seo-description: Lista identificadores de dimensão opcionais que podem ser fornecidos na Etapa 4 do assistente de integração da Adobe.
seo-title: Dimensões personalizadas Demandbase
title: Dimensões personalizadas Demandbase
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Dimensões personalizadas Demandbase{#demandbase-custom-dimensions}

Lista identificadores de dimensão opcionais que podem ser fornecidos na Etapa 4 do assistente de integração da Adobe.

Se não tiver certeza da ID exata da API para entrar no assistente, consulte seu representante Demandbase.

>[!IMPORTANT]
>
>É altamente recomendável NÃO incluir Endereço IP como uma dimensão personalizada. O número extremamente alto de valores únicos pode causar problemas de desempenho com os relatórios. Além disso, o Endereço IP já é oferecido como uma opção de relatório por meio dos relatórios do data warehouse da Adobe.

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
   <td colname="col3"> Indica se a organização identificada está classificada como ISP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alias de marketing </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> Nome da organização limpo e/ou abreviado (32 caracteres ou menos) para uso em anúncios, mensagens ou cópia de marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tags de observação de conta </td> 
   <td colname="col2"> watch_list (personalizado) </td> 
   <td colname="col3">Conjunto ilimitado de tags definido pelo cliente que pode ser adicionado aos dados de resposta da API, por organização. <p><b>Exemplo</b>: se você tiver uma tag Watch chamada Q4 Target, o campo da API será </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> Indica se a organização está na lista Fortune 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> Indica se a organização está na lista Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contagem de funcionários </td> 
   <td colname="col2"> count_funcionário </td> 
   <td colname="col3"> O número de pessoas empregadas na organização. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vendas anuais </td> 
   <td colname="col2"> year_sales </td> 
   <td colname="col3"> Para entidades públicas, as receitas anuais baseiam-se em registros públicos comunicados pela empresa para o QG global em todos os locais. Para organizações privadas, baseia-se na estimativa consensual do número anual de receitas de vendas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Telefone </td> 
   <td colname="col2"> telefone </td> 
   <td colname="col3"> O número de telefone da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço </td> 
   <td colname="col2"> rua_endereço </td> 
   <td colname="col3"> O endereço da organização identificado. </td> 
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
   <td colname="col2"> country_code </td> 
   <td colname="col3"> Código ISO de dois caracteres do país da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome do país </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> O nome do país do valor da string do país para a organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> O CEP do país/estado da organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Site </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> O URL usado pela organização identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contador de ações </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> A cotação de ações se a organização identificada for objeto de negociação pública. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código SIC primário </td> 
   <td colname="col2"> Primary_sic </td> 
   <td colname="col3"> Código SIC de Consenso atribuído à organização identificada. </td> 
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
   <td colname="col3"> A quantidade de tráfego do site, estimado em baixo, médio ou alto ou muito alto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indica que a empresa identificada vende principalmente para outras empresas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indica que a empresa identificada vende principalmente a consumidores ou indivíduos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tecnologia Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Até 75 categorias de tecnologia definidas pelos clientes por categoria, fornecedor e produtos para uso de direcionamento e/ou personalização de anúncios, mensagens ou cópia de marketing. </td> 
  </tr> 
 </tbody> 
</table>

