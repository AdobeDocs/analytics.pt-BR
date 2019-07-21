---
description: Crie um elemento de dados no Dynamic Tag Management.
keywords: Gerenciamento dinâmico de tags; elemento de dados; criar novo elemento de dados; name; type; valor padrão; forçar valor em minúsculas; lembrar este valor para
seo-description: Crie um elemento de dados no Dynamic Tag Management.
seo-title: Criar um elemento de dados
solution: Marketing Cloud, Analytics, Target, Gerenciamento dinâmico de tags
title: Criar um elemento de dados
uuid: eacd 5 c 60-6197-4129-a 9 e 1-a 39 e 9 a 58 b 38 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Criar um elemento de dados

Crie um elemento de dados no Dynamic Tag Management.

1. [Criar propriedade da Web](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123), se ainda não tiver feito.
1. Na propriedade da Web, clique em **Regras** &gt; **[!UICONTROL Elementos de dados]**.
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
          Identificação do produto
        </code>. </p> <p> <p>Observação: o nome é referenciado pelo construtor de regras, não por uma ID. Se você mudar o nome do Elemento de dados, deverá mudar sua referência em todas as regras que o utilizarem. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Tipo</strong></td> 
      <td class="chdesc stentry"> <p> Especifica de onde os dados são extraídos, como Objeto JS, Seletor de CSS, Cookie, Parâmetro de URL ou Script personalizado. </p> <p>Dependendo do tipo selecionado, serão exibidas diferentes opções. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html" format="html" scope="external">Tipos de elementos de dados</a> na documentação do produto do Dynamic Tag Management para obter mais informações e exemplos. </p> </td> 
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
