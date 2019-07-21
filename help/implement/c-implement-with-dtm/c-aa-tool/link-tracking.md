---
description: Descrições de campo no Dynamic Tag Management para rastreamento de links ao implantar o Analytics.
keywords: Gerenciamento dinâmico de tags; rastreamento de link; habilitar o clickmap; rastrear links de download; download de extensões; rastrear links externos; manter parâmetros de url
seo-description: Descrições de campo no Dynamic Tag Management para rastreamento de links ao implantar o Analytics.
seo-title: Rastreamento de link
solution: Marketing Cloud, Analytics, Gerenciamento dinâmico de tags
title: Rastreamento de link
uuid: 982 b 744 b -5696-4 c 31-b 1 d 1-410486 b 0 eedd
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# Rastreamento de link

Descrições de campo no Dynamic Tag Management para rastreamento de links ao implantar o Analytics.

**[!UICONTROL *`Property`*]** &gt;** [! UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Link Tracking]**

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
   <td colname="col2"> <p>Determina se os dados do mapa de cliques do visitante estão reunidos. </p> <p>Consulte  <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.trackInlineStats</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rastrear os links de download </td> 
   <td colname="col2"> <p>Rastreia os links até arquivos baixáveis no site. </p> <p>Consulte [Variáveis de configuração] (/help/implementation/js-implementation/c-variables/configuration-variables. md).</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Baixar de extensões </td> 
   <td colname="col2"> <p>Se o site contém links para arquivos com qualquer uma das extensões listadas, as URLs desses links aparecem no relatório. </p>Consulte [Variáveis de configuração] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rastrear links externos </td> 
   <td colname="col2"> <p>Determina se um link clicado é um link de saída. </p> <p>Consulte [Variáveis de configuração] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> <p><b>Considerações sobre aplicativos de página única:</b> Devido ao modo de codificação dos sites de SPAs, um link interno para uma página no site de SPA pode parecer externo. </p> <p>Use um dos métodos a seguir para rastrear links externos de sites de SPA: </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Se não quiser rastrear nenhum link externo do SPA, insira uma entrada na seção <span class="wintitle">Nunca rastrear</span>. </p> <p>For example, <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>todos os links # para esse host são ignorados. All outbound links to other hosts are tracked, such as <span class="filepath"> https://www.google.com</span>. </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>Se houver links que você queira rastrear no seu SPA, use a seção <span class="wintitle">Rastrear sempre</span>. </p> <p>Por exemplo, em uma página <span class="filepath">spa/#/about</span>, você pode colocar "about" na seção <span class="wintitle">Rastrear sempre</span>. </p> <p>A página "about" (sobre) será o único link externo rastreado. Any other links on the page (for example, <span class="filepath"> https://www.google.com</span>) are not tracked. </p> </li> 
    </ul> <p>Observe que essas duas opções são mutuamente exclusivas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Manter parâmetros de URL </td> 
   <td colname="col2"> <p>Preserva as sequências de consulta. </p> <p>Consulte [Variáveis de configuração] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
 </tbody> 
</table>

