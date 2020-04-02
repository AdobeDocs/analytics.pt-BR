---
description: Exibe um detalhe das palavras-chave de pesquisa.
title: Palavras-chave de pesquisa
topic: Reports
uuid: db9d477b-b711-4b93-9c25-3aebe5f2ace6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Palavras-chave de pesquisa

Exibe um detalhe das palavras-chave de pesquisa.

**Palavras-chave de pesquisa - Todas**: mostra o detalhamento de cada palavra-chave de pesquisa usada para encontrar o site. É possível classificar esta lista por exibições da página ou palavras-chave de pesquisa, clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de busca para ver os resultados da pesquisa para o site.

**Palavras-chave de pesquisa - Pagas**: mostra o detalhamento de cada palavra-chave de pesquisa paga usada para encontrar o site. É possível classificar esta lista por exibições da página ou palavras-chave de pesquisa, clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de busca para ver os resultados da pesquisa para o site.

**Palavras-chave de pesquisa - Naturais**: mostra o detalhamento de cada palavra-chave de pesquisa usada para encontrar o site. É possível classificar esta lista por exibições da página ou palavras-chave de pesquisa, clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de busca para ver os resultados da pesquisa para o site.

>[!IMPORTANT]
>
>Para as pesquisas paga e natural, os mecanismos de busca pararam de fornecer (na maioria dos casos) as palavras-chave da pesquisa como parte do referenciador. Como resultado, a Adobe classifica sempre o domínio do Google (ou Bing ou Yahoo) como pesquisa. Com base no formato e no conteúdo do referenciador (mesmo sem as palavras-chave), a Adobe geralmente pode determinar que foi o resultado de uma pesquisa, portanto, a pesquisa é contabilizada nas Palavras-chave indisponíveis. [Mais...](https://helpx.adobe.com/br/analytics/kb/keyword-unavailable.html)

## Alocação, expiração e valores especiais {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Alocação métrica </td> 
   <td colname="col2"> <p>Valor original (padrão) </p> <p> Pode ser alterado para linear. </p> </td> 
   <td colname="col3"> Mais recente (pode ser alterado para linear, usando a versão linear de uma métrica) </td> 
   <td colname="col4"> <p>Valor original (padrão) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor expira após </td> 
   <td colname="col2"> Visita - pode ser encurtada, mas não aumentada </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limites de valor </td> 
   <td colname="col2"> Nenhum limite (pode mudar em um lançamento futuro) </td> 
   <td colname="col3"> Nenhum limite (pode mudar em um lançamento futuro) </td> 
   <td colname="col4"> nenhum </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores especiais </td> 
   <td colname="col2"> <p>"Nenhum": os totais de todo o site não possuem uma palavra-chave durante a visita. </p> "Palavra-chave não disponível" pesquisa onde a palavra-chave foi removida da pesquisa e por que não está sendo enviada para a coleção de dados. Isso normalmente ocorre quando um cliente está conectado à sua conta do Google. Aplica-se ao pago e ao natural. </td> 
   <td colname="col3"> (baixo tráfego) representa valores posteriores aos primeiros 500k, que não receberam tráfego suficiente para serem relatados. </td> 
   <td colname="col4"> <p> Vazio - equivalente a "Nenhum", representa os totais de todo o site que não possuem uma palavra-chave durante a visita. </p> <p>"Palavra-chave não disponível" pesquisa onde a palavra-chave foi removida da pesquisa e por que não está sendo enviada para a coleção de dados. Isso normalmente ocorre quando um cliente está conectado à sua conta do Google. Aplica-se ao pago e ao natural. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Histórico de relatórios  {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Data | Alterar |
|---|---|
| 1/16/2014 | Data warehouse foi atualizado para corresponder à lógica usada e Reports &amp; Analytics de marketing. Até essa data, as palavras-chave de busca não persistiam durante toda a visita. |

