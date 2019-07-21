---
description: 'null'
seo-description: 'null'
seo-title: Roteiro de implementação
title: Roteiro de implementação
uuid: 988 bcca 5-67 ae -4 e 3 f -97 e 6-6 a 42030 b 1962
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Roteiro de implementação

## Novos usuários {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

Se você não estiver familiarizado com o Adobe Analytics, poderá criar rapidamente seu primeiro conjunto de relatórios (repositório de dados) do Analytics usando o guia [Introdução ao Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/). Then, you can deploy Analytics code using [Experience Platform Launch](https://docs.adobelaunch.com/).

## Roteiro de implementação {#section_E3DD8D199B744FFB9E9B386A44220206}

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Etapa </th> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Escolha um método de implementação. </td> 
   <td colname="col2"> <p>As formas mais comuns de implementar o Analytics incluem: </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/" format="https" scope="external"> Lançamento da plataforma de experiência </a> (recomendado) <p>Este guia informa tudo o que você precisa saber sobre o uso dos recursos de gerenciamento de SDKs móveis e tags de site da Adobe e como implementá-los. </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="../../implement/c-implement-with-dtm/dtm-implementation-overview.md" format="dita" scope="local">Dynamic Tag Management</a> <p>Este guia contém informações específicas do Analytics para orientá-lo pela implementação do Dynamic Tag Management. </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="../../implement/js-implementation/javascript-implementation-overview.md" format="dita" scope="local"> JavaScript </a> <p>Este guia contém uma descrição das variáveis de coleta de dados e detalhes sobre a implementação do código da coleta de dados em JavaScript, incluindo <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js" format="https" scope="external">vídeo </a>. </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="html" scope="external"> SDKs do Analytics </a> <p>Use os SDKs do Analytics para gerenciar: </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html" format="html" scope="external"> Aplicativos para dispositivos móveis no iOS </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html" format="html" scope="external"> Aplicativos para dispositivos móveis no Android </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configure o Serviço de identidade. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>Em <code>VisitorAPI.js</code>, adicione o seguinte código de inicialização de ID de visitante no início do arquivo: </p> 
     <code class="syntax javascript">var visitor = Visitor. getinstance ("INSERT-MCORG-ID-HERE"); 
 visitor. trackingserver = "INSERT-TRACKING-SERVER-HERE"; // da mesma forma que s. trackingserver 
 visitor. trackingserversecure = "INSERT-SECURE-TRACKING-SERVER-HERE"; //same como s. trackingserversecure 
 /* 
 = = = = = = = = = = = = = = NÃO ALTERE NADA ABAIXO DESTA LINHA! = = = = = = = = = = = = = </code>
  
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> " INSERT-MCORG-ID-HERE " </code> - (obrigatório) Essa ID de empresa da Adobe Experience Cloud é enviada para o administrador quando sua empresa for provisionada para a Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE"</code>: (Obrigatório) Seu servidor de rastreamento do Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE"</code> - (obrigatório se ssl estiver habilitado) Seu servidor de rastreamento seguro do Analytics. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Use o método de implementação escolhido para atualizar e implantar o código de página. </td> 
   <td colname="col2"> <p>Copie o Exemplo de código da página e cole-o depois de abrir a tag <code>&lt;body&gt;</code> em cada página que você deseja rastrear. No mínimo, atualize as seguintes variáveis: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // por exemplo, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Valide a implementação. </td> 
   <td colname="col2"> <p> <a href="../../implement/impl-testing/impl-validation/impl-validation.md" format="dita" scope="local"> Teste e validação</a> fornece informações sobre como validar a implementação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Use o Adobe Experience Cloud Debugger para verificar se os dados estão sendo enviados. </td> 
   <td colname="col2"> <p>Install the <a href="../../implement/impl-testing/debugger.md#topic_E05CEAF0682E483A9AB147D774CF2188" format="dita" scope="local"> Experience Cloud Debugger </a>. Depois de instalá-lo, carregue uma página onde você implantou o código da página e abra o depurador. O depurador exibe detalhes sobre os dados de coleta enviados. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mais Informações {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

For information about the differences between [!UICONTROL Experience Platform Launch], [!UICONTROL Dynamic Tag Management], and JavaScript methods, see [Choose an Implementation Method](../../implement/c-implementation-methods/choose-implementation-method.md#concept_97CE27B16410422EB28B4B9CE3B9529B).

Para obter uma visão geral resumida do processo de primeiros passos e ajudar a configurar rapidamente seu primeiro conjunto de relatórios do Analytics, consulte [Introdução à implementação do Analytics](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) no guia Introdução ao Analytics.
