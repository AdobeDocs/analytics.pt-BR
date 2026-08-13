---
description: O que você precisa saber sobre a migração de IDs de usuários do Analytics para o Admin Console no Adobe CX Enterprise.
title: Migração de usuários do Analytics para o Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
role: Admin
TQID: https://experienceleague.adobe.com/bCf6DWIpIVALcGPAi3tL8zlZ5V8lzPR-9XNCm4HuFnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
  - id: e499b847-6dc4-408a-9f0b-70d35ce9b711
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 2960
ht-degree: 52%

---

# Migração de usuários para o Adobe Admin Console{#analytics-user-migration-to-the-admin-console}

O que você precisa saber sobre a migração de IDs de usuários do Analytics para o Adobe Admin Console no Adobe CX Enterprise.

Para obter ajuda geral sobre os tópicos do Adobe Admin Console (não relacionados à migração do Analytics), consulte o [Guia do usuário do Admin Console](https://helpx.adobe.com/br/enterprise/administering/user-guide.html).

Depois de migrar, você pode [gerenciar usuários e produtos do CX Enterprise](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR) na Adobe Admin Console.

## O que é a migração de IDs de usuários do Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

A migração de ID de usuário do Analytics permite que os administradores migrem facilmente as contas de usuários do gerenciamento de usuários do Analytics para o Adobe Admin Console. Depois que os usuários forem migrados, eles terão acesso às soluções e aos serviços principais disponíveis no CX Enterprise. A migração está sendo realizada em fases para os clientes.

Os benefícios de usar o Adobe Admin Console incluem:

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Benefícios </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Logon único </p> </td> 
   <td colname="col2"> <p>Os usuários do Analytics podem fazer logon no CX Enterprise e em todas as soluções usando a Adobe ID ou a Enterprise ID. Esse logon permite o acesso a soluções integradas e serviços principais no CX Enterprise. </p> <p>Após a migração, os usuários que tentarem fazer logon por meio de logons antigos (<span class="filepath">my.omniture.com</span> e <span class="filepath">sc.omniture.com</span>) serão redirecionados para <span class="filepath">experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerenciar a identidade do usuário e as permissões </p> </td> 
   <td colname="col2"> <p>Os administradores do Analytics podem gerenciar usuários e permissões exclusivamente no <a href="https://adminconsole.adobe.com/enterprise/">Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerenciar produtos e serviços principais </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Convidar novos usuários </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Criar perfis de produto </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Conceder aos usuários permissão para produtos e serviços específicos </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Obter acesso a <a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=pt-BR"> serviços essenciais entre soluções</a> disponíveis no Adobe CX Enterprise </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## O que saber (e fazer) antes de migrar IDs de usuário (Perguntas frequentes) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Respostas às perguntas que você pode ter antes da migração.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta/Tarefa </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sou um administrador do Analytics e recebi um email de pré-migração. O que eu faço primeiro? </p> </td> 
   <td colname="col2"> <p>Verifique se você tem um Adobe ID e pode acessar o <a href="https://adminconsole.adobe.com/enterprise/"> CX Enterprise Admin Console</a>. </p> <p>Caso contrário, entre em contato com o <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Atendimento ao cliente da Adobe</a>. (Primeiro, você deve entrar em contato com o administrador do sistema ou do produto que poderá convidá-lo para a organização adequada). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrações do AEM com o Analytics </p> </td> 
   <td colname="col2"> <p> Os usuários do AEM com uma integração ao Analytics precisarão alterar a configuração para usar o segredo compartilhado do Analytics em vez da senha. </p> <p> Você deve fazer isso antes de habilitar a migração. Quando a migração estiver desativada, a senha configurada originalmente não será mais válida. </p> <p><b>Para obter o segredo compartilhado no Analytics</b> </p> <p> O segredo compartilhado pode ser obtido em Analytics (<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Gerenciamento de usuário</span>) e é diferente para cada usuário. </p> <p><b>Para atualizar a configuração AEM com o segredo compartilhado</b> </p> <p>Consulte <a href="https://helpx.adobe.com/br/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">Conectar ao Adobe Analytics e Criar Frameworks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atualizar o Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: atualize sua instalação do <a href="/help/analyze/report-builder/report-builder-setup.md">Report Builder</a> para a versão mais recente. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quando a migração começa? </p> </td> 
   <td colname="col2"> <p>A Adobe notificará os administradores do Analytics por email com instruções sobre quando a migração começará. </p> <p>As migrações para o Adobe Admin Console ocorrerão em levas. No dia da migração, a Adobe notifica os administradores do Analytics e concede a eles acesso à ferramenta de migração. Depois que uma empresa de logon atender aos critérios definidos para cada onda de migração, a Adobe: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Defina as datas de início e término para a migração da empresa. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Envie uma notificação por email aos atuais administradores do Analytics da empresa, aproximadamente 30 dias antes da migração. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Exiba uma notificação no produto informando os administradores da data de início da migração. </li> 
    </ul> <p> No dia da migração, os antigos grupos de permissão serão copiados automaticamente para o Adobe Admin Console. Não será mais possível convidar novos usuários ou criar novos grupos nas Ferramentas administrativas do Analytics. </p> <p>Após a migração: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Os administradores usarão o Adobe Admin Console para gerenciar os usuários e as permissões do Analytics. (Não será mais possível usar a interface de gerenciamento de usuários em Analytics &gt; Admin &gt; Gerenciamento de usuários.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Os usuários acessarão o Analytics usando a Adobe ou Enterprise ID por meio da CX Enterprise em vez de <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que acontecerá na data de início da migração? </p> </td> 
   <td colname="col2"> <p>Às 10h UTC da data de início da migração: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Seus grupos de permissão existentes no Analytics serão replicados automaticamente no Adobe Admin Console como Perfis de produtos, incluindo suas descrições e permissões granulares em conjuntos de relatórios, métricas, dimensões, Analytics e ferramentas do conjunto de relatórios. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Se um usuário atual do Analytics tiver sido criado no Adobe Admin Console (o que significará que tem uma Adobe/Enterprise ID vinculada), ele será adicionado ao Perfil de produto apropriado no Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">A seção Gerenciamento de usuários na guia Administrador do Analytics será definida como <span class="term"> somente leitura</span>. Não será mais possível criar novos usuários ou grupos de permissão aqui; essas funções deverão ser realizadas no Adobe Admin Console. Consulte <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Recursos do Analytics não compatíveis com o Adobe Admin Console</a> para obter mais informações. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">Como administrador, você terá acesso à ferramenta <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">Migração de ID do usuário</a>. Além disso, é exibida uma notificação no produto que inclui a data final da migração (em geral, após 60 dias), além de links para conteúdo de ajuda e Perguntas frequentes. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Você terá acesso à guia Permissões no Adobe Admin Console, que permite criar Perfis de produtos com todas as opções granulares com as quais você está familiarizado no Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Como migrar IDs de usuário? </p> </td> 
   <td colname="col2"> <p> Clique em <a href="/help/admin/tools/user-management/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrar IDs de Usuários</a> na página Admin, em Gerenciamento de Usuários. Use a ferramenta para adicionar usuário aos perfis de produto no Adobe Admin Console (replicado dos grupos de permissão no Analytics). Você pode migrar IDs de usuário em seu próprio ritmo. </p> <p>Privilégios de administração são necessários. Quando a migração estiver concluída, ela não poderá ser revertida. </p> <p>Na data final da migração, o acesso a <span class="filepath">my.omniture.com</span> será desativado para os usuários em suas empresas de logon. Os usuários (incluindo aqueles que ainda não foram migrados) serão redirecionados para fazer logon por meio da nova URL corporativa do CX (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>Nota: a Adobe recomenda aproveitar a oportunidade para realizar uma auditoria de seus usuários e grupos antes da migração. Exclua contas antigas e não utilizadas ou contas que não devem mais ter acesso ao produto (por exemplo, funcionários que não estão mais na organização). </p> <p>Tópico relacionado: <a href="/help/admin/tools/user-management/user-migration/migrate-enterprise.md"> Migrar contas de usuário do Analytics para Enterprise e Federated IDs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A migração afetará minha implementação do Analytics ou como os dados são coletados? </p> </td> 
   <td colname="col2"> <p>Não. </p> <p>A ferramenta de migração existe para ajudá-lo a migrar IDs de usuários e permissões do Gerenciamento de usuários do Analytics para o <a href="https://adminconsole.adobe.com/enterprise/"> CX Enterprise Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quanto tempo leva o processo de migração? </p> </td> 
   <td colname="col2"> <p>Todos os administradores atuais do Analytics receberão um email de notificação de pré-migração quatro semanas antes da migração. (A data de início real aparecerá na interface do Analytics.) </p> <p>Quando a migração começar, os administradores terão 60 dias para concluir o processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso acelerar minha migração? </p> </td> 
   <td colname="col2"> <p>Sim. No entanto, a Adobe recomenda que você use o tempo antes de a migração começar a: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Verificar se você é um administrador de produto do Analytics no Adobe Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunique à sua base de usuários que a experiência de logon deles será alterada quando a migração começar. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Auditoria de usuários e permissões atuais e execução de atividades de limpeza. </li> 
    </ul> <p>Para acelerar sua migração, entre em contato com a equipe de conta da Adobe pelo <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html"> Atendimento ao cliente da Adobe</a> e envie um pedido para antecipar a data de início da migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sou um administrador do Analytics e não tenho acesso ao Adobe Admin Console. Quem pode me ajudar a obter acesso ao Adobe Admin Console? </p> </td> 
   <td colname="col2"> <p>Qualquer administrador de sistema ou de produto que tenha acesso ao Adobe Admin Console na sua organização pode conceder acesso a você. Se você não tem certeza de quem dentro da organização possui privilégios de administrador no Console, entre em contato com o <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Atendimento ao cliente da Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso adiar a data inicial da migração? </p> </td> 
   <td colname="col2"> <p>Sim. Entre em contato com o <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Atendimento ao cliente da Adobe</a>. </p><p>Consulte abaixo uma descrição das alterações feitas no gerenciamento de usuários e permissões atual do Analytics na data inicial. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agora que minha empresa está migrando para o Adobe Admin Console, onde posso criar novos usuários e grupos de permissão antes da data inicial da migração? </p> </td> 
   <td colname="col2"> <p>Antes da data inicial da migração, você poderá criar usuários no Adobe Admin Console ou em Analytics &gt; Gerenciamento de usuários. </p> <p>Após a migração, você poderá criar usuários e grupos de permissões somente no Adobe Admin Console. </p><p>consulte a seção Migração abaixo para obter mais detalhes sobre o que acontece na data inicial da migração. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Quando posso implementar o logon único usando Federated IDs? </p> </td> 
   <td colname="col2"> <p> Uma ferramenta estará disponível em breve no Adobe Admin Console que permitirá alterar os tipos de ID de Adobe ID para Federated ID. Durante a migração, não é possível migrar usuários como Federated IDs. </p> </td> 
  </tr> 
 </tbody> 
</table>

## O que você deve saber durante a migração (Perguntas frequentes) {#section-d394524aa6d046d79025bbd7499792bc}

Informações importantes sobre o processo de migração e como ele afeta o gerenciamento de usuários atual.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Como os grupos de permissão são replicados no Adobe Admin Console? E o que acontece com meus usuários? </p> </td> 
   <td colname="col2"> <p>Um grupo migrado do Analytics é chamado de <i>Perfil de produto</i> no Adobe Admin Console. As configurações de permissão para o grupo original são mantidas na migração. No entanto, os usuários atribuídos ao grupo não são migrados. Quando um usuário pertencente a esse grupo é migrado usando a ferramenta de migração, esse usuário é atribuído a esse perfil de produto. </p> <p>Por exemplo, um grupo de permissão de Operações da Costa Oeste que concedeu a seus membros o direito ao Report Builder e ao Analysis Workspace (com determinados conjuntos de relatórios, métricas, dimensões) se tornará um perfil de produto de Operações da Costa Oeste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso delegar o esforço de migração a outro administrador? </p> </td> 
   <td colname="col2"> <p>Depois que a migração começar, qualquer administrador que acesse a instância do Analytics por meio do CX Enterprise poderá usar a ferramenta de migração para iniciar (ou continuar) a migração de usuários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso atualizar a associação do grupo de permissões para usuários não migrados? </p> </td> 
   <td colname="col2"> <p>Sim. É possível alterar a associação de grupo de usuários não migrados na seção Gerenciamento de usuários do Analytics. </p><p>Aguardando esclarecimentos de Ashok sobre o que é feito. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso criar usuários e grupos de permissões no Analytics após o início da migração e, em seguida, usar a ferramenta de migração para movê-los para o Adobe Admin Console? </p> </td> 
   <td colname="col2"> <p> Não. Quando a migração começar, todos os novos usuários e grupos de permissões (chamados de Perfis de produto no Adobe Admin Console) deverão estar criados no Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os usuários que eu migrar usando a ferramenta de migração receberia as mesmas permissões que tinham no Analytics? </p> </td> 
   <td colname="col2"> <p>Sim. Os usuários migrados usando a ferramenta terão as permissões que têm no Analytics. Além disso, eles manterão acesso aos ativos do Analytics (como segmentos, projetos, métricas calculadas e assim por diante) quando acessarem o Analytics pelo CX Enterprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os usuários que eu migrar para o Adobe Admin Console continuarão a ter acesso ao Analytics usando <span class="filepath">my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sim. Os usuários migrados ainda serão capazes de acessar o Analytics usando seus nomes de usuário e senhas existentes por meio de <span class="filepath">my.omniture.com</span> até a data final da migração, a menos que você desative o acesso de logon antigo na ferramenta de migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dois ou mais usuários têm a mesma ID de email em seus registros do Analytics. O que acontece se eu migrá-los? </p> </td> 
   <td colname="col2"> <p>Como as contas de usuários no Adobe Admin Console exigem IDs de email únicas, você receberá um erro de “ID de email duplicada” quando tentar migrar mais de um desses usuários. Você pode atualizar as IDs de email de usuários não migrados na seção Gerenciamento de usuários (herdada) antes de tentar novamente a migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> O que devo fazer depois de migrar meus usuários? </p> </td> 
   <td colname="col2"> <p>Desative o acesso de logon antigo para <span class="filepath">my.omniture.com</span>. Você não poderá desativar o logon antigo, a menos que ele tenha sido migrado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso rastrear o processo de migração? </p> </td> 
   <td colname="col2"> <p>A ferramenta de migração inclui um painel que exibe quantos dos usuários foram migrados com êxito e quantos deles têm o logon antigo desativado. </p> <p> Idealmente, você concluirá a migração de sua empresa de logon para o Adobe Admin Console quando 100% dos usuários tiverem completado a migração e tiverem seus logons antigos desativados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Preciso executar o gerenciamento de usuários e permissões durante a migração. Qual ferramenta posso usar para executar esta tarefa? </p> </td> 
   <td colname="col2"> <p>Após o início da migração, você usará o Adobe Admin Console para criar e gerenciar novos usuários e perfis de produtos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que meus usuários experimentam quando eu os migro usando a ferramenta? </p> </td> 
   <td colname="col2"> <p>Ele receberá um email de boas-vindas endereçado à ID de email em seu registro de usuário do Analytics, notificando-o sobre sua nova maneira de acessar o Analytics pelo CX Enterprise. Se não tiver um Adobe ID existente, será solicitado que ele crie um, depois do qual poderá acessar a solução usando o Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso usar APIs para migrar meus usuários em vez de usar a ferramenta de migração? </p> </td> 
   <td colname="col2"> <p>Não. Você deve usar a ferramenta de migração para garantir que todos os usuários existentes sejam migrados para o Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quais recursos de gerenciamento de usuários do Analytics não estão disponíveis no Adobe Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transferência de ativos </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Expiração do usuário </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Logs de usuário </li> 
    </ul> <p>Eles permanecerão disponíveis no gerenciamento de usuários do Analytics. </p> <p>Consulte <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">Recursos do Analytics não compatíveis com o Adobe Admin Console</a> para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criamos várias configurações no Adobe Admin Console e as mapeamos aos grupos de permissões do Analytics. O que acontecerá com essas configurações quando a migração começar? </p> </td> 
   <td colname="col2"> <p>Os grupos de permissões do Analytics serão recriados no Adobe Admin Console como perfis de produtos, assim como todos os outros grupos. Isso significa que você verá dois perfis de produtos no Console que essencialmente possuem permissões duplicadas. Você pode excluir perfis de produtos duplicados no Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual é o próximo passo após migrar os usuários? </p> </td> 
   <td colname="col2"> <p>Depois de migrar o usuário ou um conjunto de usuários, o próximo passo é desabilitar o logon antigo por <span class="filepath">my.omniture.com</span>. Você pode fazer isso selecionando esses usuários na ferramenta de migração e clicando na opção contextual “Desabilitar logon antigo” que aparece na parte superior da tela. Observe que essa opção fica visível somente quando você seleciona um usuário ou conjunto de usuários que foram migrados com sucesso para o Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que acontece na data final da migração? </p> </td> 
   <td colname="col2"> <p>Após a data de término da migração (60 dias a partir do início da migração), todos os usuários em sua empresa de logon serão redirecionados para fazer logon por meio da página de logon do CX Enterprise usando suas Adobe IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não consegui migrar todos os meus usuários até a data de término da migração. Os usuários não migrados perderiam o acesso ao Analytics? </p> </td> 
   <td colname="col2"> <p>Os usuários que não forem migrados até a data de término serão redirecionados para a página de logon do CX Enterprise (experiencecloud.adobe.com) e não poderão acessar o Analytics. Entretanto, você continuará a ter acesso à ferramenta de migração para que possa encontrá-los e migrá-los para restaurar o acesso. </p> </td> 
  </tr> 
 </tbody> 
</table>

## O que você deve saber após a migração (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta/Problema </th> 
   <th colname="col2" class="entry"> Respostas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Excluir usuários do Adobe Admin Console </p> </td> 
   <td colname="col2"> <p> No Analytics, um usuário excluído está definido como <span class="term"> expirado</span>, mas a conta continua a existir. Preservar a conta permite transferir ativos, como segmentos, métricas calculadas, relatórios agendados, projetos e assim por diante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expirações da conta </p> </td> 
   <td colname="col2"> <p> Você pode definir manualmente uma data de expiração de conta no Analytics nas Ferramentas administrativas. Depois que a data de expiração for atingida, o usuário não poderá acessar o Analytics, mas a conta de usuário real do CX Enterprise (por exemplo, Adobe ID, Enterprise ID, Federated ID etc.) não expira. Eles ainda podem fazer logon no CX Enterprise e não poderão clicar no Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recursos do Analytics não compatíveis com o Adobe Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Analise os seguintes problemas que podem se aplicar durante a migração.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta/Problema </th> 
   <th colname="col2" class="entry"> Respostas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fazer logon como </p> </td> 
   <td colname="col2"> <p> Os administradores que migrarem para o Adobe Admin Console não poderão mais usar a função “Fazer logon como” para acessar contas de usuários não-administradores que foram migradas para o Admin Console. Este recurso foi removido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiração do usuário e transferência de ativos </p> </td> 
   <td colname="col2"> <p> O Adobe Admin Console não suporta a expiração de usuários nem a transferência de ativos. Os administradores usarão a seção Usuários do Analytics e Assets em Ferramentas administrativas no Analytics para ambas as funções. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Último acesso (último logon) </p> </td> 
   <td colname="col2"> <p> Os detalhes sobre a data e a hora do último acesso dos usuários estarão disponíveis no link Usuários e ativos do Analytics e não no Adobe Admin Console. A última data de logon no Analytics é específica para quando os usuários realmente acessaram o Analytics no CX Enterprise e não reflete a data/hora quando fizeram logon no CX Enterprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>APIs de gerenciamento de usuários - <a href="https://helpx.adobe.com/br/enterprise/help/identity.html">Tipos de identidades suportadas pela Adobe</a> </p> </td> 
   <td colname="col2"> <p> Os administradores que migrarem para o Adobe Admin Console devem configurar APIs de gerenciamento de usuários oferecidas no Adobe Developer para permitir o acesso programático a contas de usuário no Adobe Admin Console. </p> <p>As APIs de permissão do Analytics serão desativadas quando você estiver habilitado para a migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenciais do Serviço Web </p> </td> 
   <td colname="col2"> <p> As credenciais do serviço Web dos usuários (e seus segredos compartilhados) não ficarão disponíveis no Adobe Admin Console e poderão ser acessadas ao clicar no usuário específico na seção de Usuários e ativos do Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logon único </p> </td> 
   <td colname="col2"> <p> As configurações de logon único do Analytics serão removidas quando você concluir a migração. Eles permanecerão ativos durante a migração. Os clientes que usam o logon único do Analytics devem atualizar para a <a href="https://helpx.adobe.com/br/enterprise/help/identity.html">Adobe Federated ID</a>. </p> <p>O Analytics recomenda que você migre seus usuários como Adobe IDs primeiro para criar facilmente as contas do CX Enterprise e, em seguida, converter essas contas para usuários federados de sinal único. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baixar grupos de permissões </p> </td> 
   <td colname="col2"> <p> O download de informações do Grupo de permissões não será mais suportado nas Ferramentas administrativas do Analytics nem no Adobe Admin Console. Os clientes devem usar as APIs de gerenciamento de usuários da adobe.io para obter informações do grupo de permissões em massa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data de criação da conta </p> </td> 
   <td colname="col2"> <p>As informações de Data de criação da conta não são mais suportadas nas Ferramentas administrativas do Analytics ou no Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Email em massa </p> </td> 
   <td colname="col2"> <p>O envio de emails em massa para os usuários não será mais aceito nas Ferramentas administrativas do Analytics nem no Adobe Admin Console. Os clientes poderão exportar em massa os endereços de email dos usuários do Adobe Admin Console e enviar um email usando qualquer cliente de email que quiserem. </p> </td> 
  </tr> 
 </tbody> 
</table>
