---
description: Visão geral da funcionalidade de uso de chamada de servidor do Adobe Analytics.
title: Visão geral do uso de chamadas do servidor
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
role: Admin
TQID: https://experienceleague.adobe.com/-IIz9r-K-flZq85Dz3lhYuo9-Ko0zt0KoJJ7DtI5Mz4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1013
ht-degree: 32%

---

# Uso de chamadas do servidor

O uso de chamadas de servidor do Adobe Analytics atende às suas solicitações de transparência nos dados de uso de chamadas do navegador e do servidor móvel. Ele permite acessar:

* Um painel de uso de chamadas do servidor que rastreia os dados de consumo de chamadas do servidor e os compara ao limite contratual. (No Adobe Analytics, selecione > [!UICONTROL **Admin**] > [!UICONTROL **Uso de chamadas do servidor**])
* Um tipo de alerta de uso de chamada de servidor no construtor de alertas que permite configurar alertas para evitar sobreposições (no Adobe Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Alertas**])

Os principais benefícios do uso de chamadas do servidor incluem:

* **Visibilidade** do consumo de chamadas do servidor e dos dados de compromisso, incluindo o consumo de dispositivos móveis em relação ao limite de uso de chamadas do servidor contratuais.
* **Alertas** para notificá-lo sobre o risco ou a ocorrência de um excedente e preparar/agir sobre a possibilidade de excedentes efetivos.

