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


# mediaName

Essa variável especifica o nome do vídeo ou item de mídia.


<!-- 

mediaName.xml

 -->

Ela só está disponível pela [!UICONTROL API de inserção de dados] e [!UICONTROL fonte de dados de processamento completo].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 64 KB | pev3 | Vídeos; Próximo fluxo de vídeo; Fluxo de vídeo anterior, Segmentos de vídeo exibidos, Tempo usado no vídeo | Nenhum |

**Sintaxe e valores possíveis** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Método autoTrack:**

Se você estiver usando o [!UICONTROL s.Media.autoTrack], a variável *`mediaName`não precisará ser implementada explicitamente.* Ela é determinada automaticamente pelo código do AppMeasurement para JavaScript.

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

```js
s.Media.close(mediaName)
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

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Exemplos** {#section_4B9584265B1A47289818141B2A88021D}

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
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Armadilhas, dúvidas e dicas** {#section_941A445BB52E4063B0F6920E61BB90DE}

* Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando [!UICONTROL s.Media.autoTrack] = true.
* A variável é armazenada como uma variável mySQL TEXT em vez de VARCHAR(100).
