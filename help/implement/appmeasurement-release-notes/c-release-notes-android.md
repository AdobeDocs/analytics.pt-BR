---
description: Notas de versão cumulativas para a biblioteca móvel do Android.
seo-description: Notas de versão cumulativas para a biblioteca móvel do Android.
seo-title: Android
solution: Analytics,Experience Cloud
subtopic: Notas de versão
title: Android
topic: Desenvolvedor e implementação
uuid: 32232d28-3459-4f78-bb00-ca3163c63461
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Android{#android}

Notas de versão cumulativas para a biblioteca móvel do Android.

>[!NOTE]
>
>Para localizar a versão atual da biblioteca, ative o registro de depuração.

Os downloads da biblioteca móvel estão disponíveis no [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) e no [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1).

## Versão 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

The [!DNL Android] SDK version 4.13.4 (Feb 16, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Mensagens no aplicativo </p> </td> 
   <td colname="2"> <p> Corrigido um problema que impedia que a versão adequada do aplicativo fosse usada ao determinar um público-alvo. Essa falha ocorria ao atualizar uma versão de aplicativo sem inicializar a Vida útil. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Vida útil </p> </td> 
   <td colname="2"> <p> Corrigido um problema que poderia impedir que a atualização de uma versão do aplicativo fosse propriamente relatada. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Aquisição </p> </td> 
   <td colname="2"> <p> Corrigido um problema que fazia com que deep links adiados não fossem acionados na primeira inicialização. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

The [!DNL Android] SDK version 4.13.3 (Jan 19, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Mensagens no aplicativo </p> </td> 
   <td colname="2"> <p> Corrigido um problema que impedia a exibição de mensagens de alerta sem o botão de click-through. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> Aprimorada a gestão do acesso a bancos de dados de somente leitura. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Links universais </p> </td> 
   <td colname="2"> <p> Corrigido um erro que fazia com que os deep links adiados e anexados a dados de aquisição fossem disparados em inicializações sucessivas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

The [!DNL Android] SDK version 4.13.2 (Nov 10, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Serviço de ID de visitante </p> </td> 
   <td colname="2"> <p>Added timestamp and Experience Cloud Organization ID to <code> adobe_mc</code> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Deep Linking </p> </td> 
   <td colname="2"> <p>Ao chamar <code>trackAdobeDeepLink</code>, as variáveis com prefixos "<code>adb</code>" e "<code>ctx</code>" agora são manipuladas corretamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

The [!DNL Android] SDK version 4.13.1 (Oct 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Aquisição </p> </td> 
   <td colname="2"> O SDK agora oferece suporte para que a aquisição de dados personalizada seja retornada adequadamente por invocações <code>AdobeDataCallback</code>. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Aquisição </p> </td> 
   <td colname="2"> O SDK agora armazena variáveis de referenciador do Google Play e variáveis personalizadas e as retorna adequadamente por invocações <code>AdobeDataCallback</code>. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> Os parâmetros de Serviço de ID de visitante agora são passados em solicitações do <span class="keyword">Target</span> via <code>mboxParams</code>. </td> 
  </tr> 
 </tbody> 
</table>

**Correções de erros**

* Corrigido um erro que fazia com que as solicitações de dados para o telefone atingissem o tempo limite.

## Versão 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

The [!DNL Android] SDK version 4.13.0 (Sept 15, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
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
  <tr rowsep="1"> 
   <td colname="1"> <p>Rastreamento de deep links </p> </td> 
   <td colname="2"> <p>Novo recurso: adicionada a capacidade de habilitar o rastreamento de deep links adiados de terceiros. </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><code> processAdobeDeepLink</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

The [!DNL Android] SDK version 4.12.0 (Aug 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Serviço de ID de visitante </p> </td> 
   <td colname="2"> <p> Adicionado um novo método para anexar a identidade do visitante a um URL fornecido, para que a identidade possa ser transferida para uma implementação com base na web. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

The [!DNL Android] SDK version 4.11.0 (June 22, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
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
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> loadRequest</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

The [!DNL Android] SDK version 4.10.0 (May 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Métodos do Target </td> 
   <td colname="2"> <p>Adicionada uma nova sintaxe e um novo exemplo para o método <code>loadRequest</code>. </p> <p>Foram adicionados os seguintes métodos do <span class="keyword">Target</span>: </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

The [!DNL Android] SDK version 4.9.0 (May 5, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Configurações de saída e privacidade </td> 
   <td colname="2"> <p>Você pode implementar deep links em seus aplicativos com o objetivo de direcionar os usuários para aplicativos ou links da Web. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

The [!DNL Android] SDK version 4.8.3 (February 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Configurações de saída e privacidade </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> Android</span> SDK 4.8.3, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span> , and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

The [!DNL Android] SDK version 4.8.0 (November 2, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Novos métodos do Serviço de ID de visitante da Experience Cloud </td> 
   <td colname="2"> <p>Os métodos abaixo foram adicionados: </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><code> syncIdentifer</code> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><code> syncIdentifiers</code> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><code> getIdentifiers</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Novas variáveis de configuração ADBMobile JSON  </td> 
   <td colname="2"> <p>A variável abaixo foi adicionada: </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> Métodos de plugin do PhoneGap</span> </td> 
   <td colname="2"> <p>Os novos métodos abaixo foram adicionados </p> <p><b>Configuração de métodos</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Métodos do Target</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
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
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

The [!DNL Android] SDK version 4.6.1 (September 24, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android SDK versão 4.6.1</span> </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 or earlier supports <span class="keyword"> Android</span> 2.2(API 8) - <span class="keyword"> Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 or later supports <span class="keyword"> Android</span> 2.3(API 9) or later </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

The [!DNL Android] SDK version 4.6 (September 17, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p> O <span class="keyword">Adobe Mobile Services</span> e o SDK do <span class="keyword">Adobe Mobile</span> permitem enviar mensagens de push para segmentos do <span class="keyword">Analytics</span>. O SDK também permite reportar com facilidade os usuários que abriram seu aplicativo como resultado da abertura da mensagem de push. </p> </td> 
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
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><code> setPushIdentifier</code> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <code> submitAdvertisingIdentifierTask</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

The [!DNL Android] SDK version 4.5 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Recurso </th> 
   <th colname="2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Extensão portátil para Android</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> Android</span> SDK version 4.5, a new <span class="keyword"> Android</span> extension lets you collect data from your <span class="keyword"> Android</span> Wearable app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

The [!DNL Android] SDK version 4.4 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
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
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>As chamadas <code>trackBeacon</code> e <code>clearCurrentBeacon</code><span class="keyword"> agora estão disponíveis no PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

Data de lançamento: **24 de novembro de 2014**

* Novo - Integração da Adobe Experience Cloud ID
* Registros de depuração aprimorados para maior transparência
* Solucionado o problema que geralmente ocorria durante a verificação de mensagens no aplicativo

## Versão 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

Data de lançamento: **16 de outubro de 2014**

* Novo - Recursos para mensagens no aplicativo.
* Novo - Agora o local do arquivo de configuração pode ser definido durante a inicialização do aplicativo.
* Novo - Agora os Pontos de interesse podem ser atualizados automaticamente sem que um novo arquivo de configuração seja necessário.
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* Solucionado o problema que fazia com que falhas no aplicativo não fossem monitoradas em determinados cenários.
* As mensagens de registro foram limpas, e registros mais completos foram adicionados para situações nas quais a opção debugLogging estiver ativada.
* Diversas melhorias no desempenho e na estabilidade.

## Versão 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

Data de lançamento: **4 de agosto de 2014**

* Solucionado o problema que fazia com que a ocorrência do Lifecycle não fosse enviada quando o tempo limite do referenciador era maior ou igual a 5 segundos e quando o monitoramento offline estava desativado.

## Versão 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

Data de lançamento: **17 de julho de 2014**

* Adicionadas proteções sobre exceções que ocorrem caso a base de dados seja corrompida ou se não puder ser criada.
* Adicionadas proteções contra problemas que podem ocorrer quando a configuração não puder ser carregada (geralmente por conta de um contexto nulo).
* Adicionadas proteções para exceções que podem ocorrer quando os dados do contexto de uma ação programada estiverem sendo atualizados.

## Versão 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

Data de lançamento: **23 de abril de 2014**

* Solucionado o problema que geralmente ocorria se o monitoramento do referenciador estivesse ativado e uma chamada de monitoramento fosse realizada antes do ciclo de vida.

## Versão 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

Data de lançamento: **17 de abril de 2014**

* Novo - Monitoramento de beacon do Bluetooth.
* Novo - Aplicativos com carimbo de data e hora foram ativados e as ocorrências de falhas foram pré-datadas para a sessão correta.
* Novo - Aplicativos que são ativados por carimbo de data e hora, sessão anterior enviada em uma ocorrência que é pré-datada para a sessão correta. (sem a versão anterior).
* Novo - Agrupamento de ocorrências.
* Corrigido o referenciador do Google Play que monitora com um tempo limite configurável para permitir dados do referenciador google atrasados.
* Corrigidos os avisos do StrictMode que poderiam aparecer em determinados cenários.
* Solucionado o problema que raramente fazia com que a biblioteca fosse bloqueada se determinados métodos fossem colocados em uma ordem específica.

## Versão 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

Data de lançamento: **24 de fevereiro de 2014**

* Solucionado o problema que fazia com que o tempo de reprodução da mídia fosse prolongado caso fosse pausado e o encerramento ocorria com atraso, sem solicitações no meio.
* Solucionado o problema onde uma ocorrência de fechamento de mídia era enviada mesmo se a mídia não estivesse sendo reproduzida.

## Versão 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

Data de lançamento: **20 de fevereiro de 2014**

* Added safety to network code to prevent crash caused by [!DNL Android] bug: https://code.google.com/p/android/issues/detail?id=54072

## Versão 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

Data de lançamento: **30 de janeiro de 2014**

* Solucionado o problema que fazia com que várias ocorrências fossem enviadas quando a base de dados estava corrompida.
* Solucionado o problema que gerava grandes médias para a duração de uma sessão se o dispositivo estivesse com configurações de data e hora incorretas.

## Versão 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

Data de lançamento: **30 de janeiro de 2014**

* Adicionadas proteções contra bases de dados corrompidas que geram ocorrências repetidas.
* Adicionado um limite de tamanho máximo para a sessão, que evita sessões muito grandes quando os tempos dos dispositivos estão incorretos.

## Versão 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

Data de lançamento: **14 de novembro de 2013**

* Corrigida a formatação incorreta dos dados trackLocation em locais específicos.

## Versão 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Data de lançamento: **27 de setembro de 2013**

[!DNL Android] O SDK 4.x para Soluções da Experience Cloud está disponível agora, fornecendo os seguintes novos recursos:

* Melhorias significativas no desempenho. Todo o processo é realizado nas ameaças em segundo plano e o SDK é totalmente à prova de ameaças.
* Localização geográfica e pontos de interesse
* Valor histórico
* Eventos agendados
* Gerenciamento de participação/não participação
* Suporte ao Audience Manager
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* Padronização dos dados de contexto e das regras de processamento

## Versão 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

Data de lançamento: **23 de setembro de 2013**

* Corrigido o bug no Audience Manager que não permitia valores ou chaves nulas no parâmetro.

## Versão 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

Data de lançamento: **12 de setembro de 2013**

* Corrigido o bug que fazia com que os eventos de mídia de linkTrackEvents não fossem adicionados à solicitação.
* Corrigida a possível exceção relacionada à modificação do ContextData após o redirecionamento para uma chamada de monitoramento.

## Versão 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

Data de lançamento: **16 agosto de 2013**

* As conexões SSL agora usam uma validação rigorosa de host
* Corrigido o bug que fazia com que as ocorrências fossem reenviadas após apenas alguns segundos quando a conexão com a rede era perdida e o Monitoramento offline estava desativado.

## Versão 3.2 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

Data de lançamento: **6 agosto de 2013**

* Suporte adicionado para o Adobe Audience Manager.
* Os dados do ciclo de vida agora são enviados com solicitações Target Mbox quando o monitoramento do ciclo de vida está desativado.
* Solucionado um problema que fazia com que o SQLite forçasse cursos fechados, resultando em entradas desnecessárias de registros.

## Versão 3.1.0 {#section_836B4F580B1C436FABD524A91857F882}

Data de lançamento: **13 de junho de 2013**

* Atualizado o armazenamento offline para usar o SQLite.
* Corrigido o bug que fazia com que o limite offline fosse redefinido para o modo padrão (1000).
* O startActivity foi atualizado para aceitar um contexto de Atividade ou Aplicativo.
* Corrigido o bug que fazia com que a configuração de lifecycleSessionTimeout para 0 resultasse em vários eventos de inicialização pelo aplicativo.

## Versão 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

Data de lançamento: **18 de abril de 2013**

* Solucionado o problema de codificação com alguns caracteres UTF8.

## Versão 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

Data de lançamento: **18 de abril de 2013**

* Solucionado o problema que fazia com que uma duração de sessão anterior fosse calculada incorretamente algumas vezes.
* As novas IDs de visitantes não serão mais baseadas em deviceID ou subscriberID.
* Solucionada uma possível falha durante a codificação de caracteres especiais em variáveis.

## Versão 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

Data de lançamento: **21 março de 2013**

* Solucionado o problema que fazia com que a visitorID não pudesse ser lida sem que fosse configurada.
* Alteração nas convenções de nome em algumas mensagens de erro, criando maior clareza.
* Alterada a acessibilidade para várias classes de base para evitar confusão.
* Várias melhorias de desempenho

## Versão 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

Data de lançamento: **21 de fevereiro de 2013**

* Não é mais necessário desaprovar `offlineThrottleDelay` como configuração devido à otimização de discussão. A configuração ainda existe para preservar a compatibilidade anterior, mas não tem mais efeito.
* Correção do problema potencial de sincronização no cache de ocorrências offline.
* Mensagem de aviso explicada ao configurar vars hierárquicas no nº 5.
* Fixed issue that could cause OSVersion to be misreported on versions of [!DNL Android] &gt; 4.0.
* Várias melhorias de desempenho.
* Solução de uma exceção potencial que poderia ser causada por um url malformado.

## Versão 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

Data de lançamento: **novembro de 2012**

* Adição de uma variável de configuração `lifecycleSessionTimeout` a qual permite que você especifique a duração, em segundos, entre a inicialização do aplicativo antes que possa ser considerada uma nova sessão.
* Adição da capacidade de definir o valor de tempo limite para uma cálculo de duração de sessão usando uma definição de configuração `lifecycleSessionTimeout`.
* Correção de problemas de segurança.

## Versão 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

Data de lançamento: **outubro de 2012**

* Adição de suporte para [Rastreamento de campanha do Google Play](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/index.html?f=referrer).

## Versão 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

Data de lançamento: **setembro de 2012**

* Solução do problema em que ocorrências da ação de fechar resultavam em uma condição de ciclo no monitor de mídia.

## Versão 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

Data de lançamento: **agosto de 2012**

* Context override parameters are now sent in as `Hashmap<String, Object>` (they were formerly `Hashmap<String, String>`).

## Versão 3.0 {#section_2955C0AF3A23476B8CF06C469DE3284C}

Data de lançamento: **julho de 2012**

Versão inicial.

## Versão anterior do Android (1.x) {#section_F2CC015616184D55AC6D6529DFC9A18B}

The following release notes apply to the 1.x version of [!DNL AppMeasurement] for [!DNL Android]. Nós recomendamos que os clientes atualizem para a versão 3.x quando possível.

## Versão 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

Data de lançamento: **março de 2012**

* Correção de um problema que causava uma exceção em algumas circunstâncias ao passar dados usando Dados de contexto.

## Versão 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

Data de lançamento: **fevereiro de 2012**

Correção de um problema que fazia com que chamadas de rastreamento de links codificassem duplamente o URL de valores pev1 - pev3.

Adição de carimbo de data/hora a variáveis usadas com chamadas de faixas de luz (trackLight).

## Versão 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

Data de lançamento: **janeiro de 2012**

* Added [!DNL Android] 3.x and 4.x compatibility.
* Implemented a UUID for visitor ID on [!DNL Android] devices that do not have SIM cards (For example, Kindle Fire).

## Versão 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

Data de lançamento: **junho de 2011**

* Atualização da biblioteca para usar a ID do dispositivo para o valor da ID de visitante do quando nenhum cartão SIM estiver inserido no dispositivo. Por padrão, a biblioteca usa a ID do assinante como a ID do visitante que não está presente se nenhum cartão SIM estiver inserido.

## Versão 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

Data de lançamento: **abril de 2011**

* Suporte para todos os tablets incluindo o Xoom.
* A capacidade de pesquisar por conjuntos de relatórios e métricas ao executar um relatório.
* Suporte para o contextData, que direciona as regras de processamento do lado do servidor (somente v15).
* Suporte para chamadas de servidor leves (em beta).
