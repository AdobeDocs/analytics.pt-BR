---
description: O que você precisa saber sobre a migração de IDs de usuários do Analytics para o Admin Console na Adobe Experience Cloud.
title: Migração de usuários do Analytics para o Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Migração de usuários do Analytics para o Admin Console {#analytics-user-migration-to-the-admin-console}

O que você precisa saber sobre a migração de IDs de usuários do Analytics para o Admin Console na Adobe Experience Cloud.

Para obter ajuda geral sobre os tópicos do Admin Console (não relacionados à migração do Analytics), consulte o [Guia do usuário do Admin Console](https://helpx.adobe.com/br/enterprise/administering/user-guide.html).

Após a migração, você pode [gerenciar usuários e produtos](https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/admin-getting-started.html) da Experience Cloud no Admin Console.

## O que é a migração de IDs de usuários do Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

A migração da ID de usuário do Analytics permite que os administradores migrem facilmente as contas de usuário no Gerenciamento de usuários do Analytics para o Adobe Admin Console. Depois que os usuários forem migrados, eles terão acesso às soluções e aos principais serviços disponíveis na Experience Cloud. A migração está sendo implementada para os clientes em fases.

Os benefícios do uso do Admin Console incluem:

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Benefício </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Logon único </p> </td> 
   <td colname="col2"> <p>Os usuários do Analytics podem fazer logon na Experience Cloud e em todas as soluções usando sua Adobe ID ou Enterprise ID. Esse logon permite acessar soluções integradas e os principais serviços na Experience Cloud. </p> <p>Após a migração, os usuários que tentarem fazer logon por meio de logons antigos (<span class="filepath">my.omniture.com</span> e <span class="filepath">sc.omniture.com</span>) serão redirecionados para <span class="filepath">experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerenciar a identidade do usuário e as permissões </p> </td> 
   <td colname="col2"> <p>Os administradores do Analytics podem gerenciar usuários e permissões exclusivamente no <a href="http://adminconsole.adobe.com/enterprise/">Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerenciar produtos e principais serviços </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Convidar novos usuários </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Criar perfis de produtos </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Conceder aos usuários permissão para produtos e serviços específicos </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Obter acesso aos <a href="https://docs.adobe.com/content/help/pt-BR/core-services/interface/experience-cloud.html">serviços essenciais das soluções</a> disponíveis na Adobe Experience Cloud </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## O que saber (e fazer) antes de migrar IDs de usuário (Perguntas frequentes) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Respostas às perguntas que você pode ter antes da migração.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta / Tarefa </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sou um administrador do Analytics e recebi um email de pré-migração. O que eu faço primeiro? </p> </td> 
   <td colname="col2"> <p>Verifique se você possui uma Adobe ID e pode acessar o <a href="https://adminconsole.adobe.com/enterprise/">Admin Console da Experience Cloud</a>. </p> <p>Caso contrário, entre em contato com o <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Atendimento ao cliente da Adobe</a>. (Primeiro, você deve entrar em contato com o administrador do sistema ou do produto que poderá convidá-lo para a organização adequada). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrações do AEM com o Analytics </p> </td> 
   <td colname="col2"> <p> Os usuários do AEM que tiverem uma integração com o Analytics precisarão alterar sua configuração para usar o segredo compartilhado do Analytics em vez da senha. </p> <p> Você deve fazer isso antes de ativar a migração. Quando a migração estiver desativada, a senha configurada originalmente não será mais válida. </p> <p><b>Para obter o segredo compartilhado no Analytics</b> </p> <p> O segredo compartilhado pode ser obtido em Analytics (<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Gerenciamento de usuário</span>) e é diferente para cada usuário. </p> <p><b>Para atualizar a configuração AEM com o segredo compartilhado</b> </p> <p>Consulte <a href="https://helpx.adobe.com/br/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">Conectar ao Adobe Analytics e Criar Frameworks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atualizar o Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: atualize sua instalação do <a href="https://marketing.adobe.com/resources/help/pt_BR/arb/t_install_arb.html">Report Builder</a> para a versão mais recente. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quando a migração começa? </p> </td> 
   <td colname="col2"> <p>A Adobe notificará os administradores do Analytics por email com instruções sobre quando a migração será iniciada. </p> <p>As migrações para o Admin Console ocorrerão no ondas. No dia da migração, a Adobe notifica os administradores do Analytics e concede acesso à ferramenta de migração. Depois que uma empresa de logon atender aos critérios definidos para cada onda de migração, a Adobe: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Defina as datas de start e término da migração do empresa. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Envie uma notificação por email aos administradores atuais do Analytics do empresa, aproximadamente 30 dias antes da migração. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Exiba uma notificação no produto informando os administradores da data do start da migração. </li> 
    </ul> <p> No dia da migração, seus antigos grupos de permissões são copiados automaticamente para o Admin Console. Não será mais possível convidar novos usuários ou criar novos grupos nas Ferramentas administrativas do Analytics. </p> <p>Após a migração: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Os administradores usarão o Admin Console para gerenciar seus usuários e permissões do Analytics. (Você não usará mais a interface de gerenciamento de usuários em Analytics &gt; Administrador &gt; Gerenciamento de usuários.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Os usuários acessarão o Analytics usando a Adobe ID ou a Enterprise ID por meio da Experience Cloud, em vez de <span class="filepath">my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que acontecerá na data de start da migração? </p> </td> 
   <td colname="col2"> <p>Às 10:00 UTC na data de start da migração: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Seus grupos de permissões existentes no Analytics serão replicados automaticamente no Admin Console como Perfis de produtos, incluindo suas descrições e permissões granulares em conjuntos de relatórios, métricas, dimensões, Analytics e ferramentas de conjunto de relatórios. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Se algum de seus usuários atuais do Analytics tiver sido criado no Admin Console (o que significa que eles têm uma Adobe/Enterprise ID vinculada), eles serão adicionados aos Perfis de Produto apropriados no Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">A seção Gerenciamento de usuários na guia Administrador do Google Analytics será definida como <span class="term"> somente leitura</span>. Não será mais possível criar novos usuários ou grupos de permissão aqui; essas funções deverão ser realizadas no Admin Console. Consulte <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Recursos do Analytics não suportados no Admin Console</a> para obter mais informações. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">Como administrador, você receberá acesso à ferramenta <a href="https://marketing.adobe.com/resources/help/pt_BR/experience-cloud/admin-console/analytics-migration/t_migrate-users.html">de Migração de ID de</a>usuário. Além disso, é exibida uma notificação no produto que inclui a data de término da migração (normalmente 60 dias no futuro), além de links para conteúdo de ajuda e perguntas frequentes. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Você receberá acesso a uma guia Permissões no Admin Console que permite criar Perfis de produtos com todas as opções granulares que você conhece no Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Como migrar IDs de usuário? </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. Use a ferramenta para adicionar usuários a perfis de produtos no Admin Console (replicados de grupos de permissões no Analytics). Você pode migrar IDs de usuário em seu próprio ritmo. </p> <p>São necessários privilégios de administração. Quando a migração estiver concluída, ela não poderá ser revertida. </p> <p>Na data de término da migração, o acesso a <span class="filepath">my.omniture.com</span> será desativado para os usuários em suas empresas de logon. Os usuários (incluindo aqueles que ainda não foram migrados) serão redirecionados para fazer logon por meio do novo URL da Experience Cloud (<span class="filepath">experiencecloud.adobe.com</span>) </p> <p>Nota: a Adobe recomenda aproveitar a oportunidade para realizar uma auditoria de seus usuários e grupos antes da migração. Exclua contas antigas e não utilizadas ou contas que não devem mais ter acesso ao produto (por exemplo, funcionários que não estão mais na organização). </p> <p>Tópico relacionado: <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Migrar contas de usuário do Analytics para Enterprise e Federated IDs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A migração afetará minha implementação do Analytics ou como os dados são coletados? </p> </td> 
   <td colname="col2"> <p>Não. </p> <p>A ferramenta de migração existe para ajudá-lo a migrar IDs de usuários e permissões do Gerenciamento de usuários do Analytics para o <a href="https://adminconsole.adobe.com/enterprise/">Admin Console da Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quanto tempo demora o processo de migração? </p> </td> 
   <td colname="col2"> <p>Todos os administradores atuais do Analytics receberão um email de notificação de pré-migração quatro semanas antes da migração. (A data real do start será exibida na interface do Analytics.) </p> <p>Quando a migração começar, os administradores terão 60 dias para concluir o processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso acelerar minha migração? </p> </td> 
   <td colname="col2"> <p>Sim. No entanto, a Adobe recomenda que você use o tempo antes da migração começar a: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Verifique se você é um administrador de produtos do Analytics no Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunique à sua base de usuários que a experiência de logon mudará quando a migração começar. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Audite seus usuários e permissões atuais e execute atividades de limpeza. </li> 
    </ul> <p>Para acelerar sua migração, entre em contato com o Gerente de sucesso do cliente pelo <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Atendimento ao cliente da Adobe</a> e envie um pedido para antecipar a data de início da migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sou um administrador do Analytics sem acesso ao Admin Console. Quem pode me ajudar a obter acesso ao Admin Console? </p> </td> 
   <td colname="col2"> <p>Qualquer administrador de sistema ou de produto que tenha acesso ao Admin Console na sua organização pode conceder o acesso a você. Se você não tem certeza de quem dentro da organização possui privilégios de administrador no Console, entre em contato com o <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Atendimento ao cliente da Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso adiar a data de início da migração? </p> </td> 
   <td colname="col2"> <p>Sim. Entre em contato com o <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Atendimento ao cliente da Adobe</a>. </p> 
    <draft-comment> 
     <p>Consulte abaixo uma descrição das alterações feitas no gerenciamento de usuários e permissões atual do Analytics na data de início. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agora que minha empresa está migrando para o Admin Console, onde posso criar novos usuários e grupos de permissões antes da data de start da migração? </p> </td> 
   <td colname="col2"> <p>Antes da data do start de migração, você pode criar usuários no Admin Console ou em Analytics &gt; Gerenciamento de usuários. </p> <p>Após o início da migração, você pode criar usuários e grupos de permissões somente no Admin Console. </p> 
    <draft-comment> 
     <p>Consulte a seção Migração abaixo para obter mais detalhes sobre o que acontece na data de início da migração). </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Quando posso implementar o logon único usando Federated IDs? </p> </td> 
   <td colname="col2"> <p> Uma ferramenta estará disponível em breve no Admin Console que permite alterar tipos de ID de Adobe ID para Federated IDs. Durante a migração, não é possível migrar usuários como Federated IDs. </p> </td> 
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
   <td colname="col1"> <p>Como os grupos de permissão são replicados no Admin Console? E os meus usuários? </p> </td> 
   <td colname="col2"> <p>Um grupo migrado do Analytics é um Perfil <i>de</i> produto no Admin Console. As configurações de permissão para o grupo original são mantidas na migração. No entanto, os usuários atribuídos ao grupo não são migrados. Quando um usuário pertencente a esse grupo é migrado usando a ferramenta de migração, esse usuário é atribuído a esse perfil de produto. </p> <p>Por exemplo, um grupo de permissão Operações na Costa Oeste que autorizava seus membros para o Construtor de relatórios e a Área de trabalho da Análise (com determinados conjuntos de relatórios, métricas, dimensões) se tornará um perfil de produtos Operações na Costa Oeste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso delegar o esforço de migração para outro administrador? </p> </td> 
   <td colname="col2"> <p>Quando a migração começar, qualquer administrador que acessar a instância do Analytics por meio da Experience Cloud poderá usar a ferramenta de migração para iniciar (ou continuar) a migração de usuários. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso atualizar a associação de grupo de permissões para usuários não migrados? </p> </td> 
   <td colname="col2"> <p>Sim. Você pode alterar a associação de grupo de usuários não migrados na seção Gerenciamento de usuários do Analytics. </p> 
    <draft-comment> 
     <p>Aguardando esclarecimentos de Ashok sobre o que é feito. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>É possível criar usuários e grupos de permissões no Analytics após o início da migração e usar a ferramenta de migração para movê-los para o Admin Console? </p> </td> 
   <td colname="col2"> <p> Não. Quando a migração começar, todos os novos usuários e grupos de permissões (chamados Perfis de produtos no Admin Console) deverão ser criados no Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os usuários que eu migrar usando a ferramenta de migração receberão as mesmas permissões que tinham no Analytics? </p> </td> 
   <td colname="col2"> <p>Sim. Os usuários migrados usando a ferramenta receberão as permissões que possuem no momento no Analytics. Além disso, eles manterão o acesso aos ativos do Analytics (como segmentos, projetos, métricas calculadas etc.) quando acessarem o Analytics por meio da Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os usuários que eu migrar para o Admin Console continuarão a ter acesso ao Analytics usando <span class="filepath">my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sim. Os usuários migrados ainda serão capazes de acessar o Analytics usando seus nomes de usuário e senhas existentes por meio de <span class="filepath">my.omniture.com</span> até a data de término da migração, a menos que você desative o acesso de logon antigo na ferramenta de migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dois ou mais usuários têm a mesma ID de email em seus registros do Analytics. O que acontece se eu os migrar? </p> </td> 
   <td colname="col2"> <p>Como as contas de usuário no Admin Console exigem IDs de email exclusivas, você verá um erro de "ID de email do Duplicado" ao tentar migrar mais de um desses usuários. Você pode atualizar as IDs de email de usuários não migrados na seção Gerenciamento de usuários (herdado) antes de tentar a migração novamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> O que devo fazer depois de migrar meus usuários? </p> </td> 
   <td colname="col2"> <p>Desative o acesso de logon antigo para <span class="filepath">my.omniture.com</span>. Você não poderá desativar o logon antigo, a menos que eles tenham sido migrados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso rastrear o processo de migração? </p> </td> 
   <td colname="col2"> <p>A ferramenta de migração inclui um painel que mostra quantos de seus usuários foram migrados com êxito e quantos deles têm seu logon antigo desativado. </p> <p> Idealmente, você terá migrado com êxito sua empresa de logon para o Admin Console quando 100% dos usuários tiverem concluído a migração e tiverem seus logons antigos desativados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Preciso executar o gerenciamento de usuários e permissões durante a migração. Qual ferramenta posso usar para executar esta tarefa? </p> </td> 
   <td colname="col2"> <p>Após o início da migração, você usará o Admin Console para criar e gerenciar novos usuários e perfis de produtos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que meus usuários experimentam ao migrá-los usando a ferramenta? </p> </td> 
   <td colname="col2"> <p>Eles receberão um email de boas-vindas endereçado à ID de email em seus registros de usuários do Analytics, notificando-os sobre sua nova maneira de acessar o Analytics por meio da Experience Cloud. Se eles não tiverem uma Adobe ID existente, serão solicitados a criar uma, após a qual poderão acessar a solução usando sua Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso usar as APIs para migrar meus usuários em vez de usar a ferramenta de migração? </p> </td> 
   <td colname="col2"> <p>Não. Você deve usar a ferramenta de migração para garantir que todos os usuários existentes sejam migrados para o Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quais recursos de gerenciamento de usuários do Analytics não estão disponíveis no Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transferência de ativos </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Expiração do usuário </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Logs do usuário </li> 
    </ul> <p>Elas permanecerão disponíveis para você no gerenciamento de usuários do Analytics. </p> <p>Consulte <a href="/help/admin/user-management2/user-migration/c-migration-tool.md">Recursos do Analytics não suportados no Admin Console</a> para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criamos várias configurações no Admin Console e as mapeamos para grupos de permissão do Analytics. O que acontecerá com essas configurações quando a migração começar? </p> </td> 
   <td colname="col2"> <p>Os grupos de permissão do Analytics são recriados no Admin Console como perfis de produtos, assim como todos os outros grupos. Isso significa que você verá dois perfis de produto no console que essencialmente têm permissões de duplicado. Você pode excluir perfis de produtos do duplicado do Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual é o próximo passo após migrar o usuário? </p> </td> 
   <td colname="col2"> <p>Depois de migrar o usuário ou um conjunto de usuários, o próximo passo é desabilitar o logon antigo por <span class="filepath">my.omniture.com</span>. Você pode fazer isso selecionando esses usuários na ferramenta de migração e clicando na opção contextual "Desativar logon antigo" que aparece na parte superior da tela. Observe que essa opção só é visível quando você seleciona um usuário ou conjunto de usuários que foram migrados com êxito para o Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que acontece na data de término da migração? </p> </td> 
   <td colname="col2"> <p>Após a data de término da migração (60 dias a partir do start da migração), todos os usuários na empresa de logon serão redirecionados para fazer logon pela página de logon da Experience Cloud usando suas Adobe IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não consegui migrar todos os meus usuários até a data de término da migração. Os usuários não migrados perderiam seu acesso ao Analytics? </p> </td> 
   <td colname="col2"> <p>Os usuários que não forem migrados até a data de término serão redirecionados para a página de logon da Experience Cloud (experiencecloud.adobe.com) e não poderão acessar o Analytics. Entretanto, você continuará a ter acesso à ferramenta de migração para que possa encontrá-los e migrá-los para restaurar o acesso. </p> </td> 
  </tr> 
 </tbody> 
</table>

## O que você deve saber após a migração (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta/problema </th> 
   <th colname="col2" class="entry"> Respostas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Excluindo usuários do Admin Console </p> </td> 
   <td colname="col2"> <p> No Analytics, um usuário excluído é configurado como <span class="term"> expirado</span>, mas a conta continua a existir. A preservação da conta permite que os ativos de transferência, como segmentos, métricas calculadas, relatórios programados, projetos e assim por diante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expirações da conta </p> </td> 
   <td colname="col2"> <p> Você pode definir manualmente uma data de expiração de conta no Analytics nas Ferramentas administrativas. Quando a data de expiração for atingida, o usuário não poderá acessar o Analytics, mas sua conta de usuário real da Experience Cloud (por exemplo, Adobe ID, Enterprise ID, Federated ID etc.) não expira. Eles ainda podem fazer logon na Experience Cloud, mas não poderão clicar no Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recursos do Analytics não suportados no Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Analise os seguintes problemas que podem se aplicar durante a migração.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta/problema </th> 
   <th colname="col2" class="entry"> Respostas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fazer logon como </p> </td> 
   <td colname="col2"> <p> Os administradores que migrarem para o Admin Console não poderão mais usar a função "Fazer logon como" para acessar contas de usuário não administrativas que foram migradas para o Admin Console. Esse recurso está sendo descontinuado do Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiração do usuário e transferência de ativos </p> </td> 
   <td colname="col2"> <p> O Admin Console não oferece suporte à expiração do usuário nem à transferência de ativos. Os administradores usarão a seção Usuários e ativos do Analytics em Ferramentas administrativas no Analytics para ambas as funções. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Último acesso (último logon) </p> </td> 
   <td colname="col2"> <p> Detalhes sobre a data e a hora do último logon de um usuário estarão disponíveis no link Usuários e ativos do Analytics e não no Admin Console. A última data de logon no Analytics reflete especificamente o momento em que os usuários realmente acessaram o Analytics por meio da Experience Cloud e não reflete a data/hora em que fizeram logon na Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>APIs de gerenciamento de usuários - <a href="https://helpx.adobe.com/br/enterprise/help/identity.html">Tipos de identidades suportadas pela Adobe</a> </p> </td> 
   <td colname="col2"> <p> Os administradores que migrarem para o Admin Console devem configurar <a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">APIs de gerenciamento de usuários</a> oferecidas no Adobe I/O para permitir o acesso programático a contas de usuário no Admin Console. </p> <p>As APIs de permissão do Analytics serão desativadas quando você estiver habilitado para a migração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenciais do Serviço Web </p> </td> 
   <td colname="col2"> <p> As credenciais de serviço da Web dos usuários (e seu segredo compartilhado) não estarão disponíveis no Admin Console e poderão ser acessadas clicando no usuário específico na seção Usuários e ativos do Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logon único </p> </td> 
   <td colname="col2"> <p> As configurações de logon único do Analytics serão removidas quando você concluir a migração. Elas permanecerão ativas durante a migração. Os clientes que usam o logon único do Analytics devem atualizar para a <a href="https://helpx.adobe.com/br/enterprise/help/identity.html">Adobe Federated ID</a>. </p> <p>O Analytics recomenda migrar os usuários como Adobe IDs primeiro para criar facilmente as contas da Experience Cloud e, em seguida, convertê-las em usuários de logon único Federados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Download de grupos de permissão </p> </td> 
   <td colname="col2"> <p> O download das informações do grupo de permissões não será mais suportado nas Ferramentas administrativas do Analytics nem no Adobe Admin Console. Os clientes devem usar as APIs de gerenciamento de usuários do adobe.io para obter informações de grupos de permissões em massa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data de criação da conta </p> </td> 
   <td colname="col2"> <p>As informações de Data de criação da conta não são mais suportadas nas Ferramentas administrativas do Analytics nem no Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Email em massa </p> </td> 
   <td colname="col2"> <p>Os emails em massa para usuários não serão mais suportados no Admin Console do Analytics nem no Adobe Admin Console. Os clientes podem exportar em massa os endereços de email dos usuários do Adobe Admin Console e enviar um email usando qualquer cliente de email que desejarem. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como notificar seus usuários sobre a migração {#section-f3b25f672a3a4d03b0559656fd99d20a}

Talvez você queira comunicar proativamente este plano de migração aos usuários atuais. Este é um modelo que você pode personalizar para enviar a todos os usuários atuais do Analytics:

Para enviar um email para todos os usuários, navegue até **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > Usuários [](https://marketing.adobe.com/resources/help/pt_BR/reference/t_email_users.html)de email.

**Assunto:** Em breve - Uma nova forma de fazer logon no Adobe Analytics e na Adobe Experience Cloud.

**Corpo:** Olá, usuários do Adobe Analytics!

Nossa empresa começará a migrar todas as contas do Adobe Analytics de [!DNL https://my.omniture.com/login/] para a Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). Com essa migração, sua conta do Adobe Analytics será atualizada para permitir o acesso ao Analytics por meio da Adobe Experience Cloud. Embora o método para acessar o Analytics seja alterado, todas as permissões existentes para seus conjuntos de relatórios e ferramentas serão preservadas.

**Próximas etapas:** começaremos a migrar os usuários a partir de **INSERIR DATA**. Aguarde uma mensagem de boas-vindas com seu novo logon endereçado à ID de e-mail listada em sua conta do Analytics. Se você não tiver configurado uma ID [da](https://helpx.adobe.com/br/x-productkb/global/adobe-id-account-change.html) Adobe vinculada ao seu endereço de email, será solicitado que você configure uma conta.

**Recursos úteis:**

[Fazer logon e gerenciar as configurações do seu perfil](https://marketing.adobe.com/resources/help/pt_BR/mcloud/getting-started-experience-cloud.html).

[Sobre nuvens, principais serviços e soluções](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) na Experience Cloud

Entre em contato com os administradores do Analytics se tiver dúvidas ou preocupações.

Melhor,

Administrador do Analytics
