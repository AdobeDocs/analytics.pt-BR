---
description: 'null'
seo-description: 'null'
seo-title: Windows Silverlight, NET, IIS, XBOX
solution: Analytics
subtopic: Notas de versão
title: Windows Silverlight, NET, IIS, XBOX
topic: Desenvolvedor e implementação
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Windows Silverlight, NET, IIS, XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>These SDKs have been sunset and are no longer supported or distributed by Adobe.

>[!NOTE]
>
>Para localizar a versão atual da biblioteca, ative o registro de depuração.

## Versão 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

Data de lançamento: **agosto de 2014**

* Removed support for the . [!DNL Microsoft Silverlight Analytics Framework] Adobe is no longer supporting or distributing the [!DNL Microsoft Silverlight Analytics Framework] integration for [!DNL AppMeasurement].

* Alterações internas para suportar recursos futuros.

## Versão 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

Data de lançamento: **março de 2013**

* Fixed exception with getting default referrer in [!DNL Silverlight] outside of a browser context and properly exposed SSL property in the [!DNL Microsoft Silverlight Analytics Framework] component.

## Versão 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

Data de lançamento: **fevereiro de 2013**

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

## Versão 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

Data de lançamento: **setembro de 2012**

* Correção de um problema que podia fazer com que o evento de conclusão de vídeo não fosse enviado quando um método `media.monitor` personalizado que controlasse o evento de fechamento da mídia fosse usado:

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## Versão 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

Data de lançamento: **abril de 2012**

* Adicionamos suporte para o recurso [!DNL XBOX].

## Versão 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

Data de lançamento: **fevereiro de 2012**

* [!DNL iOS] Phone 7: correção de um problema que fazia com que offlineThrottleDelay não fosse aplicado corretamente.
* Adição de carimbo de data/hora a variáveis usadas com chamadas de faixas de luz (trackLight).

## Versão 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

Data de lançamento: **janeiro de 2012**

* O rastreamento de vídeo foi atualizado com um novo método de acompanhar exibições completas de vídeo. Consulte [Avaliação de vídeos no Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html).

## Versão 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* New support and build for [!DNL iOS] Phone platform including offline tracking.
* Suporte para a delegação de doRequest a fim de substituir como as solicitações são enviadas para rastrear dados.
* Suporte para o contextData, que direciona as regras de processamento do lado do servidor (somente v15).
* Suporte para chamadas de servidor leves (em beta).
* Suporte para atribuir um valor diferente de 1 a um evento de contador na lista de eventos.
* Suporte para o novo método de rastreamento de vídeo utilizando eVars de conversão e eventos (em beta, no momento).

