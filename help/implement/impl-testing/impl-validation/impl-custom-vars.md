---
description: Lista de variáveis personalizadas usadas no Analytics.
keywords: Implementação do Analytics
seo-description: Lista de variáveis personalizadas usadas no Analytics.
seo-title: Variáveis personalizadas
solution: Analytics
title: Variáveis personalizadas
topic: Desenvolvedor e implementação
uuid: 54 adf 622-7 f 05-49 c 0-b 7 e 6-702 bb 2 f 17 b 1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variáveis personalizadas

Lista de variáveis personalizadas usadas no Analytics.

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> Variável </th> 
   <th class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Variáveis de tráfego </td> 
   <td> Verifique o valor de prop1 - 75. Esta é uma lista de verificação de itens a conferir. 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">Você está usando corretamente as letras maiúsculas/minúsculas? "ValueA" é um registro diferente de "valueA". Você pode usar todas as letras minúsculas, já que um pequeno subconjunto de navegadores converte todas as variáveis a letras minúsculas. </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">Os valores têm menos de 100 caracteres de comprimento? Se não, poderão ocorrer sobreposições de valores. </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> Todos os valores de uma única variável de propriedade estão relacionados ou alguns deles parecem fora de lugar? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Variáveis de conversão </td> 
   <td> As variáveis <span class="wintitle">Econversion</span> incluem eVar 1 - 75. Esta é uma lista de problemas que devem ser verificados. 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">Você está usando corretamente as letras maiúsculas/minúsculas? "ValueA" é um registro diferente de "valueA". Você pode usar todas as letras minúsculas, já que um pequeno subconjunto de navegadores converte todas as variáveis a letras minúsculas. </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">Os valores têm menos de 255 caracteres de comprimento? Se não, poderão ocorrer sobreposições de valores. </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">Todos os valores de uma única eVar estão relacionados ou alguns deles parecem fora de lugar? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Eventos personalizados </td> 
   <td> Os eventos incluem valores padrão (<span class="wintitle">prodView</span>, <span class="wintitle">scOpen</span>, <span class="wintitle">scAdd</span>, <span class="wintitle">scCheckout</span>, <span class="wintitle">purchase</span>), e eventos personalizados, de event1 a event100. Todos os eventos são enviados na variável dos eventos. Diversos eventos na mesma página devem ser delimitados por vírgulas (sem espaços em branco). 
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">Para todos os eventos de conversão padrão, os produtos devem ser preenchidos também com os produtos aplicáveis. Para todos os eventos, exceto compra, os elementos quantidade e preço são opcionais. </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108">O evento <span class="wintitle">compra</span> só deve ser definido uma vez em uma sessão, depois que a compra for concluída e confirmada. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

