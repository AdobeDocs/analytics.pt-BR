---
description: Notas de versão cumulativas do AppMeasurement para JavaScript.
seo-description: Notas de versão cumulativas do AppMeasurement para JavaScript.
seo-title: AppMeasurement para JavaScript
solution: Analytics
subtopic: Notas de versão
title: AppMeasurement para JavaScript
topic: Desenvolvedor e implementação
uuid: 1440013 d-d 266-4 dce -9807-8 b 9 adac 73315
translation-type: tm+mt
source-git-commit: 12f8d0017acfad36f3445cd31a629725dd737686

---


# AppMeasurement para JavaScript{#appmeasurement-for-javascript}

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

The latest version of each library can be downloaded in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.

## Versão 2.15.0

Data de lançamento:**15 de julho de 2019**

* Rastreamento de alcance de rolagem de activitymap adicionado à extensão do Activity Map (AN -172949)
* DIL 9.2 adicionado ao appmeasurement (AN -182472)

## Versão 2.14.0

Data de lançamento: **21 de maio de 2019**

* Correção de problemas com o gerenciamento do estado dos parâmetros do rastreador quando várias ocorrências estavam pendentes. (AN-176931, AN-176629, DTM-12758)
* Atualização do AppMeasurement para incluir Visitor.js 4.3.0 (AN-180049)

## Versão 2.13.0

Data de lançamento:**10 de abril de 2019**

Correção para muitos problemas relatados com clearvars. O problema ocorre quando as ocorrências são enviadas antes que o rastreador esteja pronto. Quando o rastreador se torna pronto, a biblioteca pode definir variáveis que já foram limpas ou alteradas. (AN-176931, AN-176629, DTM-12758).

## Versão 2.12.0

Release Date: **02/22/2019**

* Atualização do módulo Gerenciamento de público-alvo DIL 9.1. (AN-175255)
* A Política de segurança GTM não permite o módulo Activity Map. (AN-174679)
* Appmeasurement aprimorado para aceitar a opção de não participação quando o Serviço de identidade não é aprovado na aceitação. (AN-175259)

## Versão 2.11.0

Release Date: **02/11/2019**

* Adição de suporte para o novo recurso Serviços de Opt-in da Adobe no AppMeasurement. (AN-163546)
* Adição de suporte para armazenar dados de rastreamento de link no armazenamento de sessão. (AN-162272)
* Adição de suporte para tipo de transmissão de mídia para Análise de áudio. (AN-173265)

