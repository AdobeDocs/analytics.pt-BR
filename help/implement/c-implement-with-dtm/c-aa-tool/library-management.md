---
description: Descrições dos campos e opções nas configurações de Gerenciamento de biblioteca no Dynamic Tag Management.
keywords: gerenciamento de biblioteca;código de página;biblioteca de carregamento em;gerenciado pelo adobe;custom;code hospedado;s_code hospedado
seo-description: Descrições dos campos e opções nas configurações de Gerenciamento de biblioteca no Dynamic Tag Management.
seo-title: Gerenciamento de biblioteca
solution: Experience Cloud,Gerenciamento dinâmico de tags
title: Gerenciamento de biblioteca
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Gerenciamento de biblioteca

Descrições dos campos e opções nas configurações de Gerenciamento de biblioteca no Dynamic Tag Management.

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) Editar ferramenta **[!UICONTROL &gt; Gerenciamento]** **[!UICONTROL de biblioteca]**

>[!NOTE]
>
>Se mais de uma ferramenta do Adobe Analytics for usada em uma única propriedade da Web, cada ferramenta deverá ter um nome de variável de rastreador exclusivo. Nomes de variáveis de objetos duplicados entre ferramentas Adobe Analytics em uma única propriedade da Web causarão conflitos.

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>O código de página já está presente </p> </td> 
   <td colname="col2"> <p> Evita que o Dynamic Tag Management instale o código de página do <span class="keyword">Adobe Analytics</span> se ele já existir no seu site. </p> <p>Esse recurso permite que você use o Dynamic Tag Management para adicionar a sua implementação existente, em vez de começar do zero. Certifique-se de ajustar apropriadamente o nome da variável do rastreador ao marcar esta caixa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carregar biblioteca em &lt;<span class="term"> Parte superior</span> ou <span class="term"> parte inferior</span>da página&gt; </p> </td> 
   <td colname="col2"> <p>Especifica onde e quando carregar o código da página. Qualquer que seja sua seleção, todas as regras que usam a ferramenta Analytics deverão ter a mesma definição. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerenciado pela Adobe (recomendado) </p> </td> 
   <td colname="col2"> <p>Ativar o Dynamic Tag Management para gerenciar sua biblioteca. </p> <p>Caso selecione essa opção, a seguinte opção torna-se disponível: </p> <p> <b>Versão da biblioteca:</b> selecione a versão mais recente no menu <span class="wintitle">Versão da biblioteca</span>. O Dynamic Tag Management notifica quando novas versões são disponibilizadas. É possível reverter para uma versão anterior, conforme for necessário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Personalizado </p> </td> 
   <td colname="col2"> <p>Você pode configurar o código da biblioteca. </p> <p>Se você selecionar essa opção, serão disponibilizados os seguintes itens: </p> <p> <b>Definir conjuntos de relatórios utilizando o código personalizado abaixo:</b> quando esta caixa é marcada, o Dynamic Tag Management busca uma variável no seu código personalizado, chamada <span class="varname"> s_account</span>. Esta variável deve conter uma lista separada por vírgulas dos conjuntos de relatórios para os quais você deseja enviar dados. </p> <p> <b>Código hospedado:</b> escolha uma opção para hospedar o <span class="filepath">s_code</span>: </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>No DTM</b>: você pode hospedar o <span class="filepath">s_code</span> no Dynamic Tag Management. Clique em <span class="uicontrol">Editar código</span> para cortar e colar o arquivo diretamente no editor. </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>: se você tiver um bom arquivo <span class="filepath">s_code</span> e estiver satisfeito com o processo de atualização dele, poderá fornecer o URL para o arquivo aqui. O Dynamic Tag Management consume o arquivo <span class="filepath">s_code</span> para sua implementação do <span class="keyword">Adobe Analytics</span>. </li> 
    </ul> <p> <b>Abrir editor: </b>Permite <a href="../../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658" format="dita" scope="local"> inserir o código</a>principal do AppMeasurement. This code is populated automatically when using the automatic configuration method described in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8" format="dita" scope="local"> Adobe Analytics Settings</a>. </p> <p> <b>Nome da variável do rastreador: </b>Se você quiser executar duas instâncias do <span class="keyword"> Adobe Analytics</span> simultaneamente (uma no Gerenciamento dinâmico de tags e outra nativamente), renomeie o <span class="term"> objeto principal</span> . Renomear o objeto evita colisões. </p> </td> 
  </tr> 
 </tbody> 
</table>

