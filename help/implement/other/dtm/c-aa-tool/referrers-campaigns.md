---
description: Descrições de campo no Dynamic Tag Management para referenciadores e opções de campanha ao implantar o Dynamic Tag Management no Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Referenciadores e campanhas
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Referenciadores e campanhas

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL  *`Property`*]** > ![Ícone](assets/settings_gear.png) de engrenagem **[!UICONTROL Edit Tool]** > **[!UICONTROL Referrers & Campaigns]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Elemento </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Substituição de Quem indicou </td>
   <td colname="col2"> <p>Substitui o valor definido na variável A variável<span class="varname"> s.referrer</span>, que normalmente é preenchida pelo referenciador definido no navegador. </p> <p>Consulte <a href="../../../vars/page-vars/referrer.md">quem indicou</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Campaign </td>
   <td colname="col2"> <p>Uma variável que identifica campanhas de marketing usadas para trazer visitantes para o site. Normalmente, o valor da campanha é retirado de um parâmetro da cadeia de caracteres de consulta. </p> <p>Consulte <a href="../../../vars/page-vars/campaign.md">campanha</a>. </p> </td>
  </tr>
 </tbody>
</table>

Use a interface do DTM para escolher se deseja usar um Parâmetro de consulta ou um Valor (que pode extrair de um elemento de dados):

![Parâmetro de consulta](assets/dtm-queryparam.png)

Você pode inserir sua cadeia de caracteres de consulta diretamente na interface ou referenciar um elemento de dados separado, se tiver outros meios de rastrear uma campanha.
