---
description: Descrições de campo para as configurações globais de Cookies usadas para implantar o Dynamic Tag Management no Adobe Analytics.
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics
title: Cookies
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: 1ff9c892670e7b120bf727e556ff70f76c6751be
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 80%

---


# Cookies

Descrições de campo para as configurações globais de Cookies usadas para implantar o [!UICONTROL Dynamic Tag Management] no Adobe Analytics.

*`Property`* > Editar ferramenta > Cookies

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ID de visitante </td> 
   <td colname="col2"> <p>Valor exclusivo que representa um cliente tanto no sistema online como no offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namespace do visitante </td> 
   <td colname="col2"> <p>Variável para identificar o domínio com o qual os cookies são definidos. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Períodos de domínio </td> 
   <td colname="col2"> <p>O domínio no qual os cookies <code> s_cc</code> e <code> s_sq</code> do Analytics são definidos ao determinar o número de períodos no domínio do URL da página. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Períodos de domínio FP </td> 
   <td colname="col2"> <p>A variável <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> adobedc.net</span> domain, or the legacy (but still valid) <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>Consulte <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  > s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID da transação </td> 
   <td colname="col2"> <p>Valor exclusivo que representa uma transação online que resultou na atividade offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duração do cookie </td> 
   <td colname="col2"> <p>Determina a duração de um cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

