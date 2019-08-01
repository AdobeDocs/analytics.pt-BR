---
description: O que você precisa saber sobre a migração de IDs de usuários do Analytics para o Admin Console na Adobe Experience Cloud.
seo-description: O que você precisa saber sobre a migração de IDs de usuários do Analytics para o Admin Console na Adobe Experience Cloud.
seo-title: Migração de usuários do Analytics para o Admin Console
title: Migração de usuários do Analytics para o Admin Console
uuid: 7 d 020713-693 b -4945-aa 52-3669 a 631 aacb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# Migração de usuários do Analytics para o Admin Console{#analytics-user-migration-to-the-admin-console}

O que você precisa saber sobre a migração de IDs de usuários do Analytics para o Admin Console na Adobe Experience Cloud.

<!--
<p>FAQ <a href="https://wiki.corp.adobe.com/display/DMTM/Migration+FAQ" format="https" scope="external"> Source</a> </p>
-->

<!--
<p>Help publish link: <a href="https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/</a> </p>
<p>https://wiki.corp.adobe.com/display/analyticssolution/Migration+of+Analytics+Access+and+User+Management+to+the+Marketing+Cloud </p>
-->

Nesta página:

* [O que é a migração de IDs de usuários do ](../c-migration-tool/c-migration-tool.md#section-adbe49aba10c4e62afa836a97894107c)
* [O que você deve saber antes de migrar IDs de usuários (Perguntas frequentes)](../c-migration-tool/c-migration-tool.md#section-b0fc7f0bbd4b488e95b0c8e77ff077a9)
* [O que você deve saber durante a migração (Perguntas frequentes)](../c-migration-tool/c-migration-tool.md#section-d394524aa6d046d79025bbd7499792bc)
* [O que você deve saber após a migração (Perguntas frequentes)](../c-migration-tool/c-migration-tool.md#section-9681baa01b8c41cdb9659b73b70b50ff)
* [Recursos do Analytics não suportados no Admin Console](../c-migration-tool/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56)
* [Como notificar seus usuários sobre a migração](../c-migration-tool/c-migration-tool.md#section-f3b25f672a3a4d03b0559656fd99d20a)

Para obter ajuda geral sobre os tópicos do Admin Console (não relacionados à migração do Analytics), consulte o [Guia do usuário do Admin Console](https://helpx.adobe.com/enterprise/administering/user-guide.html).

Depois de migrar, você pode [gerenciar usuários e produtos da Experience Cloud](https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/) no Admin Console.

## O que é a migração de IDs de usuários do Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

A migração de ID de usuário do Analytics permite que os administradores migrem facilmente as contas de usuários do gerenciamento de usuários do Analytics para o Adobe Admin Console. Após a migração, os usuários terão acesso às soluções e aos serviços principais disponíveis na Experience Cloud. A migração das contas está acontecendo em fases.

Os benefícios de usar o Admin Console incluem:

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
   <td colname="col2"> <p>Os usuários do Analytics podem fazer logon na Experience Cloud e em todas as soluções usando a Adobe ID ou a Enterprise ID. Esse logon permite acessar as soluções integradas e os serviços principais da Experience Cloud. </p> <p>After the migration, users who attempt to sign in via legacy logins (<span class="filepath"> my.omniture.com</span> and <span class="filepath"> sc.omniture.com</span>) are redirected to <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerenciar a identidade do usuário e as permissões </p> </td> 
   <td colname="col2"> <p>Os administradores do Analytics podem gerenciar usuários e permissões exclusivamente no <a href="http://adminconsole.adobe.com/enterprise/" format="http" scope="external">Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerenciar produtos e serviços essenciais </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Convidar novos usuários </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Criar perfis de produto </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Conceder permissão aos usuários para produtos e serviços específicos </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Obter acesso aos <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html" format="html" scope="external">serviços essenciais das soluções</a> disponíveis na Adobe Experience Cloud </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## O que saber (e fazer) antes de migrar IDs de usuário (Perguntas frequentes) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Respostas às perguntas que você pode ter antes da migração.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta/tarefa </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eu sou um administrador do Analytics e recebi um email pré-migração. O que devo fazer primeiro? </p> </td> 
   <td colname="col2"> <p>Verifique se você possui uma Adobe ID e pode acessar o <a href="https://adminconsole.adobe.com/enterprise/" format="https" scope="external">Admin Console da Experience Cloud</a>. </p> <p>Caso contrário, entre em contato com o <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">Atendimento ao cliente da Adobe</a>. (Primeiro, você deve entrar em contato com o administrador do sistema ou do produto que poderá convidá-lo para a organização adequada). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrações AEM com o Analytics </p> </td> 
   <td colname="col2"> <p> Os usuários AEM com uma integração ao Analytics precisam alterar a configuração para usar o segredo compartilhado do Analytics em vez de uma senha. </p> <p> Você deve fazer isso antes de habilitar a migração. Depois de desabilitar a migração, a senha configurada inicialmente não será mais válida. </p> <p><b>Para obter um segredo compartilhado no Analytics</b> </p> <p> O segredo compartilhado pode ser obtido em Analytics (<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Gerenciamento de usuário</span>) e é diferente para cada usuário. </p> <p><b>Para atualizar a configuração AEM com o segredo compartilhado</b> </p> <p>Consulte <a href="https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html" format="html" scope="external">Conectar ao Adobe Analytics e Criar Frameworks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atualizar o Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: atualize sua instalação do <a href="https://marketing.adobe.com/resources/help/en_US/arb/t_install_arb.html" format="html" scope="external">Report Builder</a> para a versão mais recente. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quando a migração começa? </p> </td> 
   <td colname="col2"> <p>A Adobe notificará os administradores do Analytics por email com instruções sobre quando a migração começará. </p> <p>As migrações par ao Admin Console ocorrem em levas. No dia da migração, a Adobe notifica os administradores do Analytics e concede acesso à ferramenta de migração. Quando uma empresa de logon atender aos critérios definidos para cada leva de migração, a Adobe: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Definirá as datas de início e término da migração da empresa. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Enviará uma notificação por email aos administradores atuais do Analytics da empresa, aproximadamente 30 dias antes da migração. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Exibirá uma notificação no produto informando os administradores sobre a data de início da migração. </li> 
    </ul> <p> No dia da migração, os antigos grupos de permissão serão copiados automaticamente para o Admin Console. Não será mais possível convidar novos usuários ou criar novos grupos nas Ferramentas administrativas do Analytics. </p> <p>Após a migração: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Os administradores usarão o Admin Console para gerenciar os usuários e as permissões do Analytics. (Não será mais possível usar a interface de gerenciamento de usuários em Analytics &gt; Admin &gt; Gerenciamento de usuários.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Os usuários acessarão o Analytics usando a Adobe ID ou a Enterprise ID por meio da Experience Cloud, em vez de <span class="filepath">my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que acontecerá na data de início da migração? </p> </td> 
   <td colname="col2"> <p>Às 10h da manhã (UTC) na data de início da migração: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Seus grupos de permissão existentes no Analytics serão replicados automaticamente no Admin Console como Perfis de produtos, incluindo suas descrições e permissões granulares em conjuntos de relatórios, métricas, dimensões, Analytics e ferramentas do conjunto de relatórios. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Se um usuário atual do Analytics tiver sido criado no Admin Console (o que significará que tem uma Adobe/Enterprise ID vinculada), ele será adicionado ao Perfil de produto apropriado no Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">A seção Gerenciamento de usuários na guia Administrador do Google Analytics será definida como <span class="term"> somente leitura</span>. Não será mais possível criar novos usuários ou grupos de permissão aqui; essas funções deverão ser realizadas no Admin Console. Consulte <a href="../c-migration-tool/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56" format="dita" scope="local">Recursos do Analytics não suportados no Admin Console</a> para obter mais informações. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">Como administrador, você terá acesso à ferramenta <a href="../c-migration-tool/t-migrate-users.md" format="xml" scope="peer">Migração de ID do usuário</a>. Além disso, é exibida uma notificação no produto que inclui a data de término da migração (em geral, após 60 dias), além de links para conteúdo de ajuda e Perguntas frequentes. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Você terá acesso à guia Permissões no Admin Console, que permite criar Perfis de produtos com todas as opções granulares com as quais você está familiarizado no Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Como migrar IDs de usuários? </p> </td> 
   <td colname="col2"> <p> Clique em <a href="../c-migration-tool/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9" format="dita" scope="local"> Migrar IDs de usuários</a> na página Admin, em Gerenciamento de usuários. Use a ferramenta para adicionar usuário aos perfis de produto no Admin Console (replicado dos grupos de permissão no Analytics). Você pode migrar IDs de usuários em seu próprio ritmo. </p> <p>Será necessário ter privilégios administrativos. Quando a migração terminar, ela não poderá ser revertida. </p> <p>Na data de término da migração, o acesso a <span class="filepath">my.omniture.com</span> será desativado para os usuários em suas empresas de logon. Users (including those that are yet to be migrated) will be redirected to login via the new Experience Cloud URL (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>Nota: a Adobe recomenda aproveitar a oportunidade para realizar uma auditoria de seus usuários e grupos antes da migração. Exclua contas antigas e não utilizadas ou contas que não devem mais ter acesso ao produto (por exemplo, funcionários que não estão mais na organização). </p> <p>Related topic: <a href="../c-migration-tool/migrate-enterprise.md#topic-6fd22bc6fbc14fd69ce6a8518a5b9c00" format="dita" scope="local"> Migrate Analytics user accounts for Enterprise and Federated IDs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A migração afetará a minha implementação do Analytics ou a forma como os dados são coletados? </p> </td> 
   <td colname="col2"> <p>Não. </p> <p>A ferramenta de migração existe para ajudá-lo a migrar IDs de usuários e permissões do Gerenciamento de usuários do Analytics para o <a href="https://adminconsole.adobe.com/enterprise/" format="https" scope="external">Admin Console da Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual a duração do processo de migração? </p> </td> 
   <td colname="col2"> <p>Todos os administradores atuais do Analytics receberão um email de notificação quatro semanas antes da migração. (A data de início real será exibida na interface do Analytics). </p> <p>Quando a migração começar, os administradores terão 60 dias para concluir o processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso acelerar a minha migração? </p> </td> 
   <td colname="col2"> <p>Sim. Entretanto, a Adobe recomenda que você use o tempo antes do início da migração para: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Verificar se você é um administrador de produto do Analytics no Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunicar a sua base de usuários de que a experiência de logon mudará quando a migração for iniciada. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Auditar seus usuários e permissões atuais e realizar atividades de limpeza. </li> 
    </ul> <p>Para acelerar sua migração, entre em contato com o Gerente de sucesso do cliente pelo <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">Atendimento ao cliente da Adobe</a> e envie um pedido para antecipar a data de início da migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sou um administrador do Analytics e não tenho acesso ao Admin Console. Quem pode me ajudar a obter acesso ao Admin Console? </p> </td> 
   <td colname="col2"> <p>Qualquer administrador de sistema ou de produto que tenha acesso ao Admin Console na sua organização pode conceder o acesso a você. Se você não tem certeza de quem dentro da organização possui privilégios de administrador no Console, entre em contato com o <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">Atendimento ao cliente da Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso adiar a data de início da migração? </p> </td> 
   <td colname="col2"> <p>Sim. Entre em contato com o <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="html" scope="external">Atendimento ao cliente da Adobe</a>. </p> 
    <draft-comment> 
     <p>Veja abaixo uma descrição das alterações feitas ao gerenciamento de usuários e permissões atuais do Analytics na data de início. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agora que minha empresa está migrando para o Admin Console, onde posso criar novos usuários e grupos de permissão antes da data de início da migração? </p> </td> 
   <td colname="col2"> <p>Antes da data de início da migração, você poderá criar usuários no Admin Console ou em Analytics &gt; Gerenciamento de usuários. </p> <p>Após a migração, você poderá criar usuários e grupos de permissões somente no Admin Console. </p> 
    <draft-comment> 
     <p>consulte a seção Migração abaixo para obter mais detalhes sobre o que acontece na data de início da migração). </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Quando posso implementar o logon único usando Federated IDs? </p> </td> 
   <td colname="col2"> <p> Uma ferramenta estará disponível em breve no Admin Console que permitirá alterar os tipos de ID de Adobe ID para Federated ID. Durante a migração, não será possível migrar usuários como Federated IDs. </p> </td> 
  </tr> 
 </tbody> 
</table>

## O que você deve saber durante a migração (Perguntas frequentes) {#section-d394524aa6d046d79025bbd7499792bc}

Informações importantes sobre o processo de migração e como ele afeta o gerenciamento atual de usuários.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Como os grupos de permissão são replicados no Admin Console? E o que acontece com meus usuários? </p> </td> 
   <td colname="col2"> <p>Um grupo migrado do Analytics é chamado de <i>Perfil de produto</i> no Admin Console. As configurações de permissão do grupo original são mantidas na migração. Entretanto, os usuários atribuídos ao grupo não são migrados. Quando um usuário pertencente a esse grupo é migrado usando a ferramenta de migração, ele é atribuído a esse perfil de produto. </p> <p>Por exemplo, um grupo de permissões das Operações na Costa Oeste que autorizava seus membros para usar o Report Builder e a Analysis Workspace (com determinados conjuntos de relatórios, métricas, dimensões) se tornará um perfil de produto das Operações na Costa Oeste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso delegar a tarefa de migração para outro administrador? </p> </td> 
   <td colname="col2"> <p>Quando a migração começar, qualquer administrador que acessar sua instância do Analytics por meio da Experience Cloud poderá usar a ferramenta de migração para começar (ou continuar) a migrar usuários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso atualizar a associação de grupos de permissões para usuários não migrados? </p> </td> 
   <td colname="col2"> <p>Sim. Você pode alterar a associação de grupos de usuários não migrados na seção Gerenciamento de usuários do Analytics. </p> 
    <draft-comment> 
     <p>Aguardando esclarecimentos de Ashok sobre o local em que isso foi feito. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso criar usuários e grupos de permissões no Analytics após o início da migração e, em seguida, usar a ferramenta de migração para movê-los para o Admin Console? </p> </td> 
   <td colname="col2"> <p> Não. Quando a migração começar, todos os novos usuários e grupos de permissões (chamados de Perfis de produto no Admin Console) deverão estar criados no Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os usuários que eu migrar usando a ferramenta de migração receberão as mesmas permissões que tinham no Analytics? </p> </td> 
   <td colname="col2"> <p>Sim. Os usuários migrados usando a ferramenta receberão as permissões que possuem atualmente no Analytics. Além disso, manterão o acesso aos recursos do Analytics (como segmentos, projetos, métricas calculadas etc.) ao acessarem o Analytics por meio da Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os usuários que eu migrar para o Admin Console continuarão a ter acesso ao Analytics usando <span class="filepath">my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sim. Os usuários migrados ainda serão capazes de acessar o Analytics usando seus nomes de usuário e senhas existentes por meio de <span class="filepath">my.omniture.com</span> até a data de término da migração, a menos que você desative o acesso de logon antigo na ferramenta de migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dois ou mais dos meus usuários têm uma mesma ID de email em seus registros no Analytics. O que acontecerá se eu migrá-los? </p> </td> 
   <td colname="col2"> <p>Como as contas de usuários no Admin Console exigem IDs de email únicas, você receberá um erro de “ID de email duplicada” quando tentar migrar mais de um desses usuários. Você poderá atualizar as IDs de email dos usuários não migrados na seção Gerenciamento de usuários (antigo) antes de tentar migrar novamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> O que devo fazer depois de migrar meus usuários? </p> </td> 
   <td colname="col2"> <p>Desative o acesso de logon antigo para <span class="filepath">my.omniture.com</span>. Você não poderá desativar o logon antigo, a menos que os usuários tenham sido migrados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso acompanhar o processo de migração? </p> </td> 
   <td colname="col2"> <p>A ferramenta de migração inclui um painel de controle que mostra quantos usuários foram migrados com sucesso e quantos deles têm o logon antigo desativado. </p> <p> Idealmente, você concluirá a migração de sua empresa de logon para o Admin Console quando 100% dos usuários tiverem completado a migração e tiverem seus logons antigos desativados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eu preciso executar o gerenciamento de usuários e permissões durante a migração. Qual ferramenta posso usar para executar essa tarefa? </p> </td> 
   <td colname="col2"> <p>Após o início da migração, você usará o Admin Console para criar e gerenciar novos usuários e perfis de produtos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que meus usuários experienciam quando eu os migro usando a ferramenta? </p> </td> 
   <td colname="col2"> <p>Eles receberão um email de boas-vindas endereçado à ID de email em seus registros de usuários do Analytics, notificando-os sobre a nova forma de acessar o Analytics por meio da Experience Cloud. Se eles não tiverem uma Adobe ID existente, serão solicitados a criar uma e, depois disso, poderão acessar a solução usando a Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso usar APIs para migrar meus usuários, em vez de usar a ferramenta de migração? </p> </td> 
   <td colname="col2"> <p>Não. Você deve usar a ferramenta de migração para garantir que todos os usuários existentes sejam migrados para o Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quais recursos de gerenciamento de usuários do Analytics não estão disponíveis no Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transferência de ativos </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Expiração do usuário </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Logs de usuários </li> 
    </ul> <p>Esses recursos permanecerão disponíveis para você no gerenciamento de usuários do Analytics. </p> <p>Consulte <a href="../c-migration-tool/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56" format="dita" scope="local">Recursos do Analytics não suportados no Admin Console</a> para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criamos várias configurações no Admin Console e as mapeamos aos grupos de permissões do Analytics. O que acontecerá com essas configurações quando a migração começar? </p> </td> 
   <td colname="col2"> <p>Os grupos de permissões do Analytics serão recriados no Admin Console como perfis de produtos, assim como todos os outros grupos. Isso significa que você verá dois perfis de produtos no Console que essencialmente possuem permissões duplicadas. Você pode excluir perfis de produtos duplicados no Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual é o próximo passo após migrar os usuários? </p> </td> 
   <td colname="col2"> <p>Depois de migrar o usuário ou um conjunto de usuários, o próximo passo é desabilitar o logon antigo por <span class="filepath">my.omniture.com</span>. Você pode fazer isso selecionando esses usuários na ferramenta de migração e clicando na opção contextual “Desabilitar logon antigo” que aparece na parte superior da tela. Observe que essa opção fica visível somente quando você seleciona um usuário ou conjunto de usuários que foram migrados com sucesso para o Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que acontece na data de término da migração? </p> </td> 
   <td colname="col2"> <p>Após a data de término da migração (60 dias após o início da migração), todos os usuários da sua empresa de logon serão redirecionados para fazer o logon por meio da página de logon da Experience Cloud usando suas Adobe IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não consegui migrar todos os meus usuários até a data de término da migração. Os usuários não migrados perderão o acesso ao Analytics? </p> </td> 
   <td colname="col2"> <p>Os usuários que não foram migrados até a data de término serão redirecionados para a página de logon da Experience Cloud (experiencecloud.adobe.com) e não poderão acessar o Analytics. Entretanto, você continuará a ter acesso à ferramenta de migração para que possa encontrá-los e migrá-los para restaurar o acesso. </p> </td> 
  </tr> 
 </tbody> 
</table>

## O que você deve saber após a migração (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta / problema </th> 
   <th colname="col2" class="entry"> Respostas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Excluir usuários do Admin Console </p> </td> 
   <td colname="col2"> <p> No Analytics, um usuário excluído é configurado como <span class="term"> expirado</span>, mas a conta continua a existir. A preservação da conta permite a transferência de ativos, como segmentos, métricas calculadas, relatórios agendados, projetos, entre outros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiração da conta </p> </td> 
   <td colname="col2"> <p> Você pode definir manualmente uma data de expiração da conta do Analytics nas Ferramentas administrativas. Quando a data de validade chegar, o usuário não poderá acessar o Analytics, mas a conta de usuário da Experience Cloud (exemplo, Adobe ID, Enterprise ID, Federated ID etc.) não expira. Eles ainda pode acessar a Experience Cloud, mas não poderão clicar no Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recursos do Analytics não suportados no Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Analise os seguintes problemas que podem ser aplicados a você durante a migração.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta / problema </th> 
   <th colname="col2" class="entry"> Respostas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fazer logon como </p> </td> 
   <td colname="col2"> <p> Os administradores que migrarem para o Admin Console não poderão mais usar a função “Fazer logon como” para acessar contas de usuários não-administradores que foram migradas para o Admin Console. Esse recurso está sendo descontinuado no Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiração de usuários e transferência de ativos </p> </td> 
   <td colname="col2"> <p> O Admin Console não suporta a expiração de usuários nem a transferência de ativos. Os administradores usarão a seção Usuários e ativos do Analytics em Ferramentas administrativas no Analytics para realizar essas funções. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Último acesso (Último logon) </p> </td> 
   <td colname="col2"> <p> Os detalhes sobre a data e a hora do último acesso dos usuários estarão disponíveis no link Usuários e ativos do Analytics e não no Admin Console. A última data de logon no Analytics reflete especificamente o momento em que os usuários realmente acessaram o Analytics por meio da Marketing Cloud e não reflete a data/hora em que fizeram logon na Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>APIs de gerenciamento de usuários - <a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">Tipos de identidades suportadas pela Adobe</a> </p> </td> 
   <td colname="col2"> <p> Os administradores que migrarem para o Admin Console devem configurar <a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html" format="html" scope="external">APIs de gerenciamento de usuários</a> oferecidas no Adobe I/O para permitir o acesso programático a contas de usuário no Admin Console. </p> <p>As APIs de permissão do Analytics serão desativadas quando você estiver apto para a migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenciais do Serviço Web </p> </td> 
   <td colname="col2"> <p> As credenciais do serviço Web dos usuários (e seus segredos compartilhados) não ficarão disponíveis no Admin Console e poderão ser acessadas ao clicar no usuário específico na seção de Usuários e ativos do Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logon único </p> </td> 
   <td colname="col2"> <p> As configurações de logon único do Analytics serão removidas ao concluir a migração. Elas permanecerão ativas durante a migração. Os clientes que usam o logon único do Analytics devem atualizar para a <a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">Adobe Federated ID</a>. </p> <p>O Analytics recomenda primeiro migrar os usuários como Adobe IDs para facilitar a criação das contas da Experience Cloud e, em seguida, converter essas contas em usuários de logon único Federados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Download de grupos de permissões </p> </td> 
   <td colname="col2"> <p> O download de informações do grupo de permissões não será mais suportado nas Ferramentas administrativas do Analytics nem no Adobe Admin Console. Os clientes deverão usar as APIs de gerenciamento de usuários adobe.io para obter informações do grupo de permissões em massa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data de criação da conta </p> </td> 
   <td colname="col2"> <p>As informações de Data de criação da conta não serão mais suportadas nas Ferramentas administrativas do Analytics nem no Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Email em massa </p> </td> 
   <td colname="col2"> <p>O envio de emails em massa para os usuários não será mais suportado nas Ferramentas administrativas do Analytics nem no Adobe Admin Console. Os clientes poderão exportar em massa os endereços de email dos usuários do Adobe Admin Console e enviar um email usando qualquer cliente de email que quiserem. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como notificar seus usuários sobre a migração {#section-f3b25f672a3a4d03b0559656fd99d20a}

Você pode comunicar proativamente este plano de migração aos seus usuários atuais. Este é um modelo que você pode personalizar para enviar a todos os usuários atuais do Analytics:

To email all users, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; [Email Users](https://marketing.adobe.com/resources/help/en_US/reference/t_email_users.html).

**Assunto:** Em breve - Uma nova forma de fazer logon no Adobe Analytics e na Adobe Experience Cloud.

** Corpo: ** Hello Adobe Analytics Users!

Our company will begin migrating all Adobe Analytics accounts away from [!DNL https://my.omniture.com/login/] to Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). Com essa migração, sua conta do Adobe Analytics será atualizada para permitir o acesso ao Analytics por meio da Adobe Experience Cloud. Apesar da alteração do método para acessar o Analytics, todas as permissões existentes para seus conjuntos de relatórios e ferramentas serão preservadas.

** Próximas etapas: ** Começaremos a migrar os usuários iniciando em <INSERT DATE>. Fique atento para uma mensagem de boas-vindas com o seu novo logon endereçada à ID de email listada em sua conta do Analytics. Se você não tiver configurado uma [Adobe ID](https://helpx.adobe.com/x-productkb/global/adobe-id-account-change.html) vinculada ao seu endereço de email, você será solicitado a configurar uma conta.

**Recursos úteis:**

[Fazer logon e gerenciar as configurações do seu perfil](https://marketing.adobe.com/resources/help/en_US/mcloud/getting-started-experience-cloud.html).

[Sobre nuvens, serviços principais e soluções](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) na Experience Cloud

Entre em contato com os administradores do Analytics em caso de dúvidas ou preocupações.

Atenciosamente,

Administrador do Analytics
