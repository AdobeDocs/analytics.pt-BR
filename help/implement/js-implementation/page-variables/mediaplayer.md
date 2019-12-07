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


# mediaPlayer

Essa variável especifica o player usado para consumir um item de mídia ou vídeo.


<!-- 

mediaPlayer.xml

 -->

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | pev3 | Reprodutores de vídeo | Nenhum |

**Sintaxe e valores possíveis** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Método autoTrack:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Método de rastreamento manual**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores possíveis:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemplos** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Armadilhas, dúvidas e dicas** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando s.Media.autoTrack = true.

