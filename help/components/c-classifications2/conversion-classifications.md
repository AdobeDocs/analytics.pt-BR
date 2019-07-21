---
description: Classificações são usadas para categorizar valores em grupos e relatórios no nível de grupo. Por exemplo, você pode classificar todas as campanhas de Pesquisa paga em uma categoria como termos de música pop e relatar o sucesso dessa categoria com relação a métricas como Instâncias (click-throughs) e a conversão para eventos bem-sucedidos.
seo-description: Classificações são usadas para categorizar valores em grupos e relatórios no nível de grupo. Por exemplo, você pode classificar todas as campanhas de Pesquisa paga em uma categoria como termos de música pop e relatar o sucesso dessa categoria com relação a métricas como Instâncias (click-throughs) e a conversão para eventos bem-sucedidos.
seo-title: Classificações de conversão
solution: Analytics
subtopic: Classificações
title: Classificações de conversão
topic: Ferramentas administrativas
uuid: 4 c 8726 c 9-f 527-44 e 1-be 01-8 c 7 b 3 b 5 c 20 f 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Classificações de conversão

Classificações são usadas para categorizar valores em grupos e relatórios no nível de grupo. Por exemplo, você pode classificar todas as campanhas de Pesquisa paga em uma categoria como termos de música pop e relatar o sucesso dessa categoria com relação a métricas como Instâncias (click-throughs) e a conversão para eventos bem-sucedidos.

## Conversion classifications {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

Classificações são usadas para categorizar valores em grupos e relatórios no nível de grupo. Por exemplo, você pode classificar todas as campanhas de Pesquisa paga em uma categoria como *termos de música pop* e relatar o sucesso dessa categoria com relação a métricas como Instâncias (click-throughs) e conversão para eventos bem-sucedidos.

As classificações de conversão permitem que você classifique as variáveis de conversão. Depois de classificado, qualquer relatório que você puder gerar usando o dado-chave também poderá ser gerado com as propriedades de dados associadas.

Depois de habilitar as classificações, utilize o [Importador de classificações](../../components/c-classifications2/c-classifications-importer/c-working-with-saint.md#concept_08ED8C7A86C64E7DA5DE3044BB94B2EA) para atribuir valores específicos à classificação apropriada.

## Descrições de classificações de conversão {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nome</span> </td> 
   <td colname="col2"> O nome da classificação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ativado por data (somente texto)</span> </td> 
   <td colname="col2"> <p>Indica se a classificação de texto é um intervalo de datas para variáveis de campanha. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Opções (somente texto)</span> </td> 
   <td colname="col2">Cria uma lista de valores de classificação disponíveis para esta classificação. Use as <span class="wintitle">opções</span> com variáveis de campanha para fornecer aos usuários uma lista dos valores suportados com a classificação no <span class="wintitle">Gerenciador de campanhas</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tipo de número (somente numérico)</span> </td> 
   <td colname="col2">Especifica o tipo de número na classificação numérica. As opções incluem <span class="wintitle">Numérico</span>, <span class="wintitle">Porcentagem</span> e <span class="wintitle">Moeda</span>. </td> 
  </tr> 
 </tbody> 
</table>

## Adicionar classificações de conversão {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

Etapas que descrevem como adicionar classificações de conversão na Administração.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Selecione um conjunto de relatórios.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1. Na lista suspensa **Selecionar tipo de classificação**, selecione a variável à qual deseja adicionar uma classificação.

   ![Informações da etapa](assets/sub_class_create.png)

1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Add Classification]**.
1. No campo **Selecionar tipo**, selecione o tipo de classificação que deseja adicionar à variável.

   As opções incluem **[!UICONTROL Texto]** e **[!UICONTROL Numérico]**. For more information on classification types, see [About Classifications](../../components/c-classifications2/c-classifications.md#concept_4CEC7FF1A9E24204A7DA6B9AC70709DE).
1. In the **[!UICONTROL Text Classifications]** dialog box, configure the classification as desired.

   Consulte [Descrições de classificações de conversão](../../components/c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4) para obter informações sobre esses elementos.

1. In the **[!UICONTROL Dropdown List]** dialog box, add or remove options.

   Adicionar Opções cria uma lista com os valores de classificação disponíveis para essa classificação. Você pode usar esta opção com variáveis de Campanha para fornecer aos usuários uma lista dos valores suportados para a classificação no Gerenciador de campanhas. Utilize isso para dimensões de classificação nas quais há uma pequena quantidade de valores permitidos que mudam raramente ou quase nunca. Por exemplo, você pode executar campanhas diferentes direcionadas para os diferentes níveis de fidelidade do cliente: Silver, Gold e Platinum. É possível utilizar a lista suspensa para garantir que os valores aceitos sejam apenas os que correspondem aos três níveis. Se alguém tentar utilizar um valor diferente, este será descartado.
1. Clique em **[!UICONTROL Salvar]**.

## Excluir uma classificação de conversão {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

Exclua uma classificação de conversão quando ela não for mais necessária.

1. Open the Report Suite Manager by clicking **[!UICONTROL Admin]**&gt; **[!UICONTROL Report Suites]** in the Suite header.
1. Selecione um conjunto de relatórios.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1. Na lista suspensa **Selecionar tipo de classificação**, selecione a variável da qual deseja excluir uma classificação.
1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Delete Classification]**.
1. Na caixa de diálogo Excluir classificação, clique em **[!UICONTROL Excluir]**.
