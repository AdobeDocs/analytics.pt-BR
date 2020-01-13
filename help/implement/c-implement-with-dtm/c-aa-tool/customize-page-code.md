---
description: Use descrições de campo no Dynamic Tag Management para personalizar o código da página ao implantar o Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personalizar código de página
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Personalizar código de página

Use descrições de campo no Dynamic Tag Management para personalizar o código da página ao implantar o Analytics.

Adicione plug-ins para assegurar-se de que o código e a ferramenta Analytics sejam executados ao mesmo tempo. Para obter mais informações sobre os plug-ins do Analytics, consulte  [Plug-ins de implementação](/help/implement/js-implementation/plugins/impl-plugins.md).

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL   ![](assets/settings_gear.png)

Editar ferramenta]** &gt; **[!UICONTROL Personalizar código de página]**

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

