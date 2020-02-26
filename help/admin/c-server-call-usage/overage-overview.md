---
description: 'null'
title: Visão geral do uso de chamadas do servidor
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visão geral do uso de chamadas do servidor

## Por que monitorar e enviar alertas sobre o uso de chamadas do servidor? {#section_060C29BF1D00444B85892AD1FCF55290}

O Uso de chamadas do servidor do Adobe Analytics reconhece suas solicitações de transparência em dados de uso de chamada do servidor do navegador e de dispositivos móveis. Permite acessar:

* Um painel de Uso de chamadas do servidor que monitora seus dados de consumo de chamadas do servidor e os compara ao seu limite contratual. (**[!UICONTROL Analytics > Administrador > Uso de chamadas do servidor]**)
* Um tipo de alerta de Uso de chamada de servidor no Criador de alertas que permite configurar alertas para evitar sobreposições (**[!UICONTROL Analytics > Componentes > Alertas]**)

Dentre as principais vantagens do Uso de chamadas do servidor, encontram-se:

* **Visibilidade** para seus dados de consumo e de compromisso de chamadas do servidor, incluindo consumo móvel de acordo com seu limite contratual de uso de chamadas do servidor.
* **Alertas** para notificá-lo sobre o risco ou a ocorrência de um excedente e prepará-lo para executar uma ação no caso de possíveis excedentes incorrentes.

Anteriormente, apesar de poder acessar dados mensais de consumo de chamadas do servidor em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Faturamento]**, esses dados eram atualizados somente seis dias depois do fechamento do faturamento do mês. Além disso, os dados não incluíam consumo móvel. Esse recurso substituirá o relatório **[!UICONTROL Informações de faturamento]** atual em **[!UICONTROL Analytics]** > **[!UICONTROL Relatórios]** .

