---
description: Use descrições de campo no Dynamic Tag Management para personalizar o código da página ao implantar o Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personalizar código de página
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: ht
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Personalizar código de página

Use descrições de campo no Dynamic Tag Management para personalizar o código da página ao implantar o Analytics.

**[!UICONTROL  *`Property`*]** > **[!UICONTROL![](assets/settings_gear.png)

Editar ferramenta]** > **[!UICONTROL Personalizar código de página]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Abrir editor </p> </td> 
   <td colname="col2"> <p>Você pode inserir qualquer chamada de JavaScript que deve ser acionada antes da chamada <code> s.t()</code> final, contida em <code> s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Executar </p> </td> 
   <td colname="col2"> <p> <b>Antes das configurações da interface de usuário</b>: as configurações da interface têm prioridade sobre o código personalizado (por exemplo, se você desejar substituir uma eVar caso uma configuração na interface tenha sido habilitada). </p> <p> <b>Depois das configurações da interface de usuário</b>: o código do cliente tem prioridade sobre as configurações da interface. </p> </td> 
  </tr> 
 </tbody> 
</table>

