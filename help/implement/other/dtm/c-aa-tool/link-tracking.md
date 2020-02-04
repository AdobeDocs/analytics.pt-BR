---
description: Descrições de campo no Dynamic Tag Management para rastreamento de links ao implantar o Analytics.
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Rastreamento de link
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Rastreamento de link

Descrições de campo no Dynamic Tag Management para rastreamento de links ao implantar o Analytics.

**[!UICONTROL *`Property`*]**> **[!UICONTROL![](assets/settings_gear.png)

Editar ferramenta]** > **[!UICONTROL Rastreamento de link]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Elemento </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ativar o ClickMap </td>
   <td colname="col2"> <p>Determina se os dados do mapa de cliques do visitante estão reunidos. </p> <p>Consulte [trackInlinestats](../../../vars/config-vars/trackinlinestats.md). </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Rastrear os links de download </td>
   <td colname="col2"> <p>Rastreia os links até arquivos baixáveis no site. </p> <p>Consulte [trackDownloadLinks](../../../vars/config-vars/trackdownloadlinks.md).</p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Baixar de extensões </td> 
   <td colname="col2"> <p>Se o site contém links para arquivos com qualquer uma das extensões listadas, as URLs desses links aparecem no relatório. </p>Consulte [linkDownloadFileTypes](../../../vars/config-vars/linkdownloadfiletypes.md). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Rastrear links externos </td>
   <td colname="col2"> <p>Determina se um link clicado é um link de saída. </p> <p>Consulte [trackExternalLinks](../../../vars/config-vars/trackexternallinks.md). </p> <p><b>Considerações sobre aplicativos de página única:</b> Devido ao modo de codificação dos sites de SPAs, um link interno para uma página no site de SPA pode parecer externo. </p> <p>Use um dos métodos a seguir para rastrear links externos de sites de SPA: </p>
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9">
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Se não quiser rastrear nenhum link externo do SPA, insira uma entrada na seção <span class="wintitle">Nunca rastrear</span>. </p> <p>Por exemplo, <span class="filepath">https://testsite.com/spa/#</span> </p> <p>todos os links # para esse host são ignorados. Todos os links externos para outros hosts são rastreados, como <span class="filepath">https://www.google.com</span>. </p> </li>
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>Se houver links que você queira rastrear no seu SPA, use a seção <span class="wintitle">Rastrear sempre</span>. </p> <p>Por exemplo, em uma página <span class="filepath">spa/#/about</span>, você pode colocar "about" na seção <span class="wintitle">Rastrear sempre</span>. </p> <p>A página "about" (sobre) será o único link externo rastreado. Nenhum outro link da página (por exemplo, <span class="filepath">https://www.google.com</span>) será rastreado. </p> </li>
    </ul> <p>Observe que essas duas opções são mutuamente exclusivas. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> Manter parâmetros de URL </td>
   <td colname="col2"> <p>Preserva as sequências de consulta. </p> <p>Consulte [linkLeaveQueryString](../../../vars/config-vars/linkleavequerystring.md). </p> </td>
  </tr>
 </tbody>
</table>
