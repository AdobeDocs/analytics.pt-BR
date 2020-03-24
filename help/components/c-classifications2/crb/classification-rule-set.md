---
description: Um conjunto de regras é um grupo de regras de classificação para uma variável específica. Você aplica uma variável ao conjunto de regras. Se quiser criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios.
subtopic: Classifications
title: Conjuntos de regras de classificação
topic: Admin tools
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# Conjuntos de regras de classificação

Um conjunto de regras é um grupo de regras de classificação para uma variável específica. Você aplica uma variável ao conjunto de regras. Se quiser criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios.

## Conjuntos de regras de classificação

Um conjunto de regras é um grupo de regras de classificação para uma variável específica. Você aplica uma variável ao conjunto de regras. Se quiser criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios.

## Página do criador de regras de classificação  {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Os campos e opções a seguir estão disponíveis no [!UICONTROL Classifications Rule Builder].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/c-classifications2/crb/classification-rule-set.md"  > Adicionar conjunto de regras</a> </p> </td> 
   <td colname="col2"> <p>Cria um conjunto de regras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regras </p> </td> 
   <td colname="col2"> Exibe o número de regras contidas no conjunto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> Exibe o status de atividade do conjunto de regras, como Rascunho ou Ativo. As regras ativas processam diariamente, examinando os dados de classificação normalmente de um mês. As regras verificam automaticamente novos valores e carregam as classificações. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Última alteração </p> </td> 
   <td colname="col2"> Indica quando o conjunto de regras foi editado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duplicar </p> </td> 
   <td colname="col2"> Duplica (copia) um conjunto de regras, de modo que você possa aplicar o conjunto de regras a outra variável, ou à mesma variável em um conjunto de relatório diferente. </td> 
  </tr> 
 </tbody> 
</table>

## Criar um conjunto de regras de classificação {#create-classification-rule-set}

Atribua um nome ao conjunto de regras de classificação, aplique a variável e defina as configurações de substituição.

1. (Pré-requisito) Defina a estrutura de classificação em **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

   (Consulte [Classificações](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) na ajuda das Ferramentas administrativas para adicionar classificações.)

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   É possível criar classificações em uma variável em **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Traffic]** > **[!UICONTROL Traffic Classifications]** (ou **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**). Then select the variable, then click **[!UICONTROL Add Classification]**.

1. Para criar o conjunto de regras, clique em **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Nomeie o conjunto de regras e clique em **[!UICONTROL Create Rule Set]**.
1. Selecione o conjunto de regras a ser editado.

   ![](assets/classification_rules_page.png)

1. Clique em **[!UICONTROL Select Report Suites and Variables]**.

   O conjunto de relatórios e a lista de variáveis são preenchidos com todas as variáveis classificadas disponíveis em todos os conjuntos de relatórios na empresa de logon. Uma única variável em um conjunto de relatórios pode pertencer a apenas um conjunto de regras.

   See *`Variable`* in the definitions for the [Classification Rule Builder](/help/components/c-classifications2/crb/classification-rule-definitions.md) page for more information.
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. Continue [adicionando regras de classificação](/help/components/c-classifications2/crb/classification-rule-set.md) ao conjunto de regras. 
