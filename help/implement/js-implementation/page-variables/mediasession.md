---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# mediaSession

Esta variável especifica os segmentos de um vídeo ou ativo de mídia consumido.


<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 Bytes </td> 
   <td> pev3 </td> 
   <td> Tempo gasto com o vídeo <p>Segmentos de vídeo visualizados </p> </td> 
   <td> Nenhum </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxe e valores possíveis** {#section_9A63266633C4427CB4A6549E4D887B85}

**Método autoTrack:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* does not need to be implemented explicitly. Ela será determinada automaticamente pelo código do AppMeasurement para JavaScript.

**Método de rastreamento manual**

Sintaxe:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valores possíveis:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Exemplos** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Armadilhas, dúvidas e dicas** {#section_1BCEB037AB724B6EBE87420BD3604B88}

Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando [!UICONTROL s.Media.autoTrack] = true.
