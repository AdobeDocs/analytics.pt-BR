---
description: 'null'
keywords: grupos; permissões
seo-description: 'null'
seo-title: Mudanças de permissão do usuário e grupo
solution: Analytics
subtopic: Usuários e grupos
title: Mudanças de permissão do usuário e grupo
topic: Ferramentas administrativas
uuid: 94 f 2727 b -17 e 4-4003-a 222-35 c 821 d 6959 e
translation-type: tm+mt
source-git-commit: 0837416ae67936fbf81af2b7051a7ed9f522f5b5

---


# Mudanças de permissão do usuário e grupo

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). A Adobe enviará uma notificação quando for a sua vez de migrar os usuários. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

## O que mudou? {#section_2C205DE94155441B9E9D3E4C46CCF2EE}

**[!UICONTROL Administração]** &gt; **[!UICONTROL Gerenciamento de usuários]** &gt; **[!UICONTROL Grupos]**

>[!NOTE]
>
>Devido ao alto número de combinações de permissão possíveis disponíveis, não podemos fornecer documentação descrevendo todos os métodos de API que podem ser usados em todas as combinações de permissões. Normalmente, não administradores que permitiram acesso de serviços da Web terão apenas acesso de Leitura aos métodos de API. Eles não terão acesso de Gravação aos métodos.

Porque a API e a interface usam o mesmo sistema de permissão, quaisquer permissões garantidas por um administrador a um não administrador específico na interface (Adobe Admin Console) serão as mesmas permissões que o usuário possui na API.

