---
description: Descrições de campo no Dynamic Tag Management para referenciadores e opções de campanha ao implantar o Dynamic Tag Management no Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Referenciadores e campanhas
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: ht
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# Referenciadores e campanhas

Descrições de campo no [!UICONTROL Dynamic Tag Management] para referenciadores e opções de campanha ao implantar o [!UICONTROL Dynamic Tag Management] no Adobe[!DNL Analytics].

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL Editar ferramenta]** &gt; **[!UICONTROL Referenciadores e campanhas]**

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
   <td colname="col2"> <p>Substitui o valor definido na variável  A variável<span class="varname"> s.referrer</span>, que normalmente é preenchida pelo referenciador definido no navegador. </p> <p>Consulte <a href="/help/implement/js-implementation/page-variables/page-variables.md">Variáveis de página</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campanha </td> 
   <td colname="col2"> <p>Uma variável que identifica campanhas de marketing usadas para trazer visitantes para o site. Normalmente, o valor da campanha é retirado de um parâmetro da sequência de consulta. </p> <p>Consulte [<a href="/help/implement/js-implementation/page-variables/campaign.md">Variáveis de página</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Use a interface do DTM para escolher se deseja usar um Parâmetro de consulta ou um Valor (que pode extrair de um elemento de dados):

![](assets/dtm-queryparam.png)

Você pode inserir sua sequência de consulta diretamente na interface ou referenciar um elemento de dados separado, se tiver outros meios de rastrear uma campanha.
