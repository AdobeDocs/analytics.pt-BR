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


# pageURL

A variável substitui a URL real da página.


<!-- 

pageURL.xml

 -->

Em casos raros, a URL da página não é a URL que você deseja reportar no Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
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
   <td> Sem limite* </td> 
   <td> <p>G </p> </td> 
   <td> Tráfego &gt; Segmentação &gt; Caminhos de página mais comuns </td> 
   <td> URL da página </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE]Embora a Adobe permita valores *`pageURL`* de até 64k, alguns navegadores impõem um limite de tamanho no URL das solicitações de imagem. Para impedir o truncamento de outros dados, os URLs de página com mais de 255 bytes são divididos. Os primeiros 255 bytes aparecem no parâmetro `g=` e os bytes restantes aparecem posteriormente em uma sequência de consulta no parâmetro de consulta `-g=`.

**Sintaxe e valores possíveis** {#section_22AF3BF7C2F743549967B0C760A095C0}

A variável *`pageURL`* deve ser um URL válido, com um protocolo válido. O domínio é forçado a ser exibido em letras minúsculas antes de ser preenchido em relatórios, e a string de consulta pode ser eliminada, dependendo das configurações do Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

São permitidos somente caracteres compatíveis com URL como a URL da página.

> [!NOTE] É extremamente recomendável entrar em contato com o consultor da Adobe ou o Atendimento ao cliente, antes de usar a variável *`pageURL`* para fins personalizados.

**Exemplos** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Configurações** {#section_A8F77DAD88164528ACC5C16C066B47DF}

Nenhum

