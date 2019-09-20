---
description: Descrições de campo no Dynamic Tag Management para referenciadores e opções de campanha ao implantar o Dynamic Tag Management no Adobe Analytics.
keywords: Gerenciamento dinâmico de tags;referenciadores;campanhas;referrer override;campaign variable;query param
seo-description: Descrições de campo no Dynamic Tag Management para referenciadores e opções de campanha ao implantar o Dynamic Tag Management no Adobe Analytics.
seo-title: Referenciadores e campanhas
solution: Experience Cloud,Analytics,Gerenciamento dinâmico de tags
title: Referenciadores e campanhas
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Referenciadores e campanhas

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) Editar ferramenta **[!UICONTROL &gt;]** **[!UICONTROL Referenciadores e campanhas]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Substituição do referenciador </td> 
   <td colname="col2"> <p>Substitui o valor definido na variável <span class="varname"> s.referrer</span> variable, which is typically populated by the referrer set in the browser. </p> <p>Consulte [Variáveis de página](/help/implement/js-implementation/c-variables/page-variables.md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campanha </td> 
   <td colname="col2"> <p>Uma variável que identifica campanhas de marketing usadas para trazer visitantes para o site. Normalmente, o valor da campanha é retirado de um parâmetro da sequência de consulta. </p> <p>Consulte [Variáveis de página](/help/implement/js-implementation/c-variables/page-variables.md). </p> </td> 
  </tr> 
 </tbody> 
</table>

Use a interface do DTM para escolher se deseja usar um Parâmetro de consulta ou um Valor (que pode extrair de um elemento de dados):

![](assets/dtm-queryparam.png)

Você pode inserir sua sequência de consulta diretamente na interface ou referenciar um elemento de dados separado, se tiver outros meios de rastrear uma campanha.