## Versão 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] bloqueia transmissões de cookies durante a POST. (AN-165538)
* Suporte à ação de soltar para XDomainRequest. (AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Versão 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

Data de lançamento: **24/05/2018**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. A Adobe recomenda atualizar para a versão mais recente da API de visitante sempre que as bibliotecas de código associadas forem atualizadas ( [!DNL at.js], e assim por diante).[!DNL AppMeasurement.js]

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* Correção de um problema que fazia com que o cookie de rastreamento de link continuasse sendo gravado mesmo depois da desativação do rastreamento de link. (AN-156332)
* Correção de um problema onde `registerPreTrackCallback` e `registerPostTrackCallback` interrompem a assinatura da função de callback ao serem chamados várias vezes. (AN-158566)

## Versão 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

Data de lançamento: **12/04/2018**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* O cookie de rastreamento de link continua sendo gravado, mesmo com o recurso desativado. (AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## Versão 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

Data de lançamento: **29/03/2018**

Re-compilação da API de visitante 3.1.0 (AN-159524), que inclui as correções de erros: (CORE-11390, CORE-10634)

## Versão 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

Data de lançamento: **15/03/2018**

Re-compilação da API de visitante 3.1.0 (AN-159524), que inclui as correções de erros: (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353)
* Refatoração da criação do terminal de coleta de dados para facilitar o compartilhamento. (AN-156647)
* Adicionar solicitação de métricas de sincronização completa para o [!DNL AppMeasurement]. (AN-158343)

## Versão 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

Data de lançamento: **18/01/2018**

* Cessou o suporte para o IE do 6 ao 9
* Inclusão da API de Visitante v3.0.0
* Inclusão da DIL v7.00

## Versão 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

Data de lançamento: **09/11/2017**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## Versão 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

Data de lançamento: **21/09/2017**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)

* Inclusão da API de Visitante 2.5.0.

## Versão 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

Data de lançamento: **17/08/2017**

* Inclui dil.js v6.11
* Inclui a API de Visitante 2.4.0

## Versão 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

Data de lançamento: **20/07/2017**

* Correção de uma falha em que [!DNL s.Util.getQueryParam] capturava #
* Added v6.10 of [!DNL dil.js] (AN-145701)

## Versão 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

Data de lançamento: **08/06/2017**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* Inclusão da API de Visitante versão 2.2.0. (AN-144042)

## Versão 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* Foi incluída a versão mais recente de [!DNL dil.js] (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* Foi incluída novamente a API de Visitante 2.1.0. (AN-140873)
* `mcorgid` Parâmetro adicionado. (AN-139586)
* Foi adicionado o parâmetro cp (customerPerspective). (AN-140897)

## Versão 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

Data de lançamento: **09/03/2017**

* Movido para um novo processo de build que requer a atualização da versão para 2.0.0. (AN-137878)
* A gestão do mboxMCSDID foi movida para o local correto da seção em que as ligação de rastreamento é feita. (AN-138483)

## Versão 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

Data de lançamento: **19/01/2017**

* Inclui VisitorAPI 2.0.0
* A função faz chamadas e verificações para que a SDID seja consumida após a conclusão da verificação de anulação. (AN-134364)
* Os seguintes ganchos pré e pós chamada de rastreamento foram adicionados. (AN-134567)

   * s.registerPreTrackCallback
   * s.registerPostTrackCallback
   Essas funções têm como parâmetros: a chamada de retorno (como função) e os parâmetros para esta função. Por exemplo:

   ```
   s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
       console.log("pre track callback"); 
       console.dir(requestUrl); // Request URL 
       console.dir(a); // param1 
       console.dir(b); // param2 
       console.dir(c); // param3 
   }, "param1", "param2", "param3");
   ```

   A chamada de retorno é disparada quando o `requestUrl` e qualquer parâmetro passado quando a chamada de retorno é registrada. Isso ocorre antes ou depois da chamada de rastreamento, dependendo de qual método é usado para registrar a chamada de retorno. A ordem a qual essas chamadas de retorno são feitas não é garantida. As chamadas de retorno registradas na pré-função são disparadas após a criação do URL de rastreamento final. As chamadas de retorno posteriores são feitas após uma chamada de rastreamento bem-sucedida (se a chamada de rastreamento falhar, essas funções não são usadas). Qualquer chamada de retorno registrada com o `registerPreTrackCallback` não afeta a chamada de rastreamento. Além disso, o uso dos métodos de rastreamento em qualquer chamada de retorno registrada não é recomendado e pode gerar uma repetição infinita.

## Versão 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

Atualizado: **11/10/2016**

* Inclui a API de Visitante 1.10.1.

## Versão 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

Atualizado: **20/10/2016**

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusão da API de Visitante 1.9.0. (AN-132072)

## Versão 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

Atualizado: **15/09/2016**

* Update [!DNL AppMeasurement] [!DNL Audience Manager] Module with DIL 6.5 and Additional Configurations (AN-129411)

* Inclusão da API de Visitante 1.8.0 (AN-129887)

## Versão 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

Atualizado: **18/08/2016**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* Inclusão da API de Visitante 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Marketing Cloud ID service.

## Versão 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

Atualizado: **04/08/2016**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Marketing Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Marketing Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## Versão 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

Data de lançamento: **21 de julho de 2016**

* Inclusão da API de Visitante 1.6.0.
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa. 
</note>

 -->

## Versão 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

Data de lançamento: **16 de junho de 2016**

Inclusão da API de Visitante 1.5.7.

## Versão 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

Data de lançamento: **19 de maio de 2016**

[!DNL JavaScript] versão 1.5.6

* Inclusão da API de Visitante 1.5.6
* Correção do manuseio do rastreamento de cliques em links no Firefox, que não estava disparando o evento completo.

## Versão 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

Data de lançamento: **21 de abril de 2016**

* [!DNL AppMeasurement][!DNL Activity Map] O módulo foi integrado ao módulo [!DNL AppMeasurement] padrão, para que você só precise fazer referência a um [!DNL .js] arquivo. Additionally, [!DNL Activity Map] tracking is activated by default. (AN-112689)

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## Versão 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

Data de lançamento: **17 de março de 2016**

* Inclusão da API de Visitante 1.5.4
* Compatível com o cancelamento da API de Visitante versão 1.5.4 ou superior

## Versão 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

Data de lançamento: **21 de janeiro de 2016**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* O restante do URL ("-g") da página foi movido para o final da solicitação de rastreamento da string de consulta. (AN-114647)

## Versão 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

Data de lançamento: **5 de novembro de 2015**

* Inclusão da API de Visitante 1.5.3.
* Corrigida a detecção do IE11 for URL Truncation 2047 (AN-114914)

## Versão 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

Data de lançamento: **17 de setembro de 2015**

* Inclusão da API de Visitante 1.5.2

## Versão 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

Data de lançamento: **29 de agosto de 2015**

* Inclusão da API de Visitante 1.5.1.

## Versão 1.5.1 {#section_3C9637EDB058479184731067897E857C}

Data de lançamento: **16 de julho de 2015**

* [!DNL Audience Manager] Atualizado o módulo para usar AAM DIL 6.2 - IDs getcustomer de visitorapi. js e passá-las em /event chamada para AAM. (AN-104978)

## Versão 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

Data de lançamento: **18 de junho de 2015**

* Suporte para API de Visitante 1.5, que usa o método *`getCustomerIDs`* para coletar IDs de cliente e estado autenticado, e envia as IDs com as solicitações de coleta de dados.
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* Solucionado o problema conhecido descrito na versão 1.4.5.

## Versão 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

Data de lançamento: **21 de maio de 2015**

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recurso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Extensão para iOS</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external">Implementação da extensão para iOS </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Extensão portátil para Android</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external">Extensão portátil para Android </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

* Inclusão da API de Visitante 1.4.
* Foi atualizado o módulo do AudienceManagement para usar o DIL versão 6.0.

**Problema conhecido**

In the Visitor API / [!DNL AppMeasurement] [!DNL Audience Manager] Module integrations, there will be two destination publishing iFrame requests made in IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` and  `//fast.<subdomain>.demdex.net/dest4.html`. O comportamento correto, conforme observado em outros navegadores, é o de carregar apenas `//fast.<subdomain>.demdex.net/dest5.html`.

## Versão 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

Data de lançamento: **16 de abril de 2015**

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
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap </span> </p> </td> 
   <td colname="2"> <p>As chamadas <code>trackBeacon</code> e <code>clearCurrentBeacon</code><span class="keyword"> agora estão disponíveis no PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Uma pequena correção foi feita para limpar a ID de perfil de chamada do light-server após a chamada `trackLight`.

## Versão 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

Data de lançamento: **19 de fevereiro de 2015**

* Tornou o gerenciamento do rastreio tardio de chamadas consistente, o que corrigiu problemas com as variáveis revertidas durante o atraso, como por exemplo o objeto clicado.
* Alteração realizada para que o rastreamento de referenciador não fosse automático após a primeira chamada de rastreamento. Assim, as chamadas de rastreamento subsequentes (geralmente nos rastreamentos em cadeia) não contarão o referenciador duas vezes quando *`s.referrer`* for definido manualmente antes da primeira chamada de rastreamento.
* O zip de distribuição foi atualizado para incluir a API de Visitante 1.3.5.

## Versão 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

Data de lançamento: **15 de janeiro de 2015**

* Solucionado o manuseio da pré-renderização do WebKit para evitar o monitoramento de páginas pré-renderizadas que não são visualizadas.
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## Versão 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

Data de lançamento: **18 de setembro de 2014**

* A variável `tagContainerMarker` que permite que a implementação especifique até 4 caracteres que anexados à sequência da versão junto com um delimitador de caractere de travessão foi adicionada. Isto é usado pelo gerenciamento dinâmico de tags.

   ```js
   // JavaScript 
   s.tagContainerMarker = "D1.0"; 
   
   // Data Collection request 
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   Os 4 caracteres são limitados aos que são permitidos nos caminhos de arquivo URL, como caracteres alfanuméricos e pontos.

* Nas páginas que são marcadas duas vezes com o H Code, foi solucionado um loop que poderia ocorrer durante o rastreamento de link automático (fazer download e sair) quando o rastreamento de link forçado está ativado (padrão nos navegadores Webkit). Além disso, foi adicionada uma proteção geral no rastreamento de link automático para impedir loops similares. Essa proteção limita cliques repetidos no rastreamento automático de link no *mesmo* objeto a um clique a cada 10 segundos. Essa proteção é aplicada somente no monitoramento automático de link, sendo assim, as chamadas do monitoramento de link manual (s.tl) não ficam limitadas. Cliques em diferentes objetos também não são afetados por essa proteção e serão rastreados.
* Solucionado o gerenciamento de objeto clicado quando um atraso é necessário.
* Solucionado o problema gerava um contagem de visualização de página dupla quando o s.t era chamado a partir de uma função de link clicável, se a API de Visitante não tivesse os valores necessários.
* Suporte para HTTP POST.

   >[!IMPORTANT]
   >
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) implementation for Marketing Cloud.

## Versão 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

Data de lançamento: **21 de agosto de 2014**

* O rastreamento de plug-ins de navegadores foi removido (parâmetro de consultas `p`), já que os plug-ins não são mais relatados na versão 15.
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

Adicionado suporte para [eVars adicionais](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events) (76 - 250) e eventos (101-1000).

>[!NOTE]
>
>O código H não oferece suporte para evars e eventos adicionais.

[!DNL JavaScript]

## Versão 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Data de lançamento: **19 de junho de 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Suporte para novos recursos no serviço de ID do visitante 1.3.

## Versão 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

Data de lançamento: **22 de maio de 2014**

* [!DNL AppMeasurement] para [!DNL JavaScript]`s_gi` função não encontrava corretamente instâncias criadas com o código `s_gi`H. Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## Versão 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

Data de lançamento: **17 de abril de 2014**

* Suporte para [Serviço de ID do visitante da Marketing Cloud](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Versão 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

Data de lançamento: **13 de março de 2014**

* Correções de bugs para vídeo heartbeat.

## Versão 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

Data de lançamento: **20 de fevereiro de 2014**

* Correções de bugs para vídeo heartbeat.

## Versão 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

Data de lançamento: **6 de fevereiro de 2014**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager]Os clientes do também devem atualizar para a versão 4.8 do módulo DIL.

## Versão 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

Data de lançamento: **15 de novembro de 2013**

* Corrigidos os eventos de página que são usados para a [medição de vídeo heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

## Versão 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

Data de lançamento: **14 de novembro de 2013**

* Suporte adicionado para [medição de vídeo de heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* [!DNL VisitorAPI.js] foi adicionado para oferecer suporte ao [Serviço de ID do visitante](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#).

## Versão 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* Impossibilitava o envio de uma chamada de rastreamento de link de navegadores Opera para links que começavam com "opera:" ("opera:" é similar a "sobre:" e "chrome:" em outros navegadores).
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## Versão 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

Data de lançamento: **18 de setembro de 2013**

* Fixed support for placing the library and page code in the `head` tag.
* Added missing module `onLoad` support.

## Versão 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

Data de lançamento: **15 de agosto de 2013**

* Acrescentamos suporte para implantação através do gerenciamento de tags da Adobe.
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## Versão 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Data de lançamento: **18 de julho de 2013**

* Agora, o hash/fragmento é omitido pelo rastreamento automático de link. Antes, o URL a seguir era rastreado automaticamente se o `href` inteiro terminasse em `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Agora, o hash/fragmento é omitido para que o link seja rastreado somente quando o nome do arquivo terminar em uma extensão correspondente. 

## Versão 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

Data de lançamento: **23 de maio de 2013**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. Essa biblioteca oferece a mesma funcionalidade principal de [!DNL s_code.js], mas é mais leve e rápida de usar em sites móveis e para desktop.

* De 3 a 7 vezes mais rápida do que o código H.25.
* Somente 21k descompactado e 8k compactado por gzip (o código H.25 pesa 33k descompactado e 13k compactado por gzip).
* Suporte nativo para obter parâmetros de consulta, cookies de leitura e gravação e executar rastreamento de links avançado.
* Pequeno e rápido o suficiente para ser usado em sites móveis e robusto o suficiente para ser usado na Web completa para desktop, permitindo que você utilize uma única biblioteca em todos os ambientes da Web.

Veja [AppMeasurement para Javascript](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs) no Guia de implementação do [!DNL Analytics]

>[!NOTE]
>
>Alguns plug-ins não são suportados nesta nova versão. Consulte [Suporte de plug-ins](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support) para obter detalhes.
