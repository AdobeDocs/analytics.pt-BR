---
description: Você pode filtrar pelas dimensões que adiciona à grade de rótulos de linhas. Os filtros restringem os dados retornados pelas solicitações e podem ser aplicados a partir de layouts pivô ou personalizados. Ao configurar a filtragem de dimensões no Layout dinâmico, você pode especificar adicionalmente o número de entradas da célula.
title: Filtrar visão geral das dimensões
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
TQID: https://experienceleague.adobe.com/yY1Sl6vEWRb-62SzM5e5qxt5lZPHeg-LU5ZiUNb5z8Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 30%

---

# Filtrar visão geral das dimensões

{{legacy-arb}}

Você pode filtrar pelas dimensões que adiciona à grade de rótulos de linhas. Os filtros restringem os dados retornados pelas solicitações e podem ser aplicados a partir de layouts pivô ou personalizados. Ao configurar a filtragem de dimensões no Layout dinâmico, você pode especificar adicionalmente o número de entradas da célula.

O formulário de filtro selecionado é preenchido com base no elemento e na métrica selecionada na solicitação do Report Builder.

## Definir filtro - valores e caracteres especiais {#section_15840216A4044C40974945FAA435AD93}

Informações sobre filtros no painel **[!UICONTROL Filtro Mais Popular]** > **[!UICONTROL Definir Filtro]**.

![Captura de tela mostrando a caixa de diálogo Definir Filtro com opções para Filtrar por Aplicativo, Usuário e Projeto.](/help/admin/tools/assets/filter.png)

As tabelas a seguir fornecem exemplos e informações sobre filtros:

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
   <td colname="col02"> <p>Contém cada valor delimitado por espaço em qualquer ordem. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> a b c</span>e <span class="term"> b a c</span>, e assim por diante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contém qualquer termo </p> </td> 
   <td colname="col02"> <p>Contém pelo menos um dos filtros (delimitados por espaços). </p> </td> 
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
   <td colname="col02"> <p>Retorna tudo, a menos que contenha um valor inserido. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> d e f</span>, mas não a <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não contém a frase </p> </td> 
   <td colname="col02"> <p>Retorna tudo o que não contém sua frase. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Exclui <span class="term"> abc</span>, <span class="term"> abc def</span> e corresponde a <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Igual </p> </td> 
   <td colname="col02"> <p>Retorna uma correspondência exata. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> é retornado e nada mais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não é igual </p> </td> 
   <td colname="col02"> <p>Retorna qualquer item que não corresponda exatamente à sua entrada. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Não corresponde a <span class="term"> a</span>. </p> <p>Corresponde a <span class="term"> a b c</span>. </p> <p>Corresponde a <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Começa com </p> </td> 
   <td colname="col02"> <p>Retorna resultados que começam com um valor específico. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Corresponde a <span class="term"> abcd</span>, mas não a <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Termina com </p> </td> 
   <td colname="col02"> <p>Retorna resultados que terminam com o valor específico. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Corresponde <span class="term"> wxyz</span>, mas não <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avançado (caracteres especiais) </p> </td> 
   <td colname="col02"> <p>Permite regex de caracteres: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Página*Inicial$" | esportes </p> </td> 
   <td colname="col3"> <p> Isso define um filtro que começa com <span class="term"> Página Inicial</span>, procura zero ou mais caracteres e termina com <span class="term"> Página</span>. </p> <p>Além disso, qualquer página com <span class="term"> esportes</span>. </p> <p>Alguns exemplos correspondem a: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Página inicial e (outros caracteres) </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Esportes em casa </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">página de esportes </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">esportes </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sports abc </li> 
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
   <td colname="col2"> Igual </td> 
   <td colname="col3"> <p>Não será evitado, a menos que não esteja emparelhado com outra citação. Por exemplo, <span class="term"> Tela de 17 pol. </span> não é uma frase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Curinga </td> 
   <td colname="col3"> <p>O mesmo que o asterisco usado em uma expressão regular. </p> </td> 
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
