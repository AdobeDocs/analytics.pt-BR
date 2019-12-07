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


# pageType

A variável só é usada para designar uma página de erro 404, Página não encontrada.


<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
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
   <td> 20 bytes </td> 
   <td> pageType </td> 
   <td> Caminhos &gt; Páginas &gt; Páginas <p>Não encontrada </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Configure a variável *`pageType`* na página de erro exatamente como mostrado abaixo.

Não use a variável de nome de página em páginas de erro 404. A variável *`pageType`* é usada apenas para a de erro 404.

Na maioria dos casos, a página de Erro 404 é uma página estática codificada. Nesses casos, é importante que a referência ao arquivo .JS seja definida em um caminho/diretório global ou relativo apropriado.

**Sintaxe e valores possíveis** {#section_C1C59968226446559B05F6EE7374D525}

O único valor permitido de *`pageType`* é "errorPage", como mostrado abaixo.

```js
s.pageType="errorPage"
```

**Exemplos** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Configurações** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_943681AB01FE47BEAC72E93CB60C53C8}

Para capturar outros erros do lado do servidor (como erros 500), use uma prop para obter a mensagem de erro e insira "`500 Error: <URL>`", onde `<URL>` é o o URL solicitado na variável *`pageName`*. Seguindo esta orientação, você poderá usar os relatórios de [!UICONTROL Definição de caminho] para ver quais caminhos fizeram com que usuários gerassem os erros 500. A prop explica qual mensagem de erro é fornecida pelo servidor.

