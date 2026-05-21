---
description: A página Métodos de descoberta identifica como vários relatórios de métodos de descoberta recebem crédito por eventos de sucesso de conversão no seu site. Por exemplo, se um mecanismo de pesquisa se refere a um visitante do site que faz uma compra, os Métodos de descoberta especificam como o mecanismo de pesquisa recebe crédito pela referência.
title: Métodos de descoberta
feature: Admin Tools
role: Admin
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
TQID: https://experienceleague.adobe.com/eIZhSAm5tZsV4bY3Bznamfq87nhWd82ZwL-M4OIkFSM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 48%

---

# Métodos de descoberta

A página Métodos de descoberta identifica como vários relatórios de métodos de descoberta recebem crédito por eventos de sucesso de conversão no seu site. Por exemplo, se um mecanismo de pesquisa se refere a um visitante do site que faz uma compra, os Métodos de descoberta especificam como o mecanismo de pesquisa recebe crédito pela referência.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Métodos de Descoberta]**

## Descrições de métodos de descoberta {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> O método de descoberta que você deseja modificar </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alocação </td> 
   <td colname="col2"> Especifica como aplicar crédito para uma referência. As opções de alocação compatíveis incluem: <p> <span class="uicontrol"> Mais recente (último):</span> Dá todo o crédito ao último referenciador (padrão). </p> <p> <span class="uicontrol"> Valor original:</span> concede todo o crédito ao primeiro referenciador. </p> <p> <span class="uicontrol"> Linear:</span> divide o crédito igualmente entre todos os referenciadores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expirar após </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol"> Visita:</span> após um período especificado de inatividade, geralmente de cerca de 30 minutos. </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol"> Exibição da página:</span> assim que qualquer página de seu site é aberta. </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol"> Minuto:</span> após 1 minuto de inatividade. </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol"> Compra:</span> no momento da compra. </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol"> Exibição do produto:</span> quando um visitante exibe a página de um produto da Web. </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol"> Abertura do carrinho:</span> quando um visitante abre um novo carrinho de compras online. </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol"> Check-out do carrinho:</span> quando um visitante faz o check-out usando um carrinho de compras online. </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol"> Adição ao carrinho:</span> quando um visitante adiciona um produto a um carrinho de compras online. </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol"> Remoção do carrinho:</span> quando um visitante remove um produto de um carrinho de compras online. </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol"> Abertura do carrinho:</span> quando um visitante exibe o conteúdo de um carrinho de compras online. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Todos os Métodos de descoberta expiram quando a visita termina. Se você optar por Expirar após um evento diferente (por exemplo, Check-out do carrinho), o Método de descoberta expira quando o Check-out do carrinho ocorre durante a visita. Se uma Finalização do carrinho não ocorrer durante a visita, o Método de descoberta ainda expirará quando a visita terminar.
