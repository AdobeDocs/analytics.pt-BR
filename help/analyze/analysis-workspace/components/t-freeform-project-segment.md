---
description: 'null'
seo-description: 'null'
seo-title: Segmentos
title: Segmentos
uuid: 677 f 6030-5 b 3 e -4 dfa-bb 79-9 f 27 f 3382 fb 1
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Segmentos {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

O painel de segmentos do menu de Componentes mostra segmentos e modelos de segmentos, indicados por estes ícones:

![](assets/segment_icons.png)

[Uso de segmentos na Analysis Workspace no youtube](https://www.youtube.com/watch?v=QlUCdQDnni4)(6:46)

## Create segments {#section_693CFADA668B4542B982446C2B4CF0F5}

É possível criar segmentos instantâneos ao soltar qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, segmento, modelo de segmento, intervalo de datas) na zona de segmentos na parte superior de um painel.

Os tipos de componentes são convertidos automaticamente em segmentos. Como alternativa, você pode clicar no sinal "+" na caixa Adicionar segmento.

Lembre-se:

* **Não** é possível soltar os seguintes tipos de componentes na zona de segmentos: métricas calculadas e dimensões/métricas; a partir dos quais não pode-se criar segmentos.
* Para dimensões e eventos completos, a Analysis Workspace cria segmentos de ocorrência "existe". Exemplos: “Ocorrência em que eVar1 existe” ou “Ocorrência em que event1 existe”.
* Se "não especificado" ou "nenhum" for solto na área de segmentos, ele será convertido automaticamente em um segmento "não existe" para que seja tratado corretamente na segmentação.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Os segmentos criados dessa forma são internos ao projeto.

Você pode escolher se deseja tornar os segmentos públicos (globais) seguindo estas etapas:

1. Passe o mouse sobre o segmento no local onde os segmentos são colocados e clique no ícone “i”.
1. No painel de informações que é exibido, clique em **[!UICONTROL Tornar público]**.

   ![](assets/segment-info.png)

## Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

Existem vários outros métodos para aplicar os segmentos em um projeto de forma livre.

<table id="table_45B3839D70674430AF3AC5AA3134F825"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ação </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Criar segmento a partir da seleção </p> </td> 
   <td colname="col2"> <p>Criar um segmento em linha. Selecione as linhas, clique com o botão direito do mouse na seleção, em seguida, crie um segmento em linha. Este segmento se aplica somente ao projeto aberto e não é salvo como um segmento de Análise. </p> <p> 
     <ol id="ol_1D1E661387354EBF992CC150915F642E"> 
      <li id="li_B96666FD426F4AEE8EAB61B2C00A07FB">Selecione as linhas. </li> 
      <li id="li_C2245B3EA81F4FAC88A33647922535AF">Clique com o botão direito na seleção. </li> 
      <li id="li_AB4F8988B9A84920ABA06A91094625F6">Clique em <span class="uicontrol">Criar segmento a partir da seleção</span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Componentes</span> &gt; <span class="uicontrol">Novo segmento</span> </td> 
   <td colname="col2"> <p>Exibe o <span class="wintitle">Construtor de segmentos</span>. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html" format="https" scope="external">Criar segmentos</a> para obter mais informações sobre a segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="ignoretag"><span class="uicontrol"> Compartilhar</span> &gt; <span class="uicontrol">Compartilhar projeto</span></span> ou </p> <p> <span class="ignoretag"><span class="uicontrol">Compartilhar</span> &gt; <span class="uicontrol">Preparar dados do projeto</span></span> </p> </td> 
   <td colname="col2"> <p>In <a href="../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6" format="dita" scope="local"> Curate &amp; Share</a>, segments that you apply to the project are available in shared analysis for the recipient. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usar segmentos como Dimensões </p> </td> 
   <td colname="col2"> <p>Vídeo: <a href="https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39" format="https" scope="external">Usar segmentos como Dimensões na Analysis Workspace</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