## Pré-requisitos {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permissões:** Para acessar o painel de uso de chamadas do servidor e o criador de alertas ou gerenciador de alertas, é necessário ser um Administrador do Adobe Analytics.
* **Permissões:** administradores podem conceder acesso a não administradores: a permissão chama-se **[!UICONTROL Uso de chamadas do servidor]**. Consulte [Permissão de uso de chamadas do servidor](#server-call-usage-permission).

## Terminologia importante {#terminology}

Os termos a seguir são importantes para entender o uso de chamadas do servidor:

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
   <td colname="col2"> <p>Uma chamada de servidor, também conhecida como “ocorrência” ou uma “solicitação de imagem”, é uma instância na qual os dados são enviados para os servidores da Adobe para processamento. O tipo mais comum de chamada de servidor é uma exibição de página. Uma exibição de página ocorre onde um visitante visita uma página do site e uma chamada de servidor é gerada para a Adobe, onde as informações são coletadas, processadas e incluídas nas métricas de relatório. </p> <p>Há outros tipos de chamadas de servidor, incluindo links de saída e downloads de arquivo, em que os dados são enviados ao Adobe para processamento, mas não são registrados como uma nova exibição de página. Até mesmo as exibições de página "excluídas" (excluídas de seus relatórios por um intervalo de endereços IP configurado por você, por exemplo) são chamadas de servidor porque são recebidas e processadas pelo Adobe, mas nunca são exibidas em seus relatórios. </p> <p><b>Chamada do servidor primário</b>: solicitações recebidas diretamente dos navegadores de visitantes do site ou da API de inserção de dados. Inclui ocorrências principais (Exibições de página), eventos personalizados principais, eventos de download principais e eventos de saída principais. </p> <p><b>Chamada de Servidor Secundário</b>: cópias de chamadas de servidor primárias criadas por marcas de vários conjuntos ou copiadas/movidas por uma regra VISTA. Se uma chamada de servidor secundária tiver sido movida (não copiada) para um conjunto de relatórios diferente por uma regra VISTA, as chamadas secundárias acumuladas são subtraídas das chamadas de servidor primárias. </p> <p><b>Chamada de Servidor Primário Móvel </b> </p> <p>Solicitações recebidas diretamente de um dos Mobile SDKs. Inclua trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Chamada de Servidor Secundário Móvel</b> </p> <p>Cópias das Chamadas do servidor primárias criadas por marcas de vários conjuntos ou copiadas/movidas por uma regra VISTA. Se uma chamada de servidor secundária tiver sido movida (não copiada) para um conjunto de relatórios diferente por uma regra VISTA, as chamadas secundárias acumuladas são subtraídas das chamadas de servidor primárias. </p> <p>Observação: se sua empresa tiver direitos por contrato a ter somente Chamadas do servidor móveis (Primárias ou Secundárias), seu uso específico da web e de dispositivos móveis contará em relação a seu compromisso específico de dispositivos móveis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de faturamento (ID de faturamento) </p> </td> 
   <td colname="col2"> <p>A entidade legal que é cobrada por chamadas do servidor. Por exemplo, adobe.com. Cada empresa de faturamento tem uma ID de faturamento usada para identificar de maneira exclusiva o cliente de faturamento. Uma ID de cobrança pode estar vinculada a várias organizações CX Enterprise; nem sempre há uma relação 1:1 entre uma organização e uma ID de cobrança. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de logon </p> </td> 
   <td colname="col2"> <p>Uma empresa de faturamento pode ter <a href="https://helpx.adobe.com/br/analytics/kb/multiple-login-companies.html">várias empresas de logon </a>. Uma empresa de logon é uma coleção de conjuntos de relatórios usada por sua organização. Algumas organizações têm várias empresas de logon que se aplicam a diferentes partes da organização. Isso é útil principalmente para grandes organizações que lidam com diferentes unidades de negócios, nas quais muitos conjuntos de relatórios não se aplicam a outras na empresa. </p> <p>Muitas vezes, essas são as subsidiárias regionais de uma empresa. O exemplo a seguir apresenta empresas de logon e seus respectivos conjuntos de relatórios associados: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.world: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Observação: dados de uso de chamadas do servidor referentes a <u>todos</u> os conjuntos de relatórios em uma empresa de faturamento ficam visíveis para todos os usuários com as <a href="/help/admin/tools/server-call-usage/overage-overview.md">permissões</a> apropriadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organização corporativa CX </p> </td> 
   <td colname="col2"> <p>Uma organização é a entidade que permite a um administrador configurar grupos e usuários, além de controlar o logon único no CX Enterprise. A organização funciona como uma empresa de login que abrange todos os produtos e soluções da CX Enterprise. </p> <p>Frequentemente, a organização é o nome da empresa. No entanto, uma empresa pode ter muitas organizações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compromisso de chamadas do servidor </p> </td> 
   <td colname="col2"> <p>Quando sua empresa assina um contrato com a Adobe, a equipe de vendas da Adobe identifica com você, o cliente, os tipos (Principal, Secundário, Principal Móvel, Secundário Móvel) e o número aproximado de chamadas de servidor que você espera realizar durante o período do contrato. Este é o seu compromisso total de chamadas do servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Período de uso </p> </td> 
   <td colname="col2"> <p>Para fins de monitoramento do uso de chamadas do servidor, esse compromisso total de chamadas do servidor é dividido em períodos de uso menores (como 3 meses) para facilitar comparações entre anos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Período do Contrato </p> </td> 
   <td colname="col2"> <p>Os períodos de contrato podem se estender por vários anos. Digamos que sua empresa tenha um compromisso de chamada de servidor de 6 milhões de chamadas para um contrato de 3 anos. Para fins de monitoramento de uso de chamadas do servidor, esse período de 3 anos pode ser detalhado em períodos de uso menores para facilitar comparações entre anos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Permissão de uso de chamadas do servidor {#permission}

A permissão de uso de chamadas do servidor é concedida automaticamente a administradores do Analytics. Ele permite que os usuários visualizem o painel e criem alertas de chamadas do servidor. Administradores podem optar por conceder essa permissão a não administradores.

>[!NOTE]
>
>Sua empresa pode escolher quais empresas de logon terão acesso ao Uso de chamadas do servidor.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da permissão </th> 
   <th colname="col3" class="entry"> Conceder permissão se você estiver conectado ao Adobe Analytics (logon herdado) </th> 
   <th colname="col4" class="entry"> Conceder permissão se você estiver conectado ao Adobe CX Enterprise </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uso de chamadas do servidor </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Faça logon no Analytics via sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Navegue até <span class="ignoretag"> <span class="uicontrol"> Administrador </span> &gt; <span class="uicontrol"> Todos os administradores </span> &gt; <span class="uicontrol"> Gerenciamento de usuários </span> &gt; <span class="uicontrol"> Grupos </span> &gt; <span class="uicontrol"> Editar Acesso a Todos os Relatórios </span> &gt; <span class="uicontrol"> Ferramentas do Analytics </span> &gt; <span class="uicontrol"> Personalizar </span> &gt; <span class="uicontrol"> Uso de chamadas do servidor </span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Faça logon em login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Clique em <span class="uicontrol">Analytics</span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Navegue até <span class="ignoretag"> <span class="uicontrol"> Produtos </span> &gt; <span class="uicontrol"> Perfil de Produto </span> &gt; <span class="uicontrol"> Permissões </span> &gt; <span class="uicontrol"> Ferramentas do Analytics </span> &gt; <span class="uicontrol"> Uso de chamadas de servidor </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
