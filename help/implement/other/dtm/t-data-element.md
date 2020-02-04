---
description: Crie um elemento de dados no Dynamic Tag Management.
keywords: Dynamic Tag Management;data element;create new data element;name;type;default value;force lowercase value;remember this value for
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Criar um elemento de dados
uuid: eacd5c60-6197-4129-a9e1-a39e9a58b38a
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Criar um elemento de dados

Crie um elemento de dados no Dynamic Tag Management.

1. [Criar propriedade da Web](/help/implement/other/dtm/t-create-web-property.md), se ainda não tiver feito.
1. Na propriedade da web, clique em **[!UICONTROL Regras]**>**[!UICONTROL  Elementos de dados]**.
1. Clique em **[!UICONTROL Criar novo elemento de dados]**.
1. Preencha os campos e opções a seguir:

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> Opção</th> 
      <th class="chdeschd"> Descrição</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Nome</strong></td> 
      <td class="chdesc stentry"> <p>O nome fácil do elemento de dados que um profissional de marketing consegue reconhecer. Por exemplo, 
        <code>
          Product ID
        </code>. </p> <p> <p>Observação: o nome é referenciado pelo construtor de regras, não por uma ID. Se você mudar o nome do Elemento de dados, deverá mudar sua referência em todas as regras que o utilizarem. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Tipo</strong></td> 
      <td class="chdesc stentry"> <p> Especifica de onde os dados são extraídos, como Objeto JS, Seletor de CSS, Cookie, Parâmetro de URL ou Script personalizado. </p> <p>Dependendo do tipo selecionado, serão exibidas diferentes opções. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html">Tipos de elementos de dados</a> na documentação do produto do Dynamic Tag Management para obter mais informações e exemplos. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Valor padrão</strong></td> 
      <td class="chdesc stentry"> <p>Um elemento padrão. Esse valor garante que o elemento de dados sempre tenha um valor, mesmo que um parâmetro de URL não exista ou não possa ser encontrado pelo Dynamic Tag Management. </p> <p> <p>Observação: se não houver valor e nenhum valor padrão, nada será retornado. Nenhuma variável que referencie esse elemento de dados será definida. Observe também que o campo de valor padrão será ignorado no caso de um elemento de dados de "código personalizado". </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Forçar valor de minúsculas</strong></td> 
      <td class="chdesc stentry"> <p>O Dynamic Tag Management altera o valor automaticamente para letras minúsculas. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Lembrar deste valor por</strong></td> 
      <td class="chdesc stentry"> <p>Por quanto tempo você deseja que o Dynamic Tag Management se lembre desse valor. </p> <p> Os valores válidos incluem: </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>Sessão: o cronograma baseado na sessão pode variar dependendo da implementação. Os elementos de dados da sessão são definidos para o cookie da sessão. Contudo, essa configuração pode basear-se em um servidor da Web ou no navegador. Ela não se relaciona com a sessão usada no Reports &amp; Analytics de marketing. </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>Pageview </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>Visitante </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   Consulte [Elementos de dados](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html) na documentação do produto do Tag Management da Adobe para obter mais informações sobre como usar elementos de dados.
1. Clique em **[!UICONTROL Salvar o elemento de dados]**.
