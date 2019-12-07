---
description: 'null'
subtopic: Release notes
title: Windows Silverlight, NET, IIS, XBOX
topic: Developer and implementation
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Windows Silverlight, NET, IIS, XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>Esses SDKs foram encerrados e não são mais suportados nem distribuídos pela Adobe.

> [!NOTE] Observação: para encontrar a versão atual da biblioteca, acione o log de depuração.

## Versão 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

Data de lançamento: **agosto de 2014**

* Remoção do suporte para o [!DNL Microsoft Silverlight Analytics Framework]. A Adobe não oferece mais suporte ou distribuição da integração do [!DNL Microsoft Silverlight Analytics Framework] para [!DNL AppMeasurement].

* Alterações internas para suportar recursos futuros.

## Versão 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

Data de lançamento: **março de 2013**

* Correção da exceção ao obter o referenciador padrão [!DNL Silverlight] fora de um contexto do navegador e a propriedade SSL exposta corretamente no componente [!DNL Microsoft Silverlight Analytics Framework].

## Versão 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

Data de lançamento: **fevereiro de 2013**

* Adicionado suporte para enviar URLs maiores que 255 bytes para suportar a expansão do campo URL da página nos servidores de coleta de dados da Adobe. URLs de páginas mais longas do que 255 bytes são divididos, os primeiros 255 bytes aparecem no parâmetro `g=` = os bytes restantes aparecem posteriormente em uma sequência de consulta no parâmetro de consulta `-g=`. Isso ajuda a evitar que URLs longos tenham precedência em relação a outros dados no caso de truncagem, mas ainda permite a captura de URLs longos.

* Adicionado um novo método de identificação de visitante de fallback. Consulte [Identificação de visitantes únicos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
* Adicionado um novo sinalizador `abort` que pode ser definido dentro de `doPlugins`. Configurar esse sinalizador como true, faz com que a [!DNL AppMeasurement] biblioteca não continue com essa chamada de rastreamento. O sinalizador abort é redefinido em cada chamada de rastreamento, portanto, se uma chamada de rastreamento subsequente também precisar ser abortada, o sinalizador precisará ser configurado novamente dentro de `doPlugins`.

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
   If(media.event=="CLOSE") { 
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

* Novo suporte e criação para plataforma do Telefone [!DNL iOS], incluindo rastreamento offline.
* Suporte para a delegação de doRequest a fim de substituir como as solicitações são enviadas para rastrear dados.
* Suporte para o contextData, que direciona as regras de processamento do lado do servidor (somente v15).
* Suporte para chamadas de servidor leves (em beta).
* Suporte para atribuir um valor diferente de 1 a um evento de contador na lista de eventos.
* Suporte para o novo método de rastreamento de vídeo utilizando eVars de conversão e eventos (em beta, no momento).

