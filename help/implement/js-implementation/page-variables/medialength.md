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


# mediaLength

A variável especifica o tamanho total da mídia reproduzida.


<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
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
   <td> Não existe tamanho máximo para a solicitação de pev3 inteira. O tamanho é limitado ao limite de comprimento do URL do navegador. </td> 
   <td> pev3 </td> 
   <td> Tempo gasto com o vídeo; <p>Segmentos de vídeo visualizados </p> </td> 
   <td> Nenhum </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxe e valores possíveis** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**Método autoTrack:**

Se você estiver usando o [!UICONTROL s.Media.autoTrack], a variável [!UICONTROL mediaLength] não precisará ser implementada explicitamente. Ela é determinada automaticamente pelo código do AppMeasurement para JavaScript.

**Método de rastreamento manual**

Sintaxe:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores possíveis:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemplos** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Armadilhas, dúvidas e dicas** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando [!UICONTROL s.Media.autoTrack] = true.
* Se você não estiver acompanhando com o [!UICONTROL autoTrack], assegure-se de definir o comprimento em segundos.

