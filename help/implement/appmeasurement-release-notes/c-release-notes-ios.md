---
description: Notas de versão cumulativas para iOS.
solution: Analytics,Experience Cloud
subtopic: Release notes
title: iOS
topic: Developer and implementation
uuid: cc98f8f2-f619-4b31-abf9-e43f4deac64f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# iOS{#ios}

Notas de versão cumulativas para iOS.

> [!NOTE] Observação: para encontrar a versão atual da biblioteca, acione o log de depuração.

Os downloads da biblioteca móvel estão disponíveis no [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) e no [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-ios).

[Documentação 4.x](https://marketing.adobe.com/resources/help/pt_BR/mobile/ios/)

[Documentação 3.x](https://marketing.adobe.com/resources/help/pt_BR/sc/appmeasurement/ios/)

## Versão 4.13.4 {#section_BF05D33CEF6E42358C8089441449449B}

O SDK versão 4.13.4 (16 de fevereiro de 2017) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_657D643E874D47C099F2F43519C9C1C7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensagens no aplicativo </p> </td> 
   <td colname="2"> <p> Corrigido um problema que impedia que a versão adequada do aplicativo fosse usada ao determinar um público-alvo. Essa falha ocorria ao atualizar uma versão de aplicativo sem inicializar a Vida útil. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Aquisição </p> </td> 
   <td colname="2"> <p> Adicionado um atraso de três segundos antes de fazer chamadas API para dados Apple Search Ad nas instalações do aplicativo (de acordo com as recomendações da documentação). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.13.3 {#section_39618D2B29F942FCBF37E4F5507AA131}

O SDK versão 4.13.3 (19 de janeiro de 2017) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_341D35BF18714139A95CA5491899185D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensagens no aplicativo </p> </td> 
   <td colname="2"> <p> Agora você pode desativar mensagens de tela inteira quando o VoiceOver estiver sendo executado. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> Aprimorada a gestão do acesso a bancos de dados de somente leitura. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Geral </p> </td> 
   <td colname="2"> <p> Corrigido o problema que gerava uma falha ao tentar usar um método de rastreamento do plano de fundo durante o uso de Grupos de aplicativos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.13.2 {#section_CB0DFFDB38FE4D14A84423DF40BF8FD3}

O SDK versão 4.13.2 (10 de novembro de 2016) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_AA26B14D271948FFBA44D4D06E3B71AA"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Visitor ID  Serviço de </p> </td> 
   <td colname="2"> <p> Adicionados carimbo de data e hora e ID de empresa da Experience Cloud ao parâmetro <code> adobe_mc</code>. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Configuração </p> </td> 
   <td colname="2"> <p> Os IDFAs inválidos (00000000-0000-0000-0000-000000000000) passados ao SDK por meio de <code> setAdvertisingIdentifier:</code> serão ignorados. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Deep Linking </p> </td> 
   <td colname="2"> <p>Ao chamar <code> trackAdobeDeepLink</code>, as variáveis com prefixos "<code> adb</code>" e "<code> ctx</code>" agora são manipuladas corretamente. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Aquisição </p> </td> 
   <td colname="2"> <p>Os dados do Search Ads da Apple agora serão enviados junto aos seus dados de aquisição. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.13.1 {#section_18C8A7166EFD4E67AC0F7C06DFBBFE6A}

O SDK versão 4.13.1 (20 de outubro de 2016) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_5B67A6B8B79D4783BA8DCDA7C2ACA765"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Aquisição </p> </td> 
   <td colname="2"> <p> O SDK agora oferece suporte para que a aquisição de dados personalizada seja retornada adequadamente por invocações <code> AdobeDataCallback</code>. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> <p><span class="keyword"></span>Os parâmetros de Serviço de ID de visitante agora são passados em solicitações do <span class="keyword">Target</span> via <code> mboxParams</code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Correções de erros**

* Corrigido um problema que gerava uma falha ao tentar sincronizar uma nova ID ao serviço de ID de visitante enquanto ocorrências de rastreamento eram enviadas para o [!DNL Adobe Analytics].
* Correção de um problema que estava causando avisos de criação ao direcionar versões [!DNL iOS] anteriores a 8.

## Versão 4.13.0 {#section_F72A3357994E4887A9F3967F0FBFFCDD}

O [!DNL iOS] SDK versão 4.13.0 (15 de setembro de 2016) inclui as seguintes alterações:

<table frame="all" colsep="1" rowsep="1" id="table_FD6156E58FF54BA2BEED7398BC780C46"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensagens no aplicativo </p> </td> 
   <td colname="2"> <p>Novo recurso: adicionado um novo tipo de mensagem que abre um URI de deep link. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.12.0 {#section_2AD26AABBB434833AE961C8D71C9AFE8}

O SDK versão 4.12.0 (18 de agosto de 2016) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_CC3CD01203ED4BDA9BC26427E925C70D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Visitor ID  Serviço de </p> </td> 
   <td colname="2"> <p> Adicionado um novo método para anexar a identidade do visitante a um URL fornecido, para que a identidade possa ser transferida para uma implementação com base na web. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensagens no aplicativo </p> </td> 
   <td colname="2"> <p>Corrigido um problema que causava um travamento ao definir o atributo "target" como "_blank" em uma tag de HTML em uma mensagem personalizada de tela cheia. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.11.0 {#section_3ABABE0F0B964EB48BD482CCE260A13D}

O SDK versão 4.11.0 (22 de junho de 2016) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_14B23402BA3B41238F419CA57341B8F5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos do Target </p> </td> 
   <td colname="2"> <p>Agora você pode usar o novo método do <span class="keyword">Target</span> a seguir: </p> <p> 
     <ul id="ul_93CDE46E39C9431DA9104664F175708B"> 
      <li id="li_903FAC68526B4B7CB6555DC577CE493A"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.10.0 {#section_F0D6D7FD89DE4DF5A121B05FA093CC5B}

O SDK versão 4.10.0 (20 de maio de 2016) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_AC447B6E4D55489F803923BF5D1D6653"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos do Target </p> </td> 
   <td colname="2"> <p>Agora você pode usar os novos métodos do <span class="keyword">Target</span> a seguir: </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback:</code> </li> 
      <li id="li_C0FADBB3CEE141AE951CBD49F3A52642"><code> targetThirdPartyID</code> </li> 
      <li id="li_3E1B3725D9EE4ECE9DB0EB1A9E7682A4"><code> targetSetThirdPartyID:</code> </li> 
      <li id="li_659E295610F541819DD7486FC5177012"><code> targetPcID</code> </li> 
      <li id="li_B00ADCF98B6D4694BB7664DB42CDFF99"><code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos TVJS </p> </td> 
   <td colname="2"> <p>Agora você pode usar os novos métodos TVJS do <span class="keyword">Target</span>: </p> <p> 
     <ul id="ul_AED76A2B99534CF3A472AC0381B2618C"> 
      <li id="li_AA731652996C4A19A8E02D5D6B8BDC93"><code> targetThirdPartyID</code> </li> 
      <li id="li_744A63A62A8045E49C75F9D7AED5D75E"><code> targetSetThirdPartyID</code> </li> 
      <li id="li_72BC8D96FE0549A695D90B924FA80A02"> <code> targetPcID</code> </li> 
      <li id="li_FB7A9435B9994DB89FA80C2B2218C047"> <code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Adobe Target para TVML/TVJS </p> </td> 
   <td colname="2"> <p>Agora você pode usar os seguintes nomes de propriedade ao configurar seu elemento <code> ADBTarget</code>: </p> <p> 
     <ul id="ul_A0CEE891AE644B47ABD6F7425ACD464D"> 
      <li id="li_2EB0C3CA52014F45BA1EC07703E821B8"><code> id</code> </li> 
      <li id="li_069D996CED534EE88A1EC82684E470D5"><code> total</code> </li> 
      <li id="li_97F290C03FFD46B8A1E78B7BF2021F55"> <code> purchasedProductIds</code> </li> 
      <li id="li_FAAC4BB12DF9491DA21F161711A7707D"> <code> mboxParameters</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.9.0 {#section_DA97D7294B214067A4904B9738450759}

O SDK versão 4.9.0 (5 de maio de 2016) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_0B3A0F44549C4DA48C7639048C030065"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Deep linking </p> </td> 
   <td colname="2"> <p>Você pode implementar deep links em seus aplicativos com o objetivo de direcionar os usuários para aplicativos ou links da Web. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.8.6 {#section_0150641B44CF4F6CBE2B21002F8EAB30}

O [!DNL iOS] SDK versão 4.8.6 (9 de março de 2016) inclui as seguintes alterações:

<table frame="all" colsep="1" rowsep="1" id="table_5175CFFCA30B4DDBACFB23532111CB8A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Rastreamento de falhas do aplicativo </p> </td> 
   <td colname="2"> <p>O <span class="keyword"> iOS </span> SDK versão 4.8.6 contém alterações críticas que impedem que sejam relatadas falhas falsas. Recomendamos que você atualize para a versão 4.8.6. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.8.5 {#section_F42EB64F91024748893E89575F2E4487}

O [!DNL iOS] SDK versão 4.8.5 (18 de fevereiro de 2016) inclui as seguintes alterações:

<table frame="all" colsep="1" rowsep="1" id="table_AB225AF04A374421BDD8A972506ACD06"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Configurações de saída e privacidade </p> </td> 
   <td colname="2"> <p>A partir do <span class="keyword">iOS</span> SDK 4.8.5, as configurações de privacidade definidas por meio do método <code> setPrivacyStatus</code> afetam a atividade do <span class="keyword">Analytics</span>, do <span class="keyword">Target</span> e do <span class="keyword">Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.8.0 {#section_2CF142C8C2D24B529559DAF76F851BBF}

O SDK versão 4.8.0 (2 de novembro de 2015) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_9DB41F070D66498FACF1A9C135603C7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Novos métodos de serviço de ID do visitante da Experience Cloud </td> 
   <td colname="2"> <p>Os novos métodos abaixo foram adicionados: </p> 
    <ul id="ul_55D8F29ADE3746C484FEC7893FA9EF23"> 
     <li id="li_19F8AF546EEB45EBB5849EA6EB3CE6A3"><code> visitorSyncIdentifiers:authenticationState:</code> </li> 
     <li id="li_1AF1CF62B3ED442D81B438ECBF981583"><code> visitorSyncIdentifierWithType:identifier:authenticationState: </code> </li> 
     <li id="li_C116F0DA8E2A449A8B76637961C2100C"><code> visitorGetIDs</code> </li> 
    </ul> <p>Alteração do <code> visitorSyncIdentifiers:identifiers</code> método para <code> visitorSyncIdentifiers:</code> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Novos métodos TVJS </td> 
   <td colname="2"> <p>Os novos métodos abaixo foram adicionados: </p> 
    <ul id="ul_4C7F4BB1CF744444ABAA9F13BA98749E"> 
     <li id="li_5DAB089D115843CCA0A53873D6D676F0"><code> visitorSyncIdentifiersAuthenticationState</code> </li> 
     <li id="li_EDE2D1301E8648DB88A18D8C9F6A22C5"><code> visitorSyncIdentifierWithTypeIdentifierAuthenticationState</code> </li> 
     <li id="li_2CCED3C707774597934A2F08BC690B15"><code> visitorGetIDsJs</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Novas variáveis de configuração ADBMobile JSON  </td> 
   <td colname="2"> <p>A variável abaixo foi adicionada: </p> 
    <ul id="ul_95065BC06FD540D2937D11111799F77F"> 
     <li id="li_7C8C68A41FBA4D098D6803E71D4CCF7A"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.7.0 {#section_B37B1CAF065346E9A2073A06AB7AFEC2}

O [!DNL iOS] SDK versão 4.7.0 (15 de outubro de 2015) inclui as seguintes alterações:

<table frame="all" colsep="1" rowsep="1" id="table_3CCA327B859B498D828B2E056A075BEC"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Suporte para tvOS </td> 
   <td colname="2"> <p>O tvOS é compatível com Apple TV. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Suporte para App Transport Security </td> 
   <td colname="2"> <p>A partir do <span class="keyword"> iOS</span> 9, a Apple apresentou o App Transport Security, um conjunto de requisitos que cumpre as práticas recomendadas para conexões seguras. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Métodos de plugin do PhoneGap</span> </p> </td> 
   <td colname="2"> <p>Os novos métodos abaixo foram adicionados: </p> <p><b>Configuração de métodos</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Métodos de rastreamento</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">trackPushMessageClickthrough </li> 
     </ul> </p> <p>Novos métodos do Target: </p> <p> 
     <ul id="ul_E6A481FCD49D4CF48A4B0636312FCD19"> 
      <li id="li_6604FBB05C4E4988A04CB376D6667C79">targetClearCookies </li> 
     </ul> </p> <p><b>Métodos de aquisição</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Métodos do Audience Manager</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>Métodos do Serviço de ID de visitante</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> <p><b>Extensões de aplicativos e métodos do Apple Watch</b> </p> <p> 
     <ul id="ul_66B1E1AC4A6D4970B0C77A46EA14ABA7"> 
      <li id="li_1EA7A063FED04E0585D463837A7555CE">setAppGroup </li> 
      <li id="li_5869EAB018C94EE4AC28B3EE62D9F0EF">syncSettings </li> 
      <li id="li_983A98CAEBAD404EBCE1D70CB0B52BA3">initializeWatch </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.6 {#section_D091872501DA49C1A18CDC33C84B8256}

O SDK versão 4.6 (17 de setembro de 2015) inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_084C27B1A75A4A2EB84822242E37ED35"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Mensagens de push para segmentos do <span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p>  O <span class="keyword">Adobe Mobile Services</span> e o SDK do <span class="keyword">Adobe Mobile</span> permitem enviar mensagens de push para segmentos do <span class="keyword">Analytics</span>. O SDK também permite reportar com facilidade os usuários que abriram seu aplicativo como resultado da abertura da mensagem de push. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Métodos de aquisição </p> </td> 
   <td colname="2"> <p>Permite aos desenvolvedores iniciar uma campanha de aquisição de aplicativo como se o usuário tivesse clicado em um link. Isso é útil para criar links de aquisição manuais e manipular o redirecionamento da app store. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Postbacks </p> </td> 
   <td colname="2"> <p>Os postbacks permitem enviar os dados coletados pelo SDK a um servidor separado de terceiros. Ao utilizar os mesmos disparadores e características usadas para exibir uma mensagem no aplicativo, é possível configurar o SDK para enviar dados personalizados a um destino de terceiros. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Identificadores </p> </td> 
   <td colname="2"> <p>Os seguintes identificadores foram adicionados: </p> <p> 
     <ul id="ul_22EF89556F6B481ABE0D1B9C5EE70B55"> 
      <li id="li_C41F6FAC0B334B89B8B5D1A517CA2301"> <code> setPushIdentifier</code> </li> 
      <li id="li_B7893FB0453340EDB4290BC0B47BF096"><code> setAdvertisingIdentifier</code> </li> 
      <li id="li_85EF5F2B8837497B90F782946283622E">O <code> trackPushMessageClickThrough</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Suporte para WatchKit no WatchOS 2 </p> </td> 
   <td colname="2"> <p>Adicionado suporte para WatchKit no WatchOS 2. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.5 {#section_53DFAF8CFD614F69B3168014EF84DE9F}

O SDK versão 4.5 inclui as seguintes alterações:[!DNL iOS]

<table frame="all" colsep="1" rowsep="1" id="table_A69D0B8DA45348B8A5D6A014126F97C2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Extensão para iOS</span> </p> </td> 
   <td colname="2"> <p>A partir do <span class="keyword"> iOS</span> SDK versão 4.5, uma nova extensão do <span class="keyword"> iOS</span> permite coletar dados de uso no Apple Watch Apps, Today Widgets, Photo Editing widgets e todos os outros aplicativos de extensão do <span class="keyword"> iOS</span>. </p> <p>Recomendamos o uso do <span class="keyword"> iOS</span> SDK em vez do seu próprio kit. </p> <p>A Apple oferece um conjunto de APIs que permitem a comunicação do aplicativo Watch com o aplicativo que contém a API (enviando solicitações para o aplicativo que contém a API e depois recebendo respostas). </p> <p>Embora você possa enviar dados de rastreamento como um dicionário do aplicativo Watch para o aplicativo que contém a API e depois chamar qualquer método de rastreamento no aplicativo que contém a API para enviar dados, essa solução possui algumas limitações. </p> <p>Na maioria dos casos, quando um usuário está usando o aplicativo Watch, o aplicativo que contém a API está sendo executado em segundo fundo e só é seguro chamar <code> TrackActionInBackground</code>, <code> TrackLocation</code> e <code> TrackBeacon</code>. O uso de outros métodos de rastreamento interfere nos dados do ciclo de vida, por isso você deve usar apenas esses três métodos para enviar os dados do aplicativo Watch. </p> <p>Mesmo que esses três métodos de rastreamento atendam aos seus requisitos, recomendamos usar o <span class="keyword"> iOS</span> SDK, pois o SDK para o aplicativo Watch inclui todos os recursos <span class="keyword"> Móveis</span>, exceto mensagens no aplicativo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.4 {#section_0B7A98761BF0400986C368E154A3B00B}

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Dados personalizados com medições de ciclo de vida </p> </td> 
   <td colname="2"> <p>Agora é possível incluir variáveis de dados de contexto personalizados com medições de ciclo de vida. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword">Suporte para monitoramento de beacon no PhoneGap </span> </p> </td> 
   <td colname="2"> <p>As chamadas <code> trackBeacon</code> e <code> clearCurrentBeacon</code> agora estão disponíveis no <span class="keyword">PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.3 {#section_0FD2B2C4F54E4A9E8C6D0CD2F103BB9A}

Data de lançamento: **24 de novembro de 2014**

* Novo - Integração da Adobe Experience Cloud ID
* Registros de depuração aprimorados para maior transparência

## Versão 4.2 {#section_806710F7720C410DAB46376C0A7A283E}

Data de lançamento: **16 de outubro de 2014**

* Novo - Recursos para mensagens no aplicativo.
* Novo - Agora o local do arquivo de configuração pode ser definido durante a inicialização do aplicativo.
* Novo - Agora os Pontos de interesse podem ser atualizados automaticamente sem que um novo arquivo de configuração seja necessário.
* Novo - [!DNL Analytics] As chamadas de análise agora são enviadas como solicitações HTTP POST.
* As mensagens de registro foram limpas, e registros mais completos foram adicionados para situações nas quais a opção debugLogging estiver ativada.
* Diversas melhorias no desempenho e na estabilidade.

## Versão 4.1.3 {#section_8D679B676F604E0B9A64748569185368}

Data de lançamento: **18 de setembro de 2014**

* Solução da falha que poderia ocorrer se a chamada do Audience Manager Submit Signal ou a chamada do Load Request [!DNL Target] falhasse devido a um erro de rede desconhecido.

## Versão 4.1.2 {#section_6128902E5AE142C4A95D2FB3053188F8}

Data de lançamento: **5 de agosto de 2014**

* Solucionado o problema de bloqueio que ocorria com a configuração específica de privacyStatus:optunknown e offlineEnabled:false

Data de lançamento: **4 de agosto de 2014**

* Solucionado o problema que fazia com que a ocorrência do Lifecycle não fosse enviada quando o tempo limite do referenciador era maior ou igual a 5 segundos e quando o monitoramento offline estava desativado.

Data de lançamento: **17 de abril de 2014**

* Monitoramento de beacon de Bluetooth.
* Análise de aquisição do aplicativo.
* Aplicativos que são ativados por carimbo de data e hora, ocorrências de falhas pré-datadas para a sessão correta.
* Aplicativos que são ativados por carimbo de data e hora, sessão anterior enviada em uma ocorrência que é pré-datada para a sessão correta. (sem a versão anterior)
* Agrupamento de hits.

## Versão 4.0.2 {#section_B78AE82CDFAD44DCAC6D61E0B80BF4C8}

Data de lançamento: **20 de fevereiro de 2014**

* Solucionado o problema que gerava um comportamento incorreto quando o mesmo item de mídia era aberto em sequência sem fechar o item anterior.

## Versão 4.0.1 {#section_A6D017015BC742F69B6EE4A461D00FD7}

Data de lançamento: **30 de janeiro de 2014**

* Solucionado o problema que fazia com que várias ocorrências fossem enviadas quando a base de dados estava corrompida.
* Solucionado o problema que gerava grandes médias para a duração de uma sessão se o dispositivo estivesse com configurações de data e hora incorretas.

## Versão 3.3.2 {#section_6D12768F20C44BA4A0D1EA607D367147}

Data de lançamento: **30 de janeiro de 2014**

* Solucionado o problema que gerava grandes médias para a duração de uma sessão se o dispositivo estivesse com configurações de data e hora incorretas.

## Versão 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Data de lançamento: **27 de setembro de 2013**

[!DNL iOS] SDK 4.x para Soluções da Experience Cloud está disponível e oferece estes novos recursos:

* Melhorias significativas no desempenho. Todo o processo é realizado nas ameaças em segundo plano e o SDK é totalmente à prova de ameaças.
* Localização geográfica e pontos de interesse
* Valor histórico
* Eventos agendados
* Gerenciamento de participação/não participação
* Suporte ao Audience Manager
* As medições de ciclo de vida foram passadas para o como parâmetros mbox[!DNL Target]
* Padronização dos dados de contexto e das regras de processamento

## Versão 3.3.0 {#section_28FB7CD64D6C49BF93E321587F1E8950}

Data de lançamento: **23 de setembro de 2013**

* Adicionado suporte para arquiteturas ARM64 e X64 Simulator (iPhone 5s)

## Versão 3.2.1 {#section_3E73A76401664C54B32C7F3BE8BE36E3}

Data de lançamento: **16 agosto de 2013**

* Otimizado por conta da remoção do código não utilizado.
* Solucionada a falha que ocorria quando um clearVars era usado em um cenário ameaçado.

## Versão 3.2 {#section_A51E0EB26EF246DABE27234C77598D99}

Data de lançamento: **6 agosto de 2013**

* Suporte adicionado para o Adobe Audience Manager.
* Agora os dados do ciclo de vida são enviados com solicitações Mbox [!DNL Target] quando o rastreamento do ciclo de vida está desativado.

## Versão 3.1.8 {#section_849BCD1D4379433D874B8A0E0099E2B1}

Data de lançamento: **20 de junho de 2013**

* Correção de um bug introduzido no 3.1.7 que estava causando problemas com o ciclo de vida nos dispositivos anteriores ao [!DNL iOS] 5.0.

## Versão 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

Data de lançamento: **23 de maio de 2013**

* Adicionado um código para evitar que ocorrências de ciclos de vida excessivos fossem enviadas por meio de notificações de local e notificações Newsstand que iniciavam um aplicativo.

## Versão 3.1.6 {#section_4617D7A41D0841BEBD5829001DC74854}

Data de lançamento: **18 de abril de 2013**

* Solucionado o problema que fazia com que a duração de uma sessão anterior fosse calculada incorretamente algumas vezes.

## Versão 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

Data de lançamento: **21 março de 2013**

* O`ADMS_Measurement.visitorID` agora fica pré-preenchido com o valor padrão.

## Versão 3.1.4 {#section_B04D1A4858A84A19AA65A57609C9F53F}

Data de lançamento: **21 de fevereiro de 2013**

* Não é mais necessário desaprovar `offlineThrottleDelay` como configuração devido à otimização de discussão. A configuração ainda existe para preservar a compatibilidade anterior, mas não tem mais efeito.

## Versão 3.1.3 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Data de lançamento: **novembro de 2012**

* Solucionado um problema com o EXEC_BAD_Access durante a configuração manual da variável Produtos.
* Corrigida uma falha com o seletor inválido quando o tempo da mbox era encerrado.
* Adicionado um suporte para monitoramento para medição de mídia.

## Versão 3.1.2 {#section_25C8A6B67AB9487BA5DEB4DB196AE4BC}

Data de lançamento: **outubro de 2012**

* Adição de uma variável de configuração `lifecycleSessionTimeout` a qual permite que você especifique a duração, em segundos, entre a inicialização do aplicativo antes que possa ser considerada uma nova sessão.
* Correção do problema no módulo de mídia que resultava na substituição de eventos configurações pelo módulo de mídia por eventos configurados no objeto de medição.
* Correção de um problema que causava uma exceção ao alocar uma mbox por meio da integração [!DNL Target].

## Versão 3.1.0 {#section_0F3E939885DE4DF1B7430DF5F5749AD2}

Data de lançamento: **setembro de 2012**

* Suporte à arquitetura armv7s adicionado
* Suporte à arquitetura armv6 removido
* Agora o [!DNL iOS] SDK mínimo suportado é 4.3

## Versão 3.0.2 {#section_1224693620524D6C8CCAB7707483536E}

Data de lançamento: **agosto de 2012**

* Os cliente que usam o monitor de mídia para delegar não verão dois eventos de fechar
* Solução do problema em que ocorrências da ação de fechar resultavam em uma condição de ciclo no monitor de mídia

## Versão 3.0 {#section_D28F56359EC04EDC8521BE93750AE90D}

Data de lançamento: **julho de 2012**

Versão inicial.

**Aprimoramentos**

* Funcionalidade de "rastreamento automático" adicionada
* Biblioteca reduzida para aprox. 90k na versão final.
* Métodos "trackEvents" e "trackAppState" adicionados
* Melhora do suporte a da funcionalidade dos dados de contexto. (Recomendação: uso de dados de contexto para todas as informações enviadas)
* Rastreamento simplificado, portanto, uma implementação de rastreamento básica pode ser executada em 5 minutos.

**Alterações**

* [!DNL AppMeasurement]A classe agora é ADMS_Measurement
* Agora, ADMS_Measurement atua como um Singleton apropriado
* Alteração de getters e setters para eVars, props, listas, hiers, pevs
* Todas as variáveis passadas para chamadas de "rastreamento" persistirão somente para essa chamada.

**As seguintes variáveis foram modificadas**

| Versão anterior (2.x) | Versão atual (3.x) |
|---|---|
| account | reportSuiteIDs |
| dc | dataCenter |
| pageName | appState |
| contextData | persistentContextData |
| state | geoState |
| zip | geoZip |
| servidor | appSection |
| debugTracking | debugLogging |
| trackOffline | offlineTrackingEnabled |
| offlineLimit | offlineHitLimit |
| OfflineThrottleDelay | offlineThrottleDelay |

**As seguintes variáveis foram reaproveitadas:**

* linkURL (enviado com trackLinkURL:)
* linkName (enviado com trackLinkURL:)
* linkType (enviado com trackLinkURL:)
* lightProfileID (enviado com trackLight:)
* lightStoreForSeconds (enviado com trackLight:)
* lightIncrementBy (enviado com trackLight:)
* trackingServerSecure (trackingServer é usado quando ssl está ativado)

**As seguintes variáveis foram removidas:**

* timestamp
* userAgent
* dynamicVariablePrefix
* visitorNamespace
* pageURL
* pageType
* referenciador
* linkLeaveQueryString
* usePlugins
* useBestPractices (tratado por AutoTracking)
* delegate
* retrieveLightData
* deleteLightProfiles
* retrieveLightProfiles

## Versão anterior do iOS (2.x)  {#section_5F76C3DA854D4BAEA636A68B3811142B}

As seguintes notas de versão se aplicam à versão 2.x do [!DNL AppMeasurement] para [!DNL iOS]. Nós recomendamos que os clientes atualizem para a versão 3.x quando possível.

## Versão 2.1.12 {#section_85C073B86B684D52A14E8038379F56DD}

Data de lançamento: **abril de 2012**

* Suporte adicionado para medição de vídeo do.
* Solução de problemas de linktrackvars e dados de contexto.
* Várias melhorias de desempenho adicionais.

## Versão 2.1.11 {#section_F0AF2D4E5F504D798EEB95BE8FE61B4C}

Data de lançamento: **março de 2012**

* Correção de um problema que fazia com que o rastreamento offline parasse de enviar dados em algumas circunstâncias.

## Versão 2.1.10 {#section_07C24EC83AA94A6AA6AB3DE7E8D6227F}

Data de lançamento: **fevereiro de 2012**

* Correção de um problema que causava uma exceção EXC_BAD_ACCESS em algumas circunstâncias, ao multiplicar threads tentadas e, simultaneamente, criar uma chamada de rastreamento.
* Adição de carimbo de data/hora a variáveis usadas com chamadas de faixas de luz (trackLight).

## Versão 2.1.8 {#section_ACC6974CE3F741E58786CA8048F04521}

Data de lançamento: **janeiro de 2012**

* O desempenho do encadeamento de rastreamento foi significativamente aumentado.
* O armazenamento de ocorrências offline foi movido para um local que não é sincronizado com o iCloud, em conformidade com as práticas recomendadas do iCloud.
* A biblioteca foi atualizada para o formato binário FAT da Apple, o que evita a necessidade de incluir a biblioteca específica para sua arquitetura de compilação.

## Versão 2.1.6 {#section_63B4967C537847C28D33EBB92CC15695}

Data de lançamento: **novembro de 2011**

* Adição de suporte para [!DNL iOS] 5.
* [!DNL AppMeasurement]O for [!DNL iOS] foi atualizado para não mais usar o valor UDID deprecado como o valor padrão do visitorID. Se você definir um visitorID personalizado em seu aplicativo (por exemplo, `s.visitorID = @12345`), então você não será afetado por essa alteração. Se você não definir um visitorID personalizado, em vez de usar um UDID como valor para o visitorID, um visitorID é gerado aleatoriamente no início e, em seguida, armazenado em uma tecla padrão do usuário. Essa chave será usada pelo [!DNL AppMeasurement] desse ponto em diante. Essa tecla também é salva e restaurada durante o processo de backup padrão do aplicativo.

* Atualização das chamadas do plug-in de Práticas recomendadas do [!DNL iOS] não estão associadas a uma exibição de página para enviar hits usando trackLink. Isso ajuda a impedir que essas ocorrências gravem exibições de páginas com o valor padrão com o nome "nome do aplicativo/versão".

## Versão 2.1.3 {#section_E39666D780554B7398900C39C285CDB8}

Data de lançamento: **outubro 2011**

* Manuseio de delegação aprimorado. Isso corrige um problema que causava uma falha do plug-in de Práticas recomendadas do [!DNL iOS] ao tirar o aplicativo do fundo.

## Versão 2.1.2 {#section_21014073AF804EFC8231047D8847485C}

Data de lançamento: **setembro de 2011**

* Atualização do cabeçalho para permitir o uso de prop e eVar 51-75.

## Versão 2.1.1 {#section_8FB3D7C77C884E2AB982103BF7E3312A}

Data de lançamento: **agosto de 2011**

* A capacidade de pesquisar por conjuntos de relatórios e métricas ao executar um relatório.
* Suporte a dados de contexto que direciona as regras de processamento do lado do servidor (v15 somente).
* Suporte para chamadas de servidor leves (em beta).

