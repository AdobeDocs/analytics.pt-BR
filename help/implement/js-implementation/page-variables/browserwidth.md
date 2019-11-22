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



# browserWidth

A variável exibe a largura da janela do navegador.


<!-- 

browserwidth.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

**Parâmetros**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Parâmetro de consulta</b> </p> </td> 
   <td> <p> <b>Valor</b> </p> </td> 
   <td> <p> <b>Exemplo</b> </p> </td> 
   <td> <p> <b>Relatórios afetados</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Um inteiro positivo </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Tráfego &gt; Tecnologia &gt; Largura do navegador  </p> </td> 
  </tr> 
 </tbody> 
</table>
