---
description: Descrições de campo para as configurações globais de Cookies usadas para implantar o Dynamic Tag Management no Adobe Analytics.
keywords: Dynamic Tag Management, cookies, id de visitante, namespace de visitante, períodos de domínio, períodos de domínio fp, id de transação, duração do cookie
seo-description: Descrições de campo para as configurações globais de Cookies usadas para implantar o Dynamic Tag Management no Adobe Analytics.
seo-title: Cookies
solution: Experience Cloud, Analytics, Dynamic Tag Management
title: Cookies
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Cookies

Descrições de campo para as configurações globais de Cookies usadas para implantar o [!UICONTROL Dynamic Tag Management] no Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL   ![](assets/settings_gear.png)

Editar ferramenta]** &gt; **[!UICONTROL Cookies]**

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Visitor ID </td> 
   <td colname="col2"> <p>Valor exclusivo que representa um cliente nos sistemas online e offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espaço do nome do visitante </td> 
   <td colname="col2"> <p>Variável usada para identificar o domínio com o qual os cookies são definidos. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Períodos de domínio </td> 
   <td colname="col2"> <p>O domínio no qual os cookies <code>s_cc</code> e <code>s_sq</code> do Analytics são definidos ao determinar o número de períodos no domínio do URL da página. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Períodos de domínio FP </td> 
   <td colname="col2"> <p>A variável A variável <span class="term"> fpCookieDomainPeriods</span> é para cookies definidos pelo JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) que são inerentemente cookies próprios, mesmo se a implementação usar os domínios <span class="filepath"> 2o7.net</span> ou <span class="filepath"> omtrdc.net</span> de terceiros. </p> <p>Consulte <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID da transação </td> 
   <td colname="col2"> <p>Valor exclusivo que representa uma transação online que resultou na atividade offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vida do cookie </td> 
   <td colname="col2"> <p>Determina o tempo de vida de um cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

