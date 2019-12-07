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



# linkType

A variável é uma variável opcional usada no rastreamento de link que determina em qual relatório um Nome de link ou URL aparece (links personalizados, de download ou de saída).


<!-- 

linkType.xml

 -->

A variável *`linkType`* normalmente não é necessária porque o segundo parâmetro na função *`tl()`* a substitui.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> Um caractere </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Downloads de Arquivos </p> <p>Links personalizados </p> <p>Links de saída  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Os links personalizados enviam dados ao Analytics. A variável *`linkType`* (ou o segundo parâmetro na função *`tl()`*) é usada para identificar o relatório em que o nome do link ou o URL aparece (relatório de Link [!UICONTROL Personalizado], de [!UICONTROL Download] ou [!UICONTROL Saída]).

Para links de saída e de download, a variável *`linkType`* é preenchida automaticamente, dependendo se o link clicado é um link de saída ou de download. É possível configurar um link personalizado para enviar dados a qualquer um dos três relatórios com essa variável ou com o segundo parâmetro na função *`tl()`*. Ao configurar *`linkType`* para 'o', 'e' ou 'd', o URL *`linkName`* ou link é enviado para o relatório [!UICONTROL Links personalizados], [!UICONTROL Links de saída] ou [!UICONTROL Downloads de arquivo], respectivamente.

**Sintaxe e valores possíveis** {#section_18DB3A8083FB4F75B970055ED336DA4E}

A sintaxe da variável *`linkType`* depende se você usa XML ou uma sequência de consulta.

Se estiver usando XML, a variável somente poderá conter um único caractere, ou seja, “o”, “e” ou “d”.

```js
s.tl(this,'o','Link Name');
```

Se estiver usando a sequência de consulta `pe`, será necessário usar `lnk_d`, `lnk_e` ou `lnk_o`.

**Exemplos** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Configurações** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* Se *`linkType`* não for especificado, serão assumidos os links personalizados ('o').
