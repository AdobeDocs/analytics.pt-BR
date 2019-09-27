---
description: Notas de versão acumuladas para Flash. Os aplicativos Flash com ActionScript podem ser avaliados no desktop e na Web.
seo-description: Notas de versão acumuladas para Flash. Os aplicativos Flash com ActionScript podem ser avaliados no desktop e na Web.
seo-title: Flash-Flex
solution: Analytics
subtopic: Notas de versão
title: Flash-Flex
topic: Desenvolvedor e implementação
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764b7f
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Flash-Flex{#flash-flex}

Notas de versão acumuladas para Flash. Os aplicativos Flash com ActionScript podem ser avaliados no desktop e na Web.

>[!NOTE]
>
>Para localizar a versão atual da biblioteca, ative o registro de depuração.

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## April 20, 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**Versão 4.0.3 **

* Inclusão da API de Visitante 1.6.1.

## 18 de agosto de 2016 {#section_D72EF20672174249B864997905D7552A}

** 4.0.2 - Atualização**

Inclusão da API de Visitante 1.6.0.

## May 19, 2016 {#section_061305CFC1E040E69E3CDF4078C17AE4}

** 4.0.1 - Atualização**

Inclusão da API de Visitante 1.5.6

## April 21, 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

A Adobe lançou uma [atualização de segurança APSB16-13 ](https://helpx.adobe.com/security/products/analytics/apsb16-13.html)para a biblioteca [!DNL AppMeasurement] para Flash. Essa atualização soluciona uma vulnerabilidade importante da biblioteca, aplicável somente quando `debugTracking` está ativado, podendo ser usado para realizar [ataques de XSS com base em DOM](https://www.owasp.org/index.php/DOM_Based_XSS).

>[!IMPORTANT]
>
>This issue affects [!DNL AppMeasurement] for Flash only when `debugTracking` has been enabled ( `debugTracking` is disabled in the default configuration). **Se for afetada, recomendamos que você desative`debugTracking`imediatamente.** Alguns códigos de exemplo:

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled” behavior 
```

As versões afetadas são [!DNL AppMeasurement] para Flash versão 4.0 e anterior em todas as plataformas.

>[!NOTE]
>
>Due to security reasons, we will no longer be distributing an AS2 version of [!DNL AppMeasurement] for Flash. Continuaremos a suportar a coleta de dados de projetos existentes baseados em AS2. Contudo, é fortemente recomendado atualizar as implementações de cliente para AS3 e incorporar os recursos de segurança mais recentes do [!DNL AppMeasurement] para Flash.

[!DNL AppMeasurement] para clientes Flash afetados por esse problema devem recriar projetos com a biblioteca atualizada disponível para download no [!DNL Analytics] Console [Mais...](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)

## November 5, 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

Versão 4.0 - Atualização:

* Inclusão da API de Visitante 1.5.3.

## September 17, 2015 {#section_319911C0F080452981F8C8BEA2880463}

Versão 4.0 - Atualização:

* Inclusão da API de Visitante 1.5.2.

## August 20, 2015 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

Versão 4.0 - Atualização:

* Inclusão da API de Visitante 1.5.1.

## June 18, 2015 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

Versão 4.0 - Atualização

* Inclusão da API de Visitante 1.5.
* Use o método Visitor API 1.5+ getCustomerIDs para reunir IDs de clientes e o estado autenticado e envie-os com as solicitações de coleta de dados (AN-102131)

## 21 de maio de 2015 {#section_F5EFCC451F13499F9AA53326AE5926F1}

Versão 3.9.2 - Atualização:

* Inclusão da API de Visitante 1.4

## February 19, 2015 {#section_95ADF1725CE7415D956944A28182E69B}

Versão 3.9.2:

* Inclusão da API de Visitante 1.3.5.
* Alteração realizada para que o rastreamento de referenciador não fosse automático após a primeira chamada de rastreamento. Assim, as chamadas de rastreamento subsequentes (geralmente, os rastreamentos em cadeia) não contarão o referenciador duas vezes quando *`s.referrer`* for definido manualmente antes da primeira chamada de rastreamento. (AN-92647)
* Removal of deprecated [!UICONTROL Heartbeat] video tracking embedded in the Media module. The supported [!UICONTROL Heartbeat] video tracking has been moved to a separate Video [!DNL Analytics] library.

## September 18, 2014 {#section_80939868A2284961BF620851B000294F}

Versão 3.9.1:

* Added cookie support testing to Flash (k = Y/N query-string variable) and pf=1 to query-string when cookie support test is possible (browser with [!DNL JavaScript] access).
* Suporte para novos recursos no serviço de ID do visitante 1.3.2.

## 21 de agosto de 2014 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

Versão 3.9:

* Adicionadas as variáveis de latitude e longitude.
* Suporte para novos recursos no serviço de ID do visitante 1.3.1.

## Versão 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

Data de lançamento: **19 de junho de 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Suporte para novos recursos no serviço de ID do visitante 1.3.

## Versão 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

Data de lançamento: **17 de abril de 2014**

* Support for the [Experience Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Versão 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

Data de lançamento: **13 de março de 2014**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Versão 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

Data de lançamento: **6 de fevereiro de 2014**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Versão 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

Data de lançamento: **14 de novembro de 2013**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Versão 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

Data de lançamento: **17 de outubro de 2013**

* Compatível com o [monitoramento de vídeo heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* VisitorAPI.swc foi incluído para oferecer suporte ao [Serviço de ID do visitante](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_service#.html).
* Retirada do suporte para Flash player 9 com ActionScript 3. A versão mínima do Flash Player para ActionScript 3 é a versão 10.

## Versão 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

Data de lançamento: **18 de setembro de 2013**

* Alterações internas para oferecer suporte à próxima versão beta.

## Versão 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

Data de lançamento: **15 de agosto de 2013**

* Desativado o re-enfileiramento de solicitações com erros quando o monitoramento offline estiver desativado.

## Versão 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

Data de lançamento: **21 de fevereiro de 2013**

* Correção de um problema com a codificação/decodificação do URL em ActionScript 2.

## Versão 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

Data de lançamento: **31 de janeiro de 2013**

* Adicionado suporte para enviar URLs maiores que 255 bytes para suportar a expansão do campo URL da página nos servidores de coleta de dados da Adobe. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. Isso ajuda a evitar que URLs longos tenham precedência em relação a outros dados no caso de truncagem, mas ainda permite a captura de URLs longos.

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

## Versão 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

Data de lançamento: **8 de novembro de 2012**

* Internal updates for [!DNL Audience Manager] integration.

## Versão 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

Data de lançamento: **22 de outubro de 2012**

* Alteração em construções do ActionScript 3 para ignorar qualquer configuração de `s.charSet`, pois sempre usamos UTF-8

## Versão 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Release Date: **September 13, 2012**
**Important change to variable binding**: In version 3.5, an option to disable variable binding was added for customers who need to start and end literal string values with curly braces. A vinculação de variável usando chaves é usada primariamente ao configurar players de vídeo OSMF usando tags XML:

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

Um novo atributo, chamado `autoBind`, está disponível para substituir o comportamento padrão em tags XML:

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

Setting `autoBind` to `false` causes the value to be considered a literal string and variable binding is not used. When this attribute is not set to `false` the behavior in XML tags remains the same.

**Impacto no código ActionScript**

Though not commonly used, this syntax is also available to bind [!DNL AppMeasurement] variables in your ActionScript code. If you are unsure whether or not you are using variable binding, search your code for [!DNL AppMeasurement] variable values that start and end with curly braces. Por exemplo:

```
s.eVar1 = "{source}";
```

Se estiver usando a vinculação de variável, você deve alterar esse código para usar o novo método `bindVariable`:

```
s.bindVariable("eVar1","source");
```

Como opção, em vez de alterar cada local, você pode reverter para o comportamento da pré-versão 3.5 ao configurar `autoBindVariablesByValue` como verdadeiro:

```
s.autoBindVariablesByValue = true;
```

**Correções adicionais:**

* Correção de um problema que podia fazer com que o evento de conclusão de vídeo não fosse enviado quando um método `media.monitor` personalizado que controlasse o evento de fechamento da mídia fosse usado:

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## Versão 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

Data de lançamento: **19 de julho de 2012**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## Versão 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

Data de lançamento: **21 de junho de 2012**

* Alterado para sempre usar UTF-8 em compilações AS3. Isso evita problemas com sequência de caracteres para algumas linguagens multibyte.

## Versão 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

Data de lançamento: **26 de abril de 2012**

Medição de vídeo: Adicionamos reparação de deslocamento completo inconsistente relatado pela API do player Brightcove. Agora, se o deslocamento for relatado como zero, no completo usamos o comprimento como deslocamento. Isto corrige problemas com o novo método de rastreamento de completos usando um valor de deslocamento.

## Versão 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

Data de lançamento: **19 de janeiro de 2012**

* O rastreamento de vídeo foi atualizado com um novo método de acompanhar exibições completas de vídeo.

## Versão 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

Data de lançamento: **8 de setembro de 2011**

* Permitiu que props contenham um valor zero literal de "0". Os props anteriores com um valor zero literal não foram enviados.

## Versão 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

Data de lançamento: **maio de 2011**

* No OSMF, os problemas foram corrigidos ao usar plug-ins de proxy ao rastrear players de vídeo do OSMF. A correção permitiu rastrear ProxyElements do OSMF quando o elemento que estão fazendo o proxy não está sendo rastreado.
* Correção do problema que resultava em erro ao medir vídeos no Flash Player 9.0.16.

