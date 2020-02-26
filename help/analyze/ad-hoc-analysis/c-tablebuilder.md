---
description: Use o Construtor de tabela para criar um relatório com qualquer configuração de métricas, dimensões e segmentos. Por exemplo, você pode adicionar várias métricas ao Construtor de tabela e aplicar o segmento a todos ao mesmo tempo. Você pode aplicar itens pelos painéis de ferramentas como linhas e detalhamentos ou como colunas e facilmente girar a tabela para obter uma visualização diferente. Depois de criar a tabela, você pode interagir diretamente com a tabela de dados resultante para realizar análises mais detalhadas. Lembre-se de que gerar uma tabela de dados pelo Construtor de tabela executa uma consulta e cria uma nova tabela de dados.
title: Criador de tabela
uuid: d5dbd05e-9ebd-4571-b3a5-3856c28b65f3
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Criador de tabela

Use o Construtor de tabela para criar um relatório com qualquer configuração de métricas, dimensões e segmentos. Por exemplo, você pode adicionar várias métricas ao Construtor de tabela e aplicar o segmento a todos ao mesmo tempo. Você pode aplicar itens pelos painéis de ferramentas como linhas e detalhamentos ou como colunas e facilmente girar a tabela para obter uma visualização diferente. Depois de criar a tabela, você pode interagir diretamente com a tabela de dados resultante para realizar análises mais detalhadas. Lembre-se de que gerar uma tabela de dados pelo Construtor de tabela executa uma consulta e cria uma nova tabela de dados.

## Criador de tabela {#concept_574FEDC73B244101935D3C86C39DB70F}

Use o Construtor de tabela para criar um relatório com qualquer configuração de métricas, dimensões e segmentos. Por exemplo, você pode adicionar várias métricas ao Construtor de tabela e aplicar o segmento a todos ao mesmo tempo. Você pode aplicar itens pelos painéis de ferramentas como linhas e detalhamentos ou como colunas e facilmente girar a tabela para obter uma visualização diferente. Depois de criar a tabela, você pode interagir diretamente com a tabela de dados resultante para realizar análises mais detalhadas. Lembre-se de que gerar uma tabela de dados pelo Construtor de tabela executa uma consulta e cria uma nova tabela de dados.

O [!UICONTROL Criador de tabela] não está disponível para determinados relatórios de definição de caminho como o [!UICONTROL de Análise do site], [!UICONTROL de Fallout], [!UICONTROL de Fluxo] e [!UICONTROL de Foco virtual].

## Descrições do construtor de tabelas  {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Linhas/Divisões</span> </td> 
   <td colname="col2"> <p>Cria linhas e divisões de itens adicionados. O primeiro item que você arrastar para <span class="wintitle">Linhas/Divisões</span> se torna a coluna da esquerda na tabela de dados, ou o item pai em uma divisão. Adicionar um item subsequente cria divisões. </p> <p>Por exemplo, se você adicionar dimensões de Página e depois de Cidades, o relatório divide a página por cidades. Você configura quantas linhas e divisões quer mostrar em cada item, usando os seguintes menus: </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300">  <span class="uicontrol">Mostrar</span> e <span class="uicontrol">Dividir</span>: Permite que você especifique o número de itens e divisões a serem exibidos. </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol"> Padrão</span>: Usa as configurações em <span class="wintitle">Propriedades de divisões</span>. </li> 
    </ul> <p>Você também pode configurar uma lista de valor fixo para, por exemplo, dividir uma métrica por várias métricas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Propriedades de divisões</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>Permite que você especifique configurações padrão para quantas linhas e divisões você desejar exibir, baseado na ordem em que você adicionou os itens. Você pode especificar quantos resultados totais por página exibir e quantas linhas deseja dividir. </p> <p>As configurações que você fizer no <span class="wintitle">Criador de tabela</span> sobrescreve as configurações padrão nas <span class="wintitle">Propriedades de divisão</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Editar itens</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>Escolha uma lista de dimensões de itens para criar uma lista fixa de análise. Quando você adiciona itens à lista, eles se tornam persistentes em um relatório salvo e não serão recolhidos quando você abrir um relatório salvo ou programando. </p> <p>Consulte  <a href="/help/analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841"  > Analisar os dados da tabela</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Colunas</span> </td> 
   <td colname="col2"> <p>Permite que você construa colunas com itens de dimensões, segmentos e métricas. Você pode colocar a coluna no eixo usando o ícone de seta, que coloca nos eixos X e Y. </p> <p> <span class="uicontrol"> Mostrar</span>: Permite que você limite o número de colunas geradas na tabela de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Resumo</span> </td> 
   <td colname="col2"> <p>Mostra o layout estrutural do relatório para que você saiba quantas linhas e colunas serão criadas. O resumo reflete a configuração especificada nos grupos <span class="uicontrol">Linhas / Divisões</span> e <span class="uicontrol">Colunas</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Substituir tabela</span> </td> 
   <td colname="col2"> <p>Constrói (e sobrescreve) a tabela existente, baseado em sua configuração <span class="wintitle">Criador de tabela</span>. </p> <p>Observação: Clicar em <span class="uicontrol">Substituir tabela</span> executa novamente o relatório e sobrescreve os dados na grade da tabela. Se você adicionar itens à grade da tabela, a correlação entre a tabela e o <span class="wintitle">Criador de tabela</span> não é mais válida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aviso </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>Indica que a configuração do <span class="wintitle">Criador de tabela</span> não retornará dados e que nenhuma métrica foi selecionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gerar um Relatório pelo Criador de tabela {#task_B04801AC9848485C93DF02E96C9A9902}

Etapas que descrevem como usar o [!UICONTROL Construtor de tabela].

<!-- 

t_table_builder.xml

 -->

1. Para acessar o [!UICONTROL Criador de tabela], execute um relatório suportado e clique em **[!UICONTROL Criador de tabela]**.
1. Arraste itens (dimensões, métricas, segmentos) do painel de ferramenta para o [!UICONTROL Criador de tabela].
1. Configure os itens como linhas, divisões e colunas.
1. Clique em **[!UICONTROL Substituir tabela]** para gerar o relatório.

   Clicar em **[!UICONTROL Substituir tabela]** executa uma nova consulta e cria uma nova tabela de dados. Edições manuais na tabela de detalhes não são refletidas no Criador de tabela.

