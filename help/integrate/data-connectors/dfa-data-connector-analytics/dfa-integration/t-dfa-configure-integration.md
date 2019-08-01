---
description: Siga as etapas da integração dos Conectores de dados do DFA.
seo-description: Siga as etapas da integração dos Conectores de dados do DFA.
seo-title: Configurar a integração do DFA
title: Configurar a integração do DFA
uuid: 4 c 2 ac 58 a -87 c 6-46 f 3-9033-9404 beb 18 c 39
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configurar a integração do DFA{#configure-the-dfa-integration}

Siga as etapas da integração dos Conectores de dados do DFA.

As páginas de configuração contêm uma visão geral da integração, além de links úteis para mais informações. Há taxas da Adobe e do DoubleClick associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de taxas.

1. Log in to the [!DNL Adobe Analytics].
1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Locate **[!UICONTROL DoubleClick DFA]**, then click **[!UICONTROL Add New]**.

   ![Resultado da etapa](assets/wizard-01.png)

   Em cada página do Assistente de integração, forneça as informações necessárias e clique em **[!UICONTROL Avançar]**. A tabela a seguir explica as informações necessárias para concluir a integração pelo assistente.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página do Assistente # </th> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Nome da integração </td> 
   <td colname="col3"> O nome da integração que o Genesis exibe na lista Integração ativa do conjunto de relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Endereço de email de integração </td> 
   <td colname="col3"> O endereço de email que recebe todas as notificações relacionadas a essa integração. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Nome do usuário </td> 
   <td colname="col3"> O nome de usuário da API do DFA a usar com a integração. Para habilitar um usuário para fazer logon com a API, marque o atributo API na interface do DFA. Depois que você habilitar o logon da API, um campo de senha será exibido para que uma senha seja fornecida para o usuário. Essa senha é inserida junto com o nome de usuário no assistente para autenticação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Senha </td> 
   <td colname="col3"> A senha da API do DFA. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ID do anunciante </td> 
   <td colname="col3"> <p>A ID do anunciante do DFA ou a ID de configuração principal do Floodlight. Os Conectores de dados usam essa ID para identificar o anunciante do DFA a ser monitorado (versão 1.5 da integração). Essa ID de anunciante não é usada na versão 2.0 da integração - a ID de configuração principal do Floodlight será pesquisada e usada. Consulte as instruções na tela. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Variável de publicidade DFA </td> 
   <td colname="col3"> A eVar do Analytics que recebe os dados de atributo, impressões e cliques da campanha do DFA. Normalmente, essa é a eVar do código de rastreamento ( <span class="varname"> s. campaign </span>), mas você pode escolher qualquer evar disponível. Os Conectores de dados também adicionam as seguintes classificações relacionadas ao DFA à eVar selecionada: <p><b>Campanhas</b>: uma coleção de anúncios veiculados em vários sites que transmitem uma mensagem em comum. </p> <p><b>Nome do site</b>: o site no qual o anúncio foi veiculado. </p> <p><b>Nome do anúncio</b>: o nome do anúncio, conforme definido na sua conta do DFA. </p> <p><b>Nome do posicionamento do site</b>: o site e a página da Web nos quais o anúncio foi veiculado. </p> <p><b>Ferramenta de entrega</b>: DoubleClick for Advertisers. </p> <p><b>Canal</b>: anúncio de banner. </p> <p><b>Estrutura de custo</b>: CPM, CPC ou fixo, com base na estrutura de custo do anúncio. </p> <p><b>Nome criativo</b>: o nome da criação associada a uma ID de anúncio/posicionamento/criação. </p> <p><b>DFA &gt; Deduplicação do SearchCenter</b>: especifica que o DFA deve colocar valores em variáveis do SearchCenter quando ocorrem click-throughs ou view-throughs do DFA. Para obter mais informações, consulte <a href="../../dfa-data-connector-analytics/dfa-integration-features.md#concept-ff93289d1662410e98f62c200394b3e3" format="dita" scope="local">Deduplicação do SearchCenter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impressões </td> 
   <td colname="col3"> O evento personalizado que recebe os dados da métrica de impressões do DFA. A métrica de impressões indica o número de vezes que o anúncio foi veiculado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Cliques </td> 
   <td colname="col3"> Selecione o evento personalizado que recebe os dados da métrica de cliques do DFA. A métrica de Cliques indica o número de vezes que os visitantes clicaram no anúncio conforme medido pelo redirecionamento do DFA. A métrica de cliques correlaciona-se com a métrica de click-throughs do Analytics. <p>Observação: as métricas de Cliques do DFA e de Click-throughs do Analytics podem não ser exatamente iguais devido a diferenças no modo de coleta dos dados. For more information, see <a href="../../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-metric-definitions.md#concept-2d5cd5ddd2594bb386a16a2764f30982" format="dita" scope="local"> Metric Definitions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Variável de view-through </td> 
   <td colname="col3"> <p>A eVar do Analytics que recebe os dados de view-through do DFA. A variável de view-through ajuda a ver como os view-throughs afetam as taxas de conversão em seu site. </p> <p>Os Conectores de dados adicionam as mesmas classificações relacionadas ao DFA a essa eVar, assim como fazem com a variável de anúncio do DFA (veja acima). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Tempo desde a última exibição (variável de período de tempo de view-through) </td> 
   <td colname="col3"> A eVar do Analytics que recebe os dados de tempo desde a última exibição do DFA. O Tempo desde a última exibição indica quanto tempo passou desde o último view-through do anúncio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> View-throughs </td> 
   <td colname="col3"> O evento personalizado que recebe os dados da métrica de view-throughs do DFA. Use o evento de View-throughs com a variável de view-through para ver quais campanhas não influenciaram um click-through direto, mas podem ter desempenhado um papel em direcionar tráfego para o site em algum momento subsequente. <p>Os Conectores de dados renomeiam o evento personalizado selecionado para “View Throughs”. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Falha de consulta do DFA </td> 
   <td colname="col3"> (Opcional) A eVar do Analytics que recebe quaisquer códigos de mensagem de falha de consulta do DFA relatada. Os possíveis códigos de mensagem do DFA incluem: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: não há cookie do DoubleClick. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: o usuário cancelou a inscrição. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: não há histórico de campanha. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: erro de consulta (tempo limite, servidor inativo etc.). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Evento de tempo limite </td> 
   <td colname="col3"> <p>O evento de contador do Analytics que aumenta cada vez que o temporizador <span class="varname"> s. maxdelay </span> expira e nenhuma resposta foi recebida dos servidores do DFA. Use this event to configure the <span class="varname"> s.maxDelay </span> variable (see <a href="../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d" format="dita" scope="local"> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

