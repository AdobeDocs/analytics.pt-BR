---
description: 'null'
title: Visão geral do uso de chamadas do servidor
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral do uso de chamadas do servidor

## Por que monitorar e enviar alertas sobre o uso de chamadas do servidor? {#section_060C29BF1D00444B85892AD1FCF55290}

O uso de chamadas do Adobe Analytics Server atende às solicitações de transparência nos dados de uso de chamadas do navegador e do servidor móvel. Permite acessar:

* Um painel de Uso de Chamada de Servidor que rastreia os dados de consumo de chamadas do servidor e os compara ao limite contratual. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics > Components >Alerts]**)

Os principais benefícios do uso da chamada de servidor incluem:

* **Visibilidade** no consumo de chamadas do servidor e nos dados de compromisso, incluindo o consumo móvel em relação ao limite de uso de chamadas do servidor contratuais.
* **Alertas** para notificá-lo sobre o risco ou ocorrência de uma sobreposição e preparar/agir sobre a possibilidade de incorrer em sobreposições.

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. Além disso, os dados não incluíam consumo móvel. Este recurso também substituirá o relatório atual em **[!UICONTROL Billing Information]** > **[!UICONTROL Analytics]** **[!UICONTROL Reports]** .

## Pré-requisitos {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permissões:** para acessar o Painel de Uso de chamadas do servidor e o Criador/Gerenciador de alertas, é necessário ser um Administrador do Adobe Analytics.
* **Permissões:** Os administradores podem conceder acesso a não administradores: a permissão é chamada **[!UICONTROL Server Call Usage]**. Consulte [Permissão de uso de chamadas do servidor](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Terminologia importante {#section_CBA348A039F34563B097CD8890AB358D}

Veja abaixo uma breve introdução sobre a terminologia essencial para o uso da chamada do servidor:

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Termo </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chamada de servidor </p> </td> 
   <td colname="col2"> <p>Uma chamada de servidor, também conhecida como "ocorrência" ou "solicitação de imagem", é uma instância na qual os dados são enviados para os servidores da Adobe para processamento. O tipo mais comum de chamada de servidor é uma visualização de página. Uma exibição de página ocorre onde um visitante visita uma página do site e uma chamada de servidor é gerada para a Adobe, onde as informações são coletadas, processadas e incluídas nas métricas de relatório. </p> <p>Há outros tipos de chamadas de servidor, incluindo links de saída e downloads de arquivos, em que os dados são enviados para a Adobe para processamento, mas não são registrados como uma nova visualização de página. Mesmo visualizações de página "excluídas" (excluídas de seus relatórios por um intervalo de endereços IP configurado por você, por exemplo) são chamadas de servidor porque são recebidas e processadas pela Adobe, mas nunca aparecem em seus relatórios. </p> <p><b>Chamada</b>do servidor primário: Solicitações recebidas diretamente de navegadores de visitantes do site ou da API de inserção de dados. Inclui Ocorrências primárias (Visualizações de página), Eventos personalizados primários, Eventos de download primários e Eventos de saída primários. </p> <p><b>Chamada</b>de servidor secundário: Cópias de chamadas do servidor primário criadas por tags de vários conjuntos ou copiadas/movidas por uma regra VISTA. Se uma chamada de servidor secundário tiver sido movida (não copiada) para um conjunto de relatórios diferente por uma regra VISTA, as chamadas secundárias acumuladas serão deduzidas das chamadas de servidor primário. </p> <p><b>Chamada de servidor primário móvel </b> </p> <p>Solicitações recebidas diretamente de um dos Mobile SDKs. Inclua trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Chamada de servidor secundário móvel</b> </p> <p>Cópias das Chamadas do servidor primárias criadas por marcas de vários conjuntos ou copiadas/movidas por uma regra VISTA. Se uma chamada de servidor secundário tiver sido movida (não copiada) para um conjunto de relatórios diferente por uma regra VISTA, as chamadas secundárias acumuladas serão deduzidas das chamadas de servidor primário. </p> <p>Observação: se sua empresa tiver direitos por contrato a ter somente Chamadas do servidor móveis (Primárias ou Secundárias), seu uso específico da web e de dispositivos móveis contará em relação a seu compromisso específico de dispositivos móveis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de cobrança (ID de cobrança) </p> </td> 
   <td colname="col2"> <p>A entidade legal que é cobrada por chamadas de servidor. Por exemplo, adobe.com. Cada empresa de faturamento tem uma ID de faturamento usada para identificar exclusivamente o cliente de faturamento. Uma ID de faturamento pode estar vinculada a várias Organizações da Experience Cloud; nem sempre há uma relação 1:1 entre uma organização e uma ID de faturamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de login </p> </td> 
   <td colname="col2"> <p>Uma empresa de faturamento pode ter <a href="https://helpx.adobe.com/br/analytics/kb/multiple-login-companies.html">várias empresas de logon </a>. Uma empresa de logon é uma coleção de conjuntos de relatórios usados por sua organização. Algumas organizações têm várias empresas de logon que se aplicam a diferentes partes da organização. Isso é especialmente útil para organizações de grande porte que lidam com diferentes unidades de negócios, nas quais muitos conjuntos de relatórios não se aplicam a outros na empresa. </p> <p>Muitas vezes, são subsidiárias regionais de uma empresa. Este exemplo mostra empresas de logon e seus conjuntos de relatórios associados: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.world: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Observação: dados de uso de chamadas do servidor referentes a <u>todos</u> os conjuntos de relatórios em uma empresa de faturamento ficam visíveis para todos os usuários com as <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">permissões</a> apropriadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organização da Experience Cloud </p> </td> 
   <td colname="col2"> <p>Uma organização é a entidade que permite a um administrador configurar grupos e usuários, além de controlar o logon único na Experience Cloud. A organização funciona como uma empresa de logon que abrange os produtos e as soluções da Experience Cloud. </p> <p>Frequentemente, a organização é o nome da empresa. No entanto, uma empresa pode ter muitas organizações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compromisso de chamada do servidor </p> </td> 
   <td colname="col2"> <p>Quando sua empresa assina um contrato com a Adobe, a equipe de vendas da Adobe se identifica com você, o cliente, os tipos (Primário, Secundário, Primário móvel, Secundário móvel) e o número aproximado de chamadas de servidor que você espera efetuar ao longo do período do contrato. Este é o compromisso total de chamada de servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Período de uso </p> </td> 
   <td colname="col2"> <p>Para fins de monitoramento do uso de chamadas do servidor, esse compromisso total de chamadas do servidor é dividido em períodos de uso menores (como 3 meses) para facilitar comparações ano a ano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Período do Contrato </p> </td> 
   <td colname="col2"> <p>Os períodos de contrato podem ultrapassar vários anos. Digamos que sua empresa tenha um compromisso de chamada de servidor de 6 milhões de chamadas para um contrato de 3 anos. Para fins de monitoramento de uso de chamadas do servidor, esse período de 3 anos pode ser detalhado em períodos de uso menores para facilitar comparações entre anos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Permissão de uso de chamadas do servidor {#section_FCC58EB635954A32990D4E67B52B4369}

A permissão de Uso de chamadas do servidor é concedida automaticamente a Administradores do Analytics. Ele permite que os usuários visualizações o painel e criem alertas de chamada de servidor. Os administradores podem optar por conceder esta permissão a não administradores.

>[!NOTE] Sua empresa pode escolher quais empresas de logon terão acesso ao Uso de chamadas do servidor.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da permissão </th> 
   <th colname="col3" class="entry"> Conceder permissão se você estiver conectado ao Adobe Analytics (logon antigo) </th> 
   <th colname="col4" class="entry"> Conceder permissão se você estiver conectado à Adobe Experience Cloud </th> 
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

