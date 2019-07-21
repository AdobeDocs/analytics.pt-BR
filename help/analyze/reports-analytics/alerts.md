---
description: 'null'
seo-description: 'null'
seo-title: Alertas
solution: Analytics
subtopic: Alertas
title: Alertas
topic: Reports and Analytics
uuid: e 1333 a 9 b-eba 0-45 b 7-b 7 e 6-46 e 06190 db 64
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Alertas

## Alertas {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

Como novo sistema de alertas para todo o Adobe Analytics, os Alertas inteligentes permitem que você crie e gerencie alertas, completo com visualização de alertas e contribuição de regras. É possível 

* Criar alertas com base em anomalias (limite de 90%, 95% ou 99%; % de mudança; acima/abaixo).
* Visualizar a frequência de disparo de um alerta.
* Enviar alertas por email ou SMS com links para projetos da Analysis Workspace gerados automaticamente.
* Criar alertas “empilhados”, capazes de capturar várias métricas de uma só alerta.

You can access this new Alerts system from **[!UICONTROL More]** &gt; **[!UICONTROL Alerts]** in any report in Reports &amp; Analytics.

Para obter mais informações, acesse a seção sobre [Alertas inteligentes](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html) na documentação da Analysis Workspace.

## Adicionar um alerta {#task_51187E8BF19544DDA9EF2057E6F11D35}

Etapas que descrevem como adicionar um alerta no Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Navigate to the new Alert Builder in the **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** menu. No entanto, é possível acessá-lo a partir dos relatórios em Reports &amp; Analytics:

1. Em Reports &amp; Analytics, abra o relatório no qual deseja definir um alerta.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.
1. Isso levará você ao [novo Construtor de alertas](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-builder.html).

## Visualizar ou editar alertas existentes {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Contexto da tarefa

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]**. Isso leva você ao novo [Gerenciador de alertas](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-manager.html).

## Migração de alertas herdados {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Vários recursos dos alertas atuais do Analytics não serão incluídos no novo Gerenciador de alertas, que será lançado (como parte da Analysis Workspace) no último trimestre de 2016. A tabela a seguir apresenta uma lista com os recursos de alertas obsoletos, além de recursos de alertas que serão migrados para o novo Gerenciador de alertas em um novo formato.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recurso de alertas herdados </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Obsoleto ou migrado? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Totais (todos os itens) </p> </td> 
   <td colname="col2"> <p>Crie alertas em todos os itens de um relatório de dimensão. </p> </td> 
   <td colname="col3"> <p>Em alguns casos, se você criar um alerta em todos os itens de um relatório de dimensão ou se configurar o alerta apenas na métrica agregada por ele próprio (não aplicado a uma dimensão), ocorrerá o mesmo resultado. Por exemplo, suponhamos que você crie um alerta mensal Todos os itens na métrica "Receita". É possível obter o mesmo resultado com a execução do relatório Receita e a configuração de um alerta mensal nesse relatório. </p> <p>Nesta situação, o alerta herdado Totais (todos os itens) não estará mais disponível e será migrado para a versão mais simples e recente. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mil itens principais </p> <p> </p> </td> 
   <td colname="col2"> <p>Crie alertas para os mil itens principais em um relatório. </p> </td> 
   <td colname="col3"> <p>Não estão mais disponíveis no novo Gerenciador de Alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas de visitantes únicos com base em tempo (Visitantes únicos diários, semanais, mensais etc. ) </p> <p> </p> </td> 
   <td colname="col2"> <p>Crie alertas para relatórios de visitantes únicos diários, semanais, mensais e por hora. </p> </td> 
   <td colname="col3"> <p>No novo Gerenciador de alertas, não haverá mais suporte para alguns alertas de visitantes únicos com base em tempo. Por exemplo, onde você definiu um alerta semanal para visitantes únicos diários, pode definir um alerta diário, mensal etc. na métrica Visitantes únicos mais adiante. (A Analysis Workspace é compatível com uma métrica Visitantes exclusivos, mas é incompatível com métricas de Visitantes únicos diários/semanais/mensais/etc.) </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pesquisar </p> </td> 
   <td colname="col2"> <p>Crie alertas para um relatório de dimensão com uma pesquisa aplicada. Aplica-se apenas a "Totais" ("Todos os itens") ou "Mil itens principais". </p> <p> </p> </td> 
   <td colname="col3"> <p>Não estão mais disponíveis no novo Gerenciador de Alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Relatórios específicos do Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p>Crie alertas para os diversos relatórios que existem em Reports &amp; Analytics e não correspondem a um relatório da Analysis Workspace, como 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Comprimento do caminho </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bots </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Fusos horários </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Domínios de nível superior </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>Não estão mais disponíveis no novo Gerenciador de Alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas com um slot ASI como o conjunto de relatórios </p> </td> 
   <td colname="col2"> <p>Não é possível <a href="https://marketing.adobe.com/resources/help/en_US/reference/ASI_slots_admin.html" format="https" scope="external">criar ou editar slots ASI</a> e não estão disponíveis para uso no Analysis Workspace. Portanto, não são compatíveis com os novos alertas. </p> <p> </p> </td> 
   <td colname="col3"> <p>Não disponíveis no novo Gerenciador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas que usam métricas de participação </p> </td> 
   <td colname="col2"> <p>  As <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_participation.html" format="https" scope="external">Métricas de participação</a> estão disponíveis em Reports &amp; Analytics e indisponíveis no novo sistema de alertas na Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>Não disponíveis no novo Gerenciador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas mensais para conjuntos de relatórios de calendário personalizado </p> </td> 
   <td colname="col2"> <p>Isso afeta apenas os clientes com alertas configurados para conjuntos de relatórios que têm <a href="https://marketing.adobe.com/resources/help/en_US/arb/custom_calendar.html" format="https" scope="external">datas personalizadas de início de mês</a> (Federação Nacional de Varejo/NRF e tipos de calendários personalizados). </p> <p>Não afeta alertas em conjuntos de relatórios do calendário gregoriano ou gregoriano modificado. Anteriormente, esses alertas eram enviados no primeiro dia do mês gregoriano (por exemplo, 1º de janeiro, 1º de fevereiro etc). Isso não funcionará com o novo recurso de alertas Detecção de anomalias, que considera dados de meses anteriores ao detectar anomalias. No futuro, adicionaremos suporte ao sistema de programação para calendários personalizados de modo que os Alertas e os Projetos programados possam ser programados para envio no primeiro dia do mês do calendário personalizado em vez do primeiro dia do mês gregoriano. </p> <p> </p> </td> 
   <td colname="col3"> <p>Ainda não disponíveis no novo Gerenciador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas que não foram executados desde setembro de 2015. </p> </td> 
   <td colname="col2"> <p>Não foram executados desde setembro de 2015 pelos seguintes motivos: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">Você clicou em "Desativar" no alerta no Gerenciador de alertas. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">O alerta apresenta erros e nunca é concluído com sucesso. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> Esses alertas não serão migrados para o novo sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alertas marcados como "desativados" </td> 
   <td colname="col2"> No momento, não existe uma forma de desativar/reativar alertas na nova interface de usuário, embora haja planos para adicionar essa funcionalidade. <p> </p> </td> 
   <td colname="col3"> Esses alertas não serão migrados para o novo sistema. </td> 
  </tr> 
 </tbody> 
</table>

