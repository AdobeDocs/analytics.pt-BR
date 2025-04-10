---
description: Você pode filtrar pelas dimensões que adiciona à grade de rótulos de linhas. Os filtros restringem os dados retornados pelas solicitações e podem ser aplicados a partir de layouts pivô ou personalizados. Quando você configura a filtragem de dimensões a partir do layout dinâmico, pode especificar, adicionalmente, o número de entradas da célula.
title: Filtrar visão geral das dimensões
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 73%

---

# Filtrar visão geral das dimensões

{{legacy-arb}}

Você pode filtrar pelas dimensões que adiciona à grade de rótulos de linhas. Os filtros restringem os dados retornados pelas solicitações e podem ser aplicados a partir de layouts pivô ou personalizados. Quando você configura a filtragem de dimensões a partir do layout dinâmico, pode especificar, adicionalmente, o número de entradas da célula.

O formulário de filtro selecionado é preenchido com base no elemento e na métrica selecionada na solicitação Report Builder.

## Definir filtro - valores e caracteres especiais {#section_15840216A4044C40974945FAA435AD93}

Informações sobre filtros no painel **[!UICONTROL Filtro mais popular]** > **[!UICONTROL Definir filtro]**.

![Captura de tela mostrando a caixa de diálogo Definir Filtro com opções para Filtrar por Aplicativo, Usuário e Projeto.](/help/admin/admin/assets/filter.png)

As seguintes tabelas fornecem exemplos e informações sobre filtros:

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtro </th> 
   <th colname="col02" class="entry"> Descrição </th> 
   <th colname="col2" class="entry"> Exemplo de filtro </th> 
   <th colname="col3" class="entry"> Resultados da correspondência </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Contém todos os termos </p> </td> 
   <td colname="col02"> <p>Contém cada valor delimitado por espaços em qualquer ordem. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> a b c</span>e <span class="term"> b a c</span>, e assim por diante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contém qualquer termo </p> </td> 
   <td colname="col02"> <p>Contém pelo menos um dos filtros (delimitado por espaços). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, mas não a <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contém a frase </p> </td> 
   <td colname="col02"> <p>Contém o filtro de pesquisa e possivelmente outros termos. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> abc</span> e <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não contém nenhum termo </p> </td> 
   <td colname="col02"> <p>Retorna tudo a não ser que contenha um valor que você inserir. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> d e f</span>, mas não a <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não contém a frase </p> </td> 
   <td colname="col02"> <p>Retorna tudo que não contém sua frase. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Exclui <span class="term"> abc</span>, <span class="term"> abc def</span> e corresponde a <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Igual a </p> </td> 
   <td colname="col02"> <p>Retorna uma correspondência exata. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> é retornado e nada mais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não é igual </p> </td> 
   <td colname="col02"> <p>Retorno qualquer item que não corresponde exatamente à entrada. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Não corresponde a <span class="term"> a</span>. </p> <p>Corresponde a <span class="term"> a b c</span>. </p> <p>Corresponde a <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Começa com </p> </td> 
   <td colname="col02"> <p>Retorna os resultados que começam com um valor específico. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> abcd</span>, mas não a <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Termina com </p> </td> 
   <td colname="col02"> <p>Retorna os resultados que terminam com um valor específico. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Corresponde <span class="term"> wxyz</span>, mas não <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avançado (caracteres especiais) </p> </td> 
   <td colname="col02"> <p>Fornece caracteres regex: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Página*Inicial$" | esportes </p> </td> 
   <td colname="col3"> <p> Isso define um filtro que começa com <span class="term"> Página Inicial</span>, procura zero ou mais caracteres e termina com <span class="term"> Página</span>. </p> <p>Além disso, qualquer página com <span class="term"> esportes</span>. </p> <p>Alguns exemplos de correspondências: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Página inicial e (outros caracteres) </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Página inicial de esportes </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">página de esportes </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">esportes </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz esportes abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caracteres especiais </th> 
   <th colname="col2" class="entry"> Propósito </th> 
   <th colname="col3" class="entry"> Notas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> Igual a </td> 
   <td colname="col3"> <p>Sem espaço a não ser quando emparelhado com outra citação. Por exemplo, <span class="term"> Tela de 17 pol. </span> não é uma frase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Caractere curinga </td> 
   <td colname="col3"> <p>Igual ao asterisco usado em uma expressão regular. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> Começa com </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> Termina com </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> Não </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> Ou </td> 
   <td colname="col3"> <p>Suportado somente no filtro <span class="term"> Avançado (caracteres especiais)</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