## Pré-requisitos {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permissões:** para acessar o Painel de Uso de chamadas do servidor e o Criador/Gerenciador de alertas, é necessário ser um Administrador do Adobe Analytics.
* **Permissões:** administradores podem conceder acesso a não administradores: a permissão chama-se **[!UICONTROL Uso de chamadas do servidor]**. Consulte [Permissão de uso de chamadas do servidor](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Terminologia importante {#section_CBA348A039F34563B097CD8890AB358D}

Veja abaixo um breve guia sobre a terminologia essencial do Uso de chamadas do servidor:

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Termo </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chamada do servidor </p> </td> 
   <td colname="col2"> <p>Uma chamada de servidor, também conhecida como "ocorrência" ou uma "solicitação de imagem", é uma instância na qual os dados são enviados para os servidores da Adobe para processamento. O tipo de chamada mais comum do servidor é uma exibição de página. Uma exibição de página ocorre onde um visitante visita uma página do site e uma chamada de servidor é gerada para a Adobe, onde as informações são coletadas, processadas e incluídas nas métricas de relatório. </p> <p>Há outros tipos de chamadas do servidor, incluindo links de saída e downloads de arquivo, nos quais os dados são enviados até a Adobe para processamento, mas não são registrados como uma nova visualização de página. Mesmo exibições de página "excluídas" (excluídas de seus relatórios pelo intervalo de endereço IP configurado por você, por exemplo) são chamadas de servidor porque são recebidas e processadas pela Adobe, mas nunca mostradas em seus relatórios. </p> <p><b>Chamada do servidor primária</b>: solicitações recebidas diretamente de navegadores dos visitantes ao site ou da API de inserção de dados. Inclui Ocorrências primárias (Visualizações de página), Eventos personalizados primários, Eventos de download primários e Eventos de saída primários. </p> <p><b>Chamada do servidor secundária</b>: cópias das Chamadas do servidor primárias criadas por marcas de vários conjuntos ou copiadas/movidas por uma regra VISTA. Se uma chamada de servidor secundária tiver sido movida (não copiada) para um conjunto de relatórios diferente por uma regra VISTA, as chamadas secundárias acumuladas são substraídas das chamadas de servidor primárias. </p> <p><b>Chamada do servidor primária móvel</b> </p> <p>Solicitações recebidas diretamente de um dos Mobile SDKs. Inclua trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Chamada do servidor secundária móvel</b> </p> <p>Cópias das Chamadas do servidor primárias criadas por marcas de vários conjuntos ou copiadas/movidas por uma regra VISTA. Se uma chamada de servidor secundária tiver sido movida (não copiada) para um conjunto de relatórios diferente por uma regra VISTA, as chamadas secundárias acumuladas são substraídas das chamadas de servidor primárias. </p> <p>Observação: se sua empresa tiver direitos por contrato a ter somente Chamadas do servidor móveis (Primárias ou Secundárias), seu uso específico da web e de dispositivos móveis contará em relação a seu compromisso específico de dispositivos móveis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de faturamento (ID de faturamento) </p> </td> 
   <td colname="col2"> <p>A entidade jurídica que é cobrada por chamadas do servidor. Por exemplo, adobe.com. Cada empresa de faturamento tem uma ID de faturamento usada para identificar de maneira excluisva o cliente de faturamento. Uma ID de faturamento pode ser vinculada a várias Organizações da Experience Cloud Orgs; nem sempre há uma relação mutuamente exclusiva entre uma organização e uma ID de faturamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de logon </p> </td> 
   <td colname="col2"> <p>Uma empresa de faturamento pode ter <a href="https://helpx.adobe.com/br/analytics/kb/multiple-login-companies.html">várias empresas de logon </a>. Uma empresa de logon é uma coleção de conjuntos de relatórios utilizada pela organização. Algumas organizações possuem várias empresas de logon, que se aplicam a setores diferentes da organização. Isso é útil para organizações de grande porte, que lidam com várias unidades comerciais nas quais vários conjuntos de relatórios não se aplicam a outros na empresa. </p> <p>Frequentemente, essas são as subsidiárias regionais de uma empresa. O exemplo a seguir apresenta empresas de logon e seus respectivos conjuntos de relatorios associados: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Observação: dados de uso de chamadas do servidor referentes a <u>todos</u> os conjuntos de relatórios em uma empresa de faturamento ficam visíveis para todos os usuários com as <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">permissões</a> apropriadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organização da Experience Cloud </p> </td> 
   <td colname="col2"> <p>Uma organização é a entidade que permite a um administrador configurar grupos e usuários, além de controlar o logon único na Experience Cloud. A organização funciona como uma empresa de logon que abrange os produtos e as soluções da Experience Cloud. </p> <p>Frequentemente, a organização é o nome da empresa. Contudo, uma empresa pode ter muitas organizações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compromisso de chamada do servidor </p> </td> 
   <td colname="col2"> <p>Quando a sua empresa assina um contrato com a Adobe, a equipe da Adobe Sales identifica com você, o cliente, os tipos (Primárias, Secundárias, Primárias móveis e Secundárias móveis) e o número aproximado de chamadas do servidor que você espera incorrer ao longo do período de validade do contrato. Esse é seu compromisso total de chamadas do servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Período de uso </p> </td> 
   <td colname="col2"> <p>Para fins de monitoramento de uso de chamadas do servidor, esse compromisso total é detalhado em períodos de uso menores (como 3 meses) para facilitar comparações entre anos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Período do contrato </p> </td> 
   <td colname="col2"> <p>Períodos contratuais podem durar vários anos. Suponhamos que sua empresa tenha um compromisso de chamadas do servidor de 6 milhões de chamadas para um período de contrato de 3 anos. Para fins de monitoramento de uso de chamadas do servidor, esse período de 3 anos pode ser detalhado em períodos de uso menores para facilitar comparações entre anos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Permissão de uso de chamadas do servidor {#section_FCC58EB635954A32990D4E67B52B4369}

A permissão de Uso de chamadas do servidor é concedida automaticamente a Administradores do Analytics. Ela permite que usuários visualizem o painel e criem alertas de chamada do servidor. Adminstradores podem optar por conceder essa permissão a não administradores.

> [!NOTE] Sua empresa pode escolher quais empresas de logon terão acesso ao Uso de chamadas do servidor.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da permissão </th> 
   <th colname="col3" class="entry"> Conceder permissões se você estiver conectado à Adobe Analytics (logon herdado) </th> 
   <th colname="col4" class="entry"> Conceder permissões se você estiver conectado à Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uso de chamadas do servidor </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Faça logon no Analytics via sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Navegue até <span class="ignoretag"> <span class="uicontrol">Admin</span> &gt; <span class="uicontrol">Gerenciamento de usuários</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar todo o acesso a relatórios</span> &gt; <span class="uicontrol">Ferramentas do Analytics</span> &gt; <span class="uicontrol">Personalizar</span> &gt; <span class="uicontrol">Uso de chamadas do servidor </span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Faça logon em login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Clique em <span class="uicontrol">Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Navegue até <span class="ignoretag"> <span class="uicontrol">Produtos</span> &gt; <span class="uicontrol">Perfil de produto</span> &gt; <span class="uicontrol">Permissões</span> &gt; <span class="uicontrol">Ferramentas do Analytics</span> &gt; <span class="uicontrol">Uso de chamadas do servidor </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

