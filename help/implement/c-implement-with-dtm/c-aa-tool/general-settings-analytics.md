---
description: Descrições dos campos de configurações gerais no gerenciador dinâmico de tags para implantar o Adobe Analytics.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;general settings;eu compliance;character set;currency code;tracking server;ssl tracking server
title: Geral
topic: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Geral

Descrições de campo das Configurações gerais no DTM para implantar o Adobe Analytics.

**[!UICONTROL &lt;Property&gt;]** &gt; ![](assets/settings_gear.png) **[!UICONTROL Editar ferramenta]** &gt; **[!UICONTROL Geral]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ativar a conformidade EU para o <span class="keyword">Adobe Analytics </span> </p> </td> 
   <td colname="col2"> <p> Ativa ou desativa o rastreamento com base no cookie de privacidade EU. </p> <p>Quando uma página é carregada, o sistema verifica se um cookie chamado <span class="filepath">sat_track</span> está definido (ou o nome do cookie personalizado especificado na página <span class="wintitle">Editar propriedade</span>). Considere as seguintes informações: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Se o cookie não existe, ou existe mas está configurado para qualquer item exceto <span class="term"> true </span>, o carregamento da ferramenta é ignorado quando esta configuração é habilitada. Ou seja, toda parte de uma regra que usa a ferramenta não será aplicada. </p> <p>Se uma regra tiver o Analytics com conformidade EU ativada e o código de terceiros, e o cookie estiver definido como <span class="term"> false </span>, o código de terceiros ainda será executado. Contudo, as variáveis de análise não serão definidas. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Se o cookie existe, mas está configurado como <span class="term"> true </span>, a ferramenta será carregada normalmente. </li> 
    </ul> <p>Você é responsável por definir o cookie <span class="filepath"> sat\_track </span> (ou com nome personalizado) como <span class="term"> false </span> se um visitante optar por não participar. Você pode fazer isso usando o código personalizado: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> Você também deve ter um mecanismo para definir esse cookie como <span class="term"> true </span>, se quiser que um visitante possa aceitar a participação posteriormente: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conjunto de caracteres </p> </td> 
   <td colname="col2"> <p>Exibe os conjuntos de codificação de caracteres disponíveis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de moeda </p> </td> 
   <td colname="col2"> <p>Exibe os códigos de moeda suportados para seleção. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor de rastreamento </p> </td> 
   <td colname="col2"> <p>O domínio em que a solicitação de imagem e o cookie são gravados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor de rastreamento de SSL </p> </td> 
   <td colname="col2"> <p>O domínio em que a solicitação de imagem e o cookie são gravados. Usada para páginas seguras. Se não estiver definido, os dados de SSL vão para o <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centro de dados </p> </td> 
   <td colname="col2"> <p>O centro de dados da Adobe usado para a coleção de dados. </p> </td> 
  </tr> 
 </tbody> 
</table>

