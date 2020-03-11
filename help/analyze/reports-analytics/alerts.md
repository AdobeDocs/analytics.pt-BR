---
description: 'null'
subtopic: Alerts
title: Alertas
topic: Reports and analytics
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Alertas

## Alertas {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

O Alertas inteligentes é o novo sistema de alertas do Adobe Analytics, e permite criar e gerenciar alertas, completos com a visualização de alertas e a contribuição de regras. É possível

* Criar alertas com base em anomalias (limite de 90%, 95% ou 99%; % de mudança; acima/abaixo).
* Visualizar a frequência de disparo de um alerta.
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente.
* Criar alertas “empilhados”, capazes de capturar várias métricas de uma só alerta.

É possível acessar esse novo sistema de Alertas por meio de **[!UICONTROL Mais]** > **[!UICONTROL Alertas]** em qualquer relatório no Reports &amp; Analytics.

Para obter mais informações, acesse a seção sobre [Alertas inteligentes](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/intellligent_alerts.html) na documentação da Analysis Workspace.

## Adicionar um alerta {#task_51187E8BF19544DDA9EF2057E6F11D35}

Etapas que descrevem como adicionar um alerta no Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Navegue até o novo Construtor de alertas no menu **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]**. No entanto, é possível acessá-lo a partir dos relatórios em Reports &amp; Analytics:

1. Em Reports &amp; Analytics, abra o relatório no qual deseja definir um alerta.
1. Clique em **[!UICONTROL Mais]** > **[!UICONTROL Adicionar alerta]**.
1. Isso levará você ao [novo Construtor de alertas](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/alert-builder.html).

## Visualizar ou editar alertas existentes {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Contexto da tarefa

1. Vá até **[!UICONTROL Análises]** > **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]**. Isso leva você ao novo [Gerenciador de alertas](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/alert-manager.html).

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
   <td colname="col1"> <p>Alertas de visitantes únicos com base em tempo (Visitantes únicos diários, semanais, mensais etc. Visitantes únicos) </p> <p> </p> </td> 
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
   <td colname="col2"> <p>Não é possível <a href="https://marketing.adobe.com/resources/help/pt_BR/reference/ASI_slots_admin.html"  >criar ou editar slots ASI</a> e não estão disponíveis para uso no Analysis Workspace. Portanto, não são compatíveis com os novos alertas. </p> <p> </p> </td> 
   <td colname="col3"> <p>Não disponíveis no novo Gerenciador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas que usam métricas de participação </p> </td> 
   <td colname="col2"> <p>  As <a href="https://marketing.adobe.com/resources/help/pt_BR/reference/metrics_participation.html"  >Métricas de participação</a> estão disponíveis em Reports &amp; Analytics e indisponíveis no novo sistema de alertas na Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>Não disponíveis no novo Gerenciador de alertas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alertas mensais para conjuntos de relatórios de calendário personalizado </p> </td> 
   <td colname="col2"> <p>Isso afeta apenas os clientes com alertas configurados para conjuntos de relatórios que têm <a href="https://marketing.adobe.com/resources/help/pt_BR/arb/custom_calendar.html"  >datas personalizadas de início de mês</a> (Federação Nacional de Varejo/NRF e tipos de calendários personalizados). </p> <p>Não afeta alertas em conjuntos de relatórios do calendário gregoriano ou gregoriano modificado. Anteriormente, esses alertas eram enviados no primeiro dia do mês gregoriano (por exemplo, 1º de janeiro, 1º de fevereiro etc). Isso não funcionará com o novo recurso de alertas Detecção de anomalias, que considera dados de meses anteriores ao detectar anomalias. No futuro, adicionaremos suporte ao sistema de programação para calendários personalizados de modo que os Alertas e os Projetos programados possam ser programados para envio no primeiro dia do mês do calendário personalizado em vez do primeiro dia do mês gregoriano. </p> <p> </p> </td> 
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