<table id="table_D1DB0DE37752450BBCCA44DB760BB505"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aprimoramento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p id="reportaccess">Mudanças no <span class="uicontrol">Acesso ao Relatório</span> (Personalizar grupos) </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Adicionar novo grupo</span> &gt; <span class="uicontrol">Acesso ao Relatório</span> </p> <p>A seção <span class="wintitle">Acesso ao Relatório</span> da página <span class="wintitle">Definir grupo de usuários</span> foi redimensionada para quatro categorias, permitindo redimensionar permissões detalhadamente. </p> <p><img  src="assets/report-access.png" id="image_CB83E5C7DB4343619421A1FAA61478D0"> </img> </p> <p>Os itens que antes estavam em </p> 
    <ul id="ul_16D5EF18D57D4608AEEDEC40D90D8828"> 
     <li id="li_F29E84C6228A464C8807F09205AEAAC6"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Ferramentas do Analytics</a>: ative as permissões do usuário para obter integração a itens Gerais (faturamento, logs etc.), Gerenciamento da empresa, Ferramentas, Acesso a serviços da Web, Report Builder e Data Connectors. </p> <p> <b>Observação:</b> as configurações da empresa feitas na categoria Personalizar o Admin Console foram movidas para as Ferramentas do Analytics. </p> </li> 
     <li id="li_A6EB788162A2455E94CE54B9279A854D"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-report-suite-tools.md#concept_C94E9864349B428AB9CCE0CA4B0A40FF" format="dita" scope="local"> Ferramentas do Conjunto de relatórios</a>: ative permissões do usuário para Serviços da Web, Gerenciamento de conjuntos de relatórios, Ferramentas e relatórios, além de Itens do painel. </p> </li> 
     <li id="li_EDB0255E009B4F1CAFAF53966B41363C"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-metrics.md#concept_05D54436430E4320A48C7C685D337FBE" format="dita" scope="local"> Métricas</a>: ative permissões para eventos de tráfego, conversão, personalizados, de soluções e sensíveis a conteúdo, entre outros. </p> </li> 
     <li id="li_8DAE87D1DEF54803A9C6FE31C01F0FB0"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Dimensões</a>: personalize detalhadamente o acesso dos usuários, inclusive a eVars e relatórios de tráfego, de soluções e de definição de caminho. </p> </li> 
    </ul> <p>Por exemplo, você pode criar um grupo com acesso a várias ferramentas do Analytics, (<span class="wintitle">Analysis Workspace</span>, <span class="wintitle">Reports &amp; Analytics</span> e <span class="wintitle">Report Builder</span>), com permissão para métricas e dimensões específicas (inclusive eVars), e também para recursos como criação de segmentos ou métricas calculadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mudanças nos grupos predefinidos </p> </td> 
   <td colname="col2"> <p> <b>Acesso de administradores:</b> os grupos predefinidos não são mais exigidos para os administradores. Agora, os administradores têm acesso a todos os itens (ferramentas, métricas e dimensões), e também aos Serviços da Web, ao Report Builder, Activity Map e Ad Hoc Analysis. </p> <p>A finalidade dos grupos é conceder ou restringir o acesso a usuários não administrativos. </p> <p> <b>Grupos personalizados:</b> os grupos personalizados substituíram os predefinidos. Os grupos predefinidos atuais serão migrados para grupos personalizados, usando o mesmo nome. Todos os grupos personalizados criados por você serão preservados, inclusive com suas configurações. No entanto, você observará que a localização das configurações mudou. Por exemplo, as Configurações da empresa (em Personalizar Admin Console) agora estão em <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Personalizar ferramentas do Analytics</a>. </p> <p> Users belonging to <span class="term"> All Report Access</span> have been migrated to a custom group with access to: </p> 
    <ul id="ul_696A9243F5FD4AF187352C2F4B1CFDC2"> 
     <li id="li_683A0A3BB7214CFFBC61D5A4CD237F48">Todas as dimensões </li> 
     <li id="li_D8FDBF6A32224731AB706315DEA0A03E">Todas as métricas </li> 
     <li id="li_65ABE5C95D43444D88E63EE95C9AED05">Todos os Conjuntos de relatórios </li> 
     <li id="li_7ED1505590144B38B3B9851BAA6BBB49">Permissão para relatórios de canal </li> 
     <li id="li_F718FE1FCF9A4B05AB933CA3F105F3EC">Permissão para relatórios de detecção de anomalias </li> 
     <li id="li_527BD52007E846FE8B5F71AB3C12F695">Permissão para relatórios em tempo real </li> 
     <li id="li_AFFB58C7FB644AC8A85E2D76BA7D51F5">Permissão de acesso à Analysis Workspace </li> 
    </ul> <p>Os administradores podem excluir grupos personalizados e criar os seus próprios, pois todas as configurações antes disponíveis nos grupos predefinidos continuam aceitando personalização nas configurações de <span class="wintitle">Acesso ao relatório</span> em <a href="../c-user-groups/groups.md" format="dita" scope="local">Definir grupos de usuários</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permissões no nível de dimensões </p> </td> 
   <td colname="col2"> <p>Personalize permissões para que incluam ou excluam o acesso a dimensões (além das métricas). </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>Todas as dimensões e métricas atuais dos grupos personalizados foram automaticamente migradas para as novas categorias. Se um grupo tiver métricas ativadas, receberá por padrão todas as novas dimensões (eVars e com sensível a conteúdo) e métricas permissíveis. </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> Permissões do Importador de classificações (antigo SAINT): o acesso a classificações é determinado pelo acesso à <a href="https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html" format="html" scope="external">variável</a> em que se baseia a classificação. </li> 
    </ul> <p>See <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Customize Dimension Permissions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console </p> </td> 
   <td colname="col2"> <p>Recomendado somente para clientes novos ou com empresas <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html" format="html" scope="external">provisionadas na Experience Cloud</a>. Há planos para a migração dos atuais clientes do <span class="keyword">Analytics</span> para o sistema de gerenciamento de identidade da <span class="keyword">Experience Cloud</span>. </p> <p>More information is available in <a href="https://helpx.adobe.com/enterprise/using/manage-permissions-and-roles.html" format="html" scope="external"> Manage product permissions in the Admin Console</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Perguntas frequentes sobre mudanças nas permissões {#section_02809EFC95054B40A089E6C6E4FACA13}

Aqui estão informações novas e importantes sobre atualizações novas e planejadas, e também sobre o efeito que terão no seu ambiente administrativo.

