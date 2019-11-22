---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# browserHeight

A variável exibe a altura da janela do navegador.


<!-- 
browserheight.xml
-->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

**Parâmetros**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Parâmetro de consulta </th> 
   <th class="entry"> Valor </th> 
   <th class="entry"> Exemplo </th> 
   <th class="entry"> Relatórios afetados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Um inteiro positivo </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Tráfego &gt; Tecnologia &gt; Altura do navegador  </p> </td> 
  </tr> 
 </tbody> 
</table>

