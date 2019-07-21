---
description: Descrições de campo para as configurações globais de Cookies usadas para implantar o Dynamic Tag Management no Adobe Analytics.
keywords: Gerenciamento dinâmico de tags; cookies; ID do visitante; namespace do visitante; períodos de domínio; fp domain periods; id da transação; duração do cookie
seo-description: Descrições de campo para as configurações globais de Cookies usadas para implantar o Dynamic Tag Management no Adobe Analytics.
seo-title: Cookies
solution: Marketing Cloud, Analytics, Gerenciamento dinâmico de tags
title: Cookies
uuid: 9 c 81 ecbb -0 f 02-4 c 1 a-a 5 a 5-426 cdea 57 f 38
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Cookies

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt;** [! UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Cookies]**

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ID do visitante </td> 
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
   <td colname="col2"> <p>A variável <span class="term"> A variável fpcookiedomainperiods</span> serve para cookies definidos pelo javascript (<code> s_ sq</code>, <code> s_ cc</code>, plug-ins) que são inerentemente cookies primários, mesmo se a implementação usar os domínios <span class="filepath"> 2 o 7. net</span> ou <span class="filepath"> omtrdc. net</span> de terceiros. </p> <p>See <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
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

