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



# linkName

A variável é uma variável opcional usada no [!UICONTROL Rastreamento de link] que determina o nome de um link personalizado, de download ou de saída.


<!-- 

linkName.xml

 -->

A variável *`linkName`* normalmente não é necessária porque o terceiro parâmetro na função *`tl()`* a substitui.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 bytes </td> 
   <td> pev2 </td> 
   <td> <p>Downloads de Arquivos </p> <p>Links personalizados </p> <p>Links de saída  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Os links personalizados] se referem a links que enviam dados de rastreamento. The *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. Se *`linkName`* não estiver preenchida, o URL do link aparecerá no relatório.

**Sintaxe e valores possíveis** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

Não há limitações nas variáveis *`linkName`* além das limitações padrão de variáveis.

**Exemplos** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Configurações** {#section_F15FF429FC274F708D50DF79D4668EA3}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_170A78452A7340B5B229713AC1FB71FA}

* A variável *`linkName`* é substituída pelo terceiro parâmetro na função *`tl()`*.

* Se a variável *`linkName`* e o terceiro parâmetro na função *`tl()`* estiverem em branco, o URL completo do link (com exceção da sequência de consulta) aparecerá no relatório (mesmo se o link for relativo).
