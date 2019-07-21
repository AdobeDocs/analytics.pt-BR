---
description: A página Métodos de descoberta identifica como vários relatórios de métodos de descoberta recebem crédito para eventos bem-sucedidos de conversão em seu site. Por exemplo, se um mecanismo de pesquisa encaminhar um visitante para o seu site e o visitante fizer uma compra, Métodos de descoberta especificará como o mecanismo de pesquisa recebe crédito pela indicação.
seo-description: A página Métodos de descoberta identifica como vários relatórios de métodos de descoberta recebem crédito para eventos bem-sucedidos de conversão em seu site. Por exemplo, se um mecanismo de pesquisa encaminhar um visitante para o seu site e o visitante fizer uma compra, Métodos de descoberta especificará como o mecanismo de pesquisa recebe crédito pela indicação.
seo-title: Métodos de descoberta
solution: Analytics
title: Métodos de descoberta
topic: Ferramentas administrativas
uuid: 1053993 e -7 fc 4-4874-84 fa -367 ecdcd 7 b 45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métodos de descoberta

A página Métodos de descoberta identifica como vários relatórios de métodos de descoberta recebem crédito para eventos bem-sucedidos de conversão em seu site. Por exemplo, se um mecanismo de pesquisa encaminhar um visitante para o seu site e o visitante fizer uma compra, Métodos de descoberta especificará como o mecanismo de pesquisa recebe crédito pela indicação.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Conjuntos]** de relatórios &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Conversão]** &gt; **[!UICONTROL Buscar métodos]**.

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
   <td colname="col2"> O método de descoberta que deseja modificar </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alocação </td> 
   <td colname="col2"> Especifica como aplicar crédito a uma referência. As opções de alocação compatíveis são: <p> <span class="uicontrol"> Mais recente (último):</span> Dá todo o crédito ao último referenciador (padrão). </p> <p> <span class="uicontrol"> Valor original:</span> concede todo o crédito ao primeiro referenciador. </p> <p> <span class="uicontrol"> Linear:</span> divide o crédito igualmente entre todos os referenciadores. </p> </td> 
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
>Todos os Métodos de descoberta expiram quando a visita termina. Se você optar por Expirar após um evento diferente (por exemplo, Check-out do carrinho), o Método de descoberta expirará quando Check-out do carrinho ocorrer durante a visita. Se não ocorrer o Check-out do carrinho durante a visita, o Método de descoberta ainda expirará ao final da visita.

