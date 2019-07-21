---
description: Um conjunto de regras é um grupo de regras de classificação para uma variável específica. Você aplica uma variável ao conjunto de regras. Se deseja criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios.
seo-description: Um conjunto de regras é um grupo de regras de classificação para uma variável específica. Você aplica uma variável ao conjunto de regras. Se deseja criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios.
seo-title: Conjuntos de regras de classificação
solution: Analytics
subtopic: Classificações
title: Conjuntos de regras de classificação
topic: Ferramentas administrativas
uuid: c 4 d 7 b 77 c-fa 98-44 be -955 f -9 aee 7 f 73480 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conjuntos de regras de classificação

Um conjunto de regras é um grupo de regras de classificação para uma variável específica. Você aplica uma variável ao conjunto de regras. Se deseja criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios.

## Classification rule sets {#concept_CD3D510F5070486584F3BB535AE41524}

Um conjunto de regras é um grupo de regras de classificação para uma variável específica. Você aplica uma variável ao conjunto de regras. Se deseja criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios.

## Página do criador de regras de classificação {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Construtor de regras de classificação]**

Os campos e opções a seguir encontram-se disponíveis no [!UICONTROL Construtor de regras de classificações].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B" format="dita" scope="local"> Adicionar conjunto de regras</a> </p> </td> 
   <td colname="col2"> <p>Cria um conjunto de regras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regras </p> </td> 
   <td colname="col2"> Exibe o número de regras incluídas no conjunto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> Exibe o status da atividade do conjunto de regras, como Rascunho ou Ativo. As regras ativas processam diariamente, examinando os dados de classificação normalmente de um mês. As regras verificam automaticamente novos valores e carregam as classificações. </td> 
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

## Create a Classification Rule Set {#task_86F216DFD2534FA181E64ABDF306782B}

<!-- 

t_classification_rule_set.xml

 -->

Atribua um nome ao conjunto de regras de classificação, aplique a variável e defina as configurações de substituição.

1. (Prerequisite) Define the classification structure in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

   (Consulte [Classificações](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=classifications) na página de ajuda das Ferramentas administrativas para ver como adicionar classificações.)

   As variáveis serão exibidas no painel [!UICONTROL Novo conjunto de regras] somente após terem pelo menos uma classificação definida para aquelas variáveis.

   You can create classifications on a variable in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Traffic]** &gt; **[!UICONTROL Traffic Classifications]** (or **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**). Depois, selecione a variável e clique em **[!UICONTROL Adicionar classificação]**.

1. To create the rule set, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]** &gt; **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Name the rule set, then click **[!UICONTROL Create Rule Set]**.
1. Selecione o conjunto de regras a ser editado.

   ![](assets/classification_rules_page.png)

1. Click **[!UICONTROL Select Report Suites and Variables]**.

   A lista de conjunto de relatórios e variáveis é preenchida com todas as variáveis classificadas disponíveis em todos os conjuntos de relatórios em sua empresa de logon. Uma única variável em um conjunto de relatórios pode pertencer a somente um conjunto de regras.

   Consulte *`Variable`* nas definições da página [Construtor de regras de classificação](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4D1A70A607C9419EB2116A5174EACB72) para obter mais informações.
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. Continue by [adding classification rules](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) to the rule set.
