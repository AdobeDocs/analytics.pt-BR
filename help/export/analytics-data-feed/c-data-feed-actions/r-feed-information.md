---
description: Use a seção Informações do feed para nomear o feed, especificar o conjunto de relatórios com o qual o feed será executado, determinar a recorrência do feed e especificar o início e o fim do feed.
keywords: Feed de dados; informações; name; conjunto de relatórios; e-mail quando concluído; e-mail; intervalo; feed; atrasar o processamento; delay; start; end; date; feed contínuo
seo-description: Use a seção Informações do feed para nomear o feed, especificar o conjunto de relatórios com o qual o feed será executado, determinar a recorrência do feed e especificar o início e o fim do feed.
seo-title: Informações do feed
solution: Analytics
title: Informações do feed
uuid: adf 92 f 42-a 957-4 de 0-a 5 a 1-683 f 2933 af 04
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Informações do feed

Use a seção Informações do feed para nomear o feed, especificar o conjunto de relatórios com o qual o feed será executado, determinar a recorrência do feed e especificar o início e o fim do feed.

![](assets/feed-info.jpg)

<table id="table_C98C7C3CE4194BEF819E792793EBC517">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome (obrigatório) </p> </td>
   <td colname="col2"> <p>Insira um nome para o feed. </p> <p>O nome deve ser único dentre o conjunto de relatórios e deve ter, no máximo, 255 caracteres. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Conjunto de relatórios (obrigatório) </p> </td>
   <td colname="col2"> <p>Especifique os conjuntos de relatórios para a consulta de feed. </p> <p>Pelo menos um conjunto de relatórios deve ser selecionado. Não é permitido listar o mesmo conjunto de relatórios duas vezes. </p> <p>Todos os conjuntos de relatórios não virtuais disponíveis para o usuário conectado estão disponíveis. </p></td>
  </tr>
  <tr>
   <td colname="col1"> <p>Enviar email ao concluir (obrigatório) </p> </td>
   <td colname="col2"> <p>Especifique o email do destinatário que receberá as atualizações de entrega do feed. </p> <p>Este campo não pode ser deixado em branco. Deve conter um endereço de email devidamente formatado. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Intervalo de feed (obrigatório) </p> </td>
   <td colname="col2"> <p>Especifique a recorrência da programação. </p> <p>Observação: devido ao tamanho potencial dos arquivos da compactação do feed de dados, verifique se o processo de ETL usa um utilitário de compactação de 64 bits. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Atraso de processamento (opcional) </p> </td>
   <td colname="col2"> <p>Especifique o atraso para aplicar a cada instância da programação. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Data inicial e final (obrigatório) </p> <p>Feed contínuo (opcional) </p> </td>
   <td colname="col2"> <p>Programe as datas de início e término do feed. </p> <p>
     <ul id="ul_509977336CD34032924B48E043E8CBC7">
      <li id="li_BFB5B6ADCB184D839C9BA42DB3DCAF32">Data inicial: o padrão é a data de hoje </li>
      <li id="li_34F8DB45D9B54076840D1A0B782812D3">Data de término: o padrão é a data de amanhã </li>
     </ul>
     </p> </td>
  </tr>
 </tbody>
</table>