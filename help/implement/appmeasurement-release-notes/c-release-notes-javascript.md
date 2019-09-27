---
description: Notas de versão acumuladas para o código herdado JavaScript H.
seo-description: Notas de versão acumuladas para o código herdado JavaScript H.
seo-title: Código H JavaScript - herdado
solution: Analytics
subtopic: Notas de versão
title: Código H JavaScript - herdado
topic: Desenvolvedor e implementação
uuid: 4586b250-0f1b-45b8-829c-18dc1201956f
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Código H JavaScript - herdado{#javascript-h-code-legacy}

Notas de versão acumuladas para o código herdado JavaScript H.

>[!NOTE]
>
>To find the current library version, use [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger_about.html).

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - Update {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

Data de lançamento: **16 de junho de 2016**

Inclusão da API de Visitante 1.5.7.

## H.25.5 - Update {#section_B10151D7718F4568AE523BE1553FCCB7}

Data de lançamento: **19 de maio de 2016**

Inclusão da API de Visitante 1.5.5.

## H.27.5 - Update {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

Data de lançamento: **5 de novembro de 2015**

* Inclusão da API de Visitante 1.5.3.

## H.27.5 - Update {#section_8A94D8A74A39486AAE248A22D661A261}

Data de lançamento: **17 de setembro de 2015**

* Inclusão da API de Visitante 1.5.2.

## H.27.5 - Update {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

Data de lançamento: **20 de agosto de 2015**

* Inclusão da API de Visitante 1.5.1.

## H.27.5 - Update {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

Data de lançamento: **18 de junho de 2015**

* Inclusão da API de Visitante 1.5.

## H.27.5 - Update {#section_B3E310AFF909480BAD59A7F87D298348}

Data de lançamento: **21 de maio de 2015**

* Inclusão da API de Visitante 1.4

## H.27.5 - Update {#section_E7006FC903064376A85D3EC2AC1D2544}

Data de lançamento: **16 de abril de 2015**

* Added Integrate module to s_code.js in legacy [!DNL AppMeasurement] for [!DNL JavaScript] H.X ZIP file. (AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

Data de lançamento: **19 de fevereiro de 2015**

* Inclusão da API de Visitante 1.3.5.
* Alteração realizada para que o rastreamento de referenciador não fosse automático após a primeira chamada de rastreamento. Assim, as chamadas de rastreamento subsequentes (geralmente, os rastreamentos em cadeia) não contarão o referenciador duas vezes quando *`s.referrer`* for definido manualmente antes da primeira chamada de rastreamento. (AN-92647)

## H.27.4 - Update {#section_ED38D59E83B4417180877F7C10BE4582}

Data de lançamento: **15 de janeiro de 2015**

* O zip de distribuição foi atualizado para incluir a API de Visitante 1.3.4.

Data de lançamento: **18 de setembro de 2014**

* A variável `tagContainerMarker` que permite que a implementação especifique até 4 caracteres que anexados à sequência da versão junto com um delimitador de caractere de travessão foi adicionada. Isto é usado pelo gerenciamento dinâmico de tags.

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

Data de lançamento: **21 de agosto de 2014**

* Alterações internas para suportar recursos futuros.

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Data de lançamento: **19 de junho de 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Suporte para novos recursos no serviço de ID do visitante 1.3.

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

Data de lançamento: **11 de junho de 2014**

* Fixed an issue in the [!DNL Analytics] for [!DNL Target] integration that caused some hits to incorrectly be merged.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

Data de lançamento: **22 de maio de 2014**

* Support for the [Experience Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Suporte para [Analytics para integração com Target](https://marketing.adobe.com/resources/help/en_US/target/a4t/).

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

Data de lançamento: **17 de outubro de 2013**

* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Data de lançamento: **18 de julho de 2013**

* Agora, o hash/fragmento é omitido pelo rastreamento automático de link. Antes, o URL a seguir era rastreado automaticamente se o `href` inteiro terminasse em `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

Agora, o hash/fragmento é omitido para que o link seja rastreado somente quando o nome do arquivo terminar em uma extensão correspondente. 

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

Data de lançamento: **29 de abril de 2013**

* A opção `useForcedLinkTracking` descrita em [Manual Link Tracking Using Custom Link Code](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_manuallinktrackcustomlink.html) aplica-se agora ao Firefox 20+ (antes se aplicava somente aos navegadores WebKit).

* A geração da ID do objeto da imagem agora é exclusiva entre instâncias. Isso evita colisões quando há mais de uma instância na mesma página.

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

Data de lançamento: **19 de abril de 2013**

* Fixed an issue in forced link tr [!DNL Windows]acking that caused a [!DNL JavaScript] error on some [!DNL Android] 2.2 Devices.

* No rastreamento automático de vídeos do Media Player, foi corrigido um problema de scrubbing que fazia com que o tempo de reprodução não fosse rastreado corretamente.

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

Data de lançamento: **fevereiro de 2013**

* Changed automatic exit link tracking to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

* Escopo refinado de eventos de cliques afetados por `useForcedLinkTracking`. O rastreamento de link forçado automático se aplica apenas a:

   * `<A>` e `<AREA>` tags

   * A tag deve ter um atributo `HREF`
   * The `HREF` can't start with `#`, `about:`, or `javascript:`

   * The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

Data de lançamento: **janeiro de 2013**

* Adicionado suporte para enviar URLs maiores que 255 bytes para suportar a expansão do campo URL da página nos servidores de coleta de dados da Adobe. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. Isso ajuda a evitar que URLs longos tenham precedência em relação a outros dados no caso de truncagem, mas ainda permite a captura de URLs longos.

* Corrigido o tratamento de decodificação de URL em sequências que estão codificadas com um uso misturado entre `escape` e `encodeURIComponent`.

* Corrigido um problema nos navegadores WebKit em que o rastreamento de link falha se a primeira chamada do servidor na página expirar.
* Adicionado um novo método de identificação de visitante de fallback. Consulte [Identificação de visitantes únicos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
* Adicionado um novo sinalizador `abort` que pode ser definido dentro de `doPlugins`. Setting this flag to true causes the [!DNL AppMeasurement] library to not continue with that tracking call. O sinalizador abort é redefinido em cada chamada de rastreamento, portanto, se uma chamada de rastreamento subsequente também precisar ser abortada, o sinalizador precisará ser configurado novamente dentro de `doPlugins`.

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

Isso permite que você centralize a lógica usada para identificar a atividade que você não deseja rastrear, como links personalizados ou links externos na exibição de anúncios.

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

Data de lançamento: **outubro de 2012**

* Added support for reporting an additional version number in the [!DNL JavaScript] version report. Anteriormente esta versão era limitada a 2 caracteres (por exemplo, 1.8). O suporte foi adicionado para um número de versão de 3 caracteres (por exemplo, 1.8.5).
* Um problema com o [!DNL Tag Manager] que impedia que valores repetidos nos blocos de Códigos dependentes fossem enviados foi corrigido.

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

Data de lançamento: **setembro de 2012**

* Imposição da codificação do URL dos seguintes caracteres:

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

This resolves issues with un-escaped characters being stored in the [!DNL ClickMap] `s_sq` cookie.

* Correção de um problema que podia fazer com que o evento de conclusão de vídeo não fosse enviado quando um método `media.monitor` personalizado que controlasse o evento de fechamento da mídia fosse usado:

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

Data de lançamento: **julho de 2012**

Criação de uma atualização para garantir que o rastreamento de links fosse concluído com sucesso em navegadores WebKit (Safari e Chrome). Após essa atualização, os links de download e de saída que são acompanhados automaticamente (determinados por `s.trackDownloadLinks` e `s.trackExternalLinks`) serão acompanhados com sucesso. If you are tracking custom links using manual [!DNL JavaScript] calls, you need to modify how these calls are made.

Por exemplo, links de saída e de download com frequência são rastreados com código semelhante ao seguinte:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

O FireFox e o Internet Explorer executam a chamada de rastreamento de link e abrem a nova página. No entanto, os navegadores WebKit podem cancelar a execução da chamada de rastreamento do link quando a nova página é aberta. Com frequência, isso impede que as chamadas de rastreamento de link sejam concluídas com o uso de navegadores WebKit.

Para contornar esse comportamento, o H.25 inclui um método sobrecarregado de rastreamento de link (`s.tl`) que força os navegadores WebKit a aguardarem a conclusão da chamada de rastreamento de link. Esse novo método executa a chamada de rastreamento de link e, em seguida, lida com o evento de navegação em vez de usar a ação padrão do navegador. Este método sobrecarregado requer um parâmetro adicional, chamado `doneAction`, para especificar a ação a ser executada quando a chamada de rastreamento de link é concluída.

Para usar esse novo método, atualize as chamadas para `s.tl` com um parâmetro `doneAction` adicional, semelhante ao seguinte:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

Passar 'navigate' como `doneAction` espelha o comportamento padrão do navegador e abre o URL especificado pelo atributo `href` quando a chamada de rastreamento é concluída.

A seguinte tabela resume as variáveis de configuração e atualizações efetuadas no H.25 para suportar essa funcionalidade.

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variável </p> </th> 
   <th colname="col2" class="entry"> <p>Descrição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>Esse sinalizador é usado para desativar o rastreamento de link forçado para navegadores WebKit. O rastreamento de link forçado é ativado por padrão para navegadores WebKit e é ignorada por outros navegadores. </p> <p> <b>Valor padrão</b> </p> <p> <code> true </code> </p> <p> <b>Exemplo</b> </p> 
    <code class="syntax javascript">
      s.useForcedLinkTracking&amp;nbsp;=&amp;nbsp;falso </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forcedLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p>O número máximo de milissegundos a fim de aguardar a conclusão do rastreamento antes de executar <code>doneAction</code> que foi passado para <code>s.tl</code>. Esse valor especifica o tempo máximo de espera. Se a chamada de link de rastreamento for completada antes do tempo limite, <code>doneAction</code> é executado imediatamente. Se as chamadas de link de rastreamento não estiverem sendo completadas, pode ser necessário aumentar esse tempo limite. </p> <p> <b>Valor padrão</b> </p> <p>250 </p> <p> <b>Exemplo</b> </p> 
    <code class="syntax javascript">
      s.forcedLinkTrackingTimeout&amp;nbsp;=&amp;nbsp;500 </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink (<code>s.tl </code>) </td> 
   <td colname="col2"> <p>Rastreia links de saída, download e personalizados. Fornece um parâmetro opcional para especificar uma ação de navegação que será executada depois que a chamada de link de rastreamento for completada em navegadores WebKit. </p> <p> <b>Sintaxe</b> </p> 
    <code class="syntax javascript">
      s.tl(linkObject,linkType,linkName,variableOverrides,doneAction) </code> <p> <b>doneAction</b>: (opcional) especifica a ação que deve ser tomada depois que a chamada de rastreamento de link é enviada ou atinge o tempo limite (com base no valor especificado por <code>s.forcedLinkTrackingTimeout </code>). A <code>doneAction</code> pode ser a sequência "navegar", que resulta na definição do método <code>document.location</code> no atributo <code>href</code> de <code>linkObject </code>. A <code>doneAction</code> também pode ser uma função que permite a personalização avançada. </p> <p>If providing a value for <code> onclick </code> in an anchor <code> false </code> event, you must return <code> s.tl </code> after the <code> href </code> call to prevent the default browser navigation. </p> <p> To mirror the default behavior and follow the URL specified by the <code> doneAction </code> attribute, provide a string of 'navigate' as the <code> doneAction </code>. </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <code>$1</code>. </p> <p> <b>Exemplos</b> </p> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp;href="..."&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,'navigate');return&amp;nbsp;false"&gt;Click&amp;nbsp;Aqui&lt;/a&gt; </code> <code class="syntax javascript">&lt;a&amp;nbsp;href="#"&amp;nbsp sp;onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=..});return&amp;nbsp;false"&gt;Click&amp;nbsp;Aqui&lt;/a&gt; </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

Data de lançamento: **abril de 2012**

Esta atualização é recomendada para todos s clientes.

* Aprimoramento realizado para detectar quando uma página é pré-processada usando o Google Chrome Prerender ([https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)). Since Prerender loads and executes [!DNL JavaScript] and other code, this could result in page views being sent before a user clicks to visit your site. The [!DNL JavaScript] library now waits until the user visits your site before sending server calls for these prerendered pages.
* Variável `timestamp`[!DNL JavaScript] adicionada à biblioteca para clientes que desejam personalizar os dados do carimbo de data e hora semelhantes a outras bibliotecas do [!DNL AppMeasurement]

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

Data de lançamento: **fevereiro de 2012**

* Correção de um problema que fazia com que dados extras fossem incluídos na solicitação de imagem de clientes que usassem substituições `Object.prototype` do Javascript. Todo o uso de `Object.prototype` agora é ignorado quando se lida com variáveis de dados de contexto.
* Correção de um problema que fazia com que o parâmetro de consulta `pe` fosse passado duas vezes com o mesmo valor em algumas circunstâncias.
* Correção do rastreamento [!DNL ClickMap][!DNL JavaScript] no para ignorar cliques na marca de corpo, mesmo quando a marca tiver um gerenciador de evento `onClick`.
* Adição de carimbo de data/hora a variáveis usadas com chamadas de faixas de luz ( `trackLight`).

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

Data de lançamento: **janeiro de 2012**

* O rastreamento de vídeo foi atualizado com um novo método de acompanhar exibições completas de vídeo.
* Fixed an issue that caused an "Attribute only valid on v:image" [!DNL JavaScript] error for `OnClick` events on VML elements in IE.
* Correção de um bug que fazia com que variáveis de dados de contexto não fossem incluídas em chamadas a servidores de link, embora exista referência a elas em `linkTrackVars`. Variáveis de dados de contexto são usadas com Regras de processamento.

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

Data de lançamento: **novembro de 2011**

* Atualizado o rastreamento de vídeo para combinar ocorrências de segmentos e fases que ocorrem ao mesmo tempo.

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

Data de lançamento: **novembro de 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

Data de lançamento: **novembro de 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

Data de lançamento: **outubro 2011**

* Fixed an issue that caused the `linkTrackVars=none` and `linkTrackEvents=none` settings to not apply when using automatic exit link tracking. Essas configurações agora são aplicadas para links de saída automáticos, de forma que props, eVars e eventos não sejam enviados com a solicitação de imagem de link de saída.

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

Data de lançamento: **setembro de 2011**

* Remoção de atributos de borda de tags de imagem em dispositivos móveis para seguir os padrões da linguagem WML (Wireless Markup Language). Isso corrige os problemas de renderização em alguns dispositivos móveis.

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

Data de lançamento: **agosto de 2011**

Correção de precisão das medidas de percentual no rastreamento de vídeo.

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

Data de lançamento: **julho de 2011**

* Adicionamos suporte para o recurso [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

Data de lançamento: **junho de 2011**

* Fixed an issue that caused [!DNL JavaScript] errors when accessing certain properties of Vector Markup Language (VML) shape elements.
* As sequências de caracteres de referência com mais de 255 caracteres agora são truncadas ao reduzir o caminho em vez da sequência de consulta. Isso corrige os problemas nos quais os parâmetros da sequência de consulta estavam truncados e não eram coletados.

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

Data de lançamento: **maio de 2011**

* Correção do problema que impedia o envio da variável de rastreamento de vídeo (pev3).
* Correção do problema que impedia a chamada `s_gi` de ativar o código para a compatibilidade com o código G e H. Ao passar 1 como o segundo parâmetro para essa chamada, o código é configurado para ser compatível com ambas as versões.

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

Data de lançamento: **abril de 2011**

* Suporte para o contextData, que direciona as regras de processamento do lado do servidor (somente v15).
* Suporte para chamadas de servidor leves (v15 somente).
* Suporte para atribuir um valor diferente de 1 a um evento de contador na lista de eventos.
* Suporte para o novo método de rastreamento de vídeo utilizando eVars de conversão e eventos (em beta, no momento).
* Remoção do suporte para configurar Media.trackWhilePlaying como falso. Sempre será verdadeiro.
* Sinalizador debugTracking adicionado para permitir o registro em log de solicitações de envio para o console Firebug de forma semelhante às outras plataformas.
* Certifique-se de que "+" está sempre codificado por URL, independentemente do navegador.