<table id="table_1E93F45C66E841E6882FB602509F30A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1">Que mudanças de permissões ocorreram na versão lançada em <b>julho de 2016</b>? </td> 
   <td colname="col2"> <p> <b>Acesso integral ao Conjunto de relatórios</b> </p> <p>Ao adicionar conjuntos de relatórios para inclusão em um grupo, é possível especificar <span class="uicontrol">Acesso a todo o conjunto de relatórios</span>. Esta definição aplica as permissões do grupo a todos os conjuntos de relatórios atuais e futuros. </p> <p>Para ativar este recurso, vá até <span class="uicontrol">Gerenciamento de usuários</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Adicionar novo grupo de usuários</span> e selecione <span class="uicontrol">Acesso a todo o conjunto de relatórios</span>. </p> <p><img placement="break"  src="assets/all-report-suites.png" width="300px" id="image_9E814D412E87484C940F1100D6DE2B0F" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo usar o Admin Console para gerenciar usuários ou o Gerenciamento de usuários existente do Analytics? </p> </td> 
   <td colname="col2"> <p>As alterações feitas em Analytics &gt; Administrador &gt; Gerenciamento de usuários não são refletidas no Admin Console. Portanto, somente os novos clientes que já usam o Admin Console para gerenciamento de usuários e grupos devem continuar a fazê-lo. Está planejada uma migração do gerenciamento de grupos existente do Analytics para o Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que mudanças de Permissões foram feitas na versão de <b>outubro de 2016</b>? </p> </td> 
   <td colname="col2"> <p>Estarão disponíveis os seguintes aprimoramentos da atual interface de <span class="wintitle">Ferramentas administrativas</span>: </p> <p> 
     <ul id="ul_2A31E8DC17A94B7FABDBA9C87C3947EF"> 
      <li id="li_AE2ECCA01CC64D30B109BE74379EE474">Permission changes as described in <a href="../../../admin/user-management2/c-user-management/permissions-changes.md#concept_86581595B86B47D5B8F90282FC3E31EF" format="dita" scope="local"> Administrative Changes - Fall 2016</a>. </li> 
      <li id="li_33CB2B6A2E5F45BE97CC5E0983AF280E">Foram removidos relatórios de tráfego extintos que não apareciam mais no menu. </li> 
      <li id="li_57234CF27E1D405987DE89312CD62C52">Permissões de classificações: O acesso às classificações será determinado pelo acesso à variável para a qual a classificação é. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Há algo que eu precise fazer para migrar usuários? </p> </td> 
   <td colname="col2"> <p>Não; todas as migrações de permissões serão transparentes. </p> <p> 
     <ul id="ul_654F85286EC04416B3E0BA725EBE10AD"> 
      <li id="li_8050B8941F794103B82A0ADF0930D216">Todos os atuais relatórios de tráfego de um Grupo personalizado serão migrados automaticamente para a nova Categoria de dimensão. </li> 
      <li id="li_B97079DB29A346B98D066F11AB7F94AF">Se um Grupo personalizado tiver alguma métrica já ativada, receberá automaticamente todas as novas devidas dimensões (variáveis eVars e de Solução). </li> 
      <li id="li_F1219EF490DA473BA15F2B215F2995AE"> Um grupo personalizado com pelo menos uma métrica receberá automaticamente acesso a todas as dimensões de eVars e outras sensíveis a conteúdo, <b>exceto</b> as recém-disponíveis dimensões de tráfego (antes, relatórios de tráfego). </li> 
      <li id="li_F494CE6144A04A6199CFBBA1D7BEA32B">Todos os grupos predefinidos mudarão para uma permissão. Estas novas permissões serão adicionadas a uma nova categoria de <span class="uicontrol">Ferramentas do Analytics</span>. </li> 
      <li id="li_2FCD9254FC3C4FD7871EEF9453E5CE1E">Todos os Grupos personalizados, com qualquer métrica, terão todos os eventos de Soluções do Analytics adicionados como novas métricas. </li> 
      <li id="li_34C4560769B64F28A4E83BAE71065DCC">Todos os usuários que antes estavam em Todo acesso a relatório serão adicionados ao novo grupo personalizado. A opção Todo acesso a relatório deixará de existir. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que não mudará? </p> </td> 
   <td colname="col2"> <p>Os Atributos de visitante continuarão sem permissões. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Referência rápida de permissões {#section_A3FDD8259F524B21A5489833533D1B28}

A tabela a seguir lista tarefas e onde elas podem ocorrer (dependendo do status da empresa).

>[!NOTE]
>
>A *`migrated user`* and *`Experience Cloud user`* refer to users who have accepted an email invitation to join the Experience Cloud. Se o convite por email não for aceito, os usuários ainda serão usuários do Analytics e não poderão ser gerenciados no Admin Console. (A única exceção é o caso de a migração estar usando [Enterprise IDs ou Federated IDs](https://helpx.adobe.com/enterprise/using/set-up-identity.html). Nesse caso, o usuário será migrado quando o administrador migrar os usuários individualmente.)

<table id="table_B68FD00FC5D24823A86BB69558C0327C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col2" class="entry"> Empresa de logon sem migração </th> 
   <th colname="col3" class="entry"> Empresa de logon em migração no momento </th> 
   <th colname="col4" class="entry"> Empresa de logon com migração concluída </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Criar um usuário </td> 
   <td colname="col2"> <p>Admin Console (creating a user and adding him or her to an Analytics <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> product configuration</a> also creates the user account in Analytics). </p> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Ferramentas administrativas</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external">Console de administração</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external">Console de administração</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Editar um usuário </td> 
   <td colname="col2"> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Ferramentas administrativas</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external">Console de administração</a> </p> <p> Ferramentas administrativas - A edição de usuários migrados nas Ferramentas administrativas limita-se ao gerenciamento de chaves de API e à exclusão / transferência de ativos. </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external">Console de administração</a> </p> <p> Ferramentas administrativas - A edição limita-se ao gerenciamento de chaves de API e à exclusão / transferência de ativos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excluir um usuário </td> 
   <td colname="col2"> <p>Console de administração - Para usuários da Experience Cloud </p> <p>Ferramentas administrativas - Para todos os usuários, mas para os usuários da Experience Cloud, exclui somente o usuário do Analytics mapeado, não a conta da Experience Cloud. </p> </td> 
   <td colname="col3"> <p>Console de administração - Para usuários migrados. </p> <p>Ferramentas administrativas - Para usuários exclusivos ao Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> <p> Ferramentas administrativas - Após excluir um usuário da Experience Cloud ou desvincular sua conta no Admin Console, você pode excluir o logon do Analytics das Ferramentas administrativas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Logon no Analytics </td> 
   <td colname="col2"> <p> <b>Experience Cloud: </b> <span class="filepath"> marketing.adobe.com</span>. Disponível apenas para usuários da Experience Cloud. </p> <p> <b>Analytics (herdado):</b> <span class="filepath">sc.omniture.com</span>. Apenas para usuários do Analytics e para usuários da Experience Cloud com credenciais do Analytics </p> </td> 
   <td colname="col3"> <p> <span class="filepath">marketing.adobe.com</span> - Disponível apenas para usuários da Experience Cloud. </p> <p> <span class="filepath"> sc.omniture.com</span> - Apenas para usuários do Analytics e para usuários da Experience Cloud com credenciais do Analytics. </p> <p>Durante a migração, os administradores podem desativar o recurso de logon em <span class="filepath">omniture.com</span> para usuários específicos. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Criar um grupo </td> 
   <td colname="col2"> <p>Console de administração - quando um grupo é criado no Admin Console, um grupo mapeado no Analytics será exibido nas Ferramentas administrativas, mas esse grupo mapeado não pode ter seu nome alterado das Ferramentas administrativas nem ser excluído das Ferramentas administrativas. </p> <p>Ferramentas administrativas. </p> </td> 
   <td colname="col3"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
   <td colname="col4"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Editar usuários em um grupo </td> 
   <td colname="col2"> <p>Console de administração - Somente para usuários da Experience Cloud </p> <p>Ferramentas administrativas - É possível editar a associação a grupos de usuários da Experience Cloud e os usuários exclusivos do Analytics nas Ferramentas administrativas. No entanto, se um usuário da Experience Cloud fizer parte de um grupo no Console de administração, ele não poderá ser removido do grupo nas Ferramentas administrativas. </p> </td> 
   <td colname="col3"> <p>Admin Console - somente usuários da Experience Cloud </p> <p> Ferramentas administrativas - Logons exclusivos ao Analytics ainda podem ser adicionados/removidos dos grupos com as Ferramentas administrativas. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Editar permissões para um grupo </td> 
   <td colname="col2"> <p>Admin Console - você pode editar grupos criados no Console de administração. </p> <p>Ferramentas administrativas - É possível editar permissões para qualquer grupo. </p> </td> 
   <td colname="col3"> <p>Console de administração </p> </td> 
   <td colname="col4"> <p>Console de administração </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excluir grupo </td> 
   <td colname="col2"> <p>Console de administração - você pode excluir apenas grupos criados no Admin Console. </p> <p>Ferramentas administrativas - Só é possível excluir grupos criados nas Ferramentas administrativas. </p> </td> 
   <td colname="col3"> <p>Console de administração </p> </td> 
   <td colname="col4"> <p>Console de administração </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mudar o status administrativo do usuário </td> 
   <td colname="col2"> <p>Admin Console - somente para usuários da Experience Cloud. </p> <p>Ferramentas administrativas </p> </td> 
   <td colname="col3"> <p>Admin Console - somente para usuários da Experience Cloud. </p> <p>Ferramentas administrativas - Para usuários exclusivos ao Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
 </tbody> 
</table>
