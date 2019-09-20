---
description: Use descrições de campo no Dynamic Tag Management para personalizar o código da página ao implantar o Analytics.
keywords: Gerenciamento dinâmico de tags;personalizar código de página;abrir editor;executar
seo-description: Use descrições de campo no Dynamic Tag Management para personalizar o código da página ao implantar o Analytics.
seo-title: Personalizar código de página
solution: Experience Cloud,Analytics,Target,Gerenciamento dinâmico de tags
title: Personalizar código de página
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Personalizar código de página

Use descrições de campo no Dynamic Tag Management para personalizar o código da página ao implantar o Analytics.

Adicione plug-ins para assegurar-se de que o código e a ferramenta Analytics sejam executados ao mesmo tempo. Para obter mais informações sobre os plug-ins do Analytics, consulte [Plug-ins de implementação](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Customize Page Code]**

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
   <td colname="col2"> <p>Você pode inserir qualquer chamada de JavaScript que deve ser acionada antes da chamada <code>s.t()</code> final, contida em <code>s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Executar </p> </td> 
   <td colname="col2"> <p> <b>Antes das configurações da interface de usuário</b>: as configurações da interface têm prioridade sobre o código personalizado (por exemplo, se você desejar substituir uma eVar caso uma configuração na interface tenha sido habilitada). </p> <p> <b>Depois das configurações da interface de usuário</b>: o código do cliente tem prioridade sobre as configurações da interface. </p> </td> 
  </tr> 
 </tbody> 
</table>

