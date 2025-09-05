---
description: Gerencie usuários, grupos e produtos do Analytics no Adobe Admin Console.
subtopic: Users and groups
title: Gerenciamento de usuários e produtos
feature: Admin Tools
exl-id: c0fbbb3a-0011-49d2-89a2-70fce11e0fb2
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 100%

---

# Gerenciamento de usuários e produtos (herdado)

Gerencie usuários, grupos e produtos do Analytics no Adobe Admin Console.

>[!IMPORTANT]
>
>O gerenciamento de usuários e produtos foi movido para o [Adobe Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). Para começar a gerenciar permissões de usuário do Adobe Analytics, consulte [Analytics no Adobe Admin Console](/help/admin/admin-console/home.md).

## Recursos de ajuda para administradores do Adobe Admin Console {#help}

| Tarefa ou recurso | Descrição |
| --- | --- |
| Migrar IDs de usuários do Analytics para o Adobe Admin Console | A Adobe está auxiliando os administradores do Analytics a migrar as IDs de usuário para o Adobe Admin Console. Esse esforço ocorrerá em ondas. Quando for sua vez de migrar os usuários, a Adobe notificará os administradores do Analytics por email com instruções. Uma ferramenta de migração está disponível em [User Management do Analytics](/help/admin/tools/user-management/user-migration/c-migration-tool.md) para simplificar esta tarefa.<p>**Importante**: no dia da migração dos usuários, os antigos grupos de permissão serão copiados automaticamente para o Adobe Admin Console. Não será mais possível convidar novos usuários ou criar novos grupos nas Ferramentas administrativas do Analytics. Consulte as Perguntas frequentes e a ajuda para a Migração de usuários do Analytics para o Adobe Admin Console e assim obter informações sobre como se preparar para a migração e sobre os recursos administrativos afetados. |
| Iniciar o Adobe Admin Console | Depois que suas contas de usuário forem migradas, será possível gerenciar usuários e produtos de todas as soluções no Adobe Admin Console. Navegue até: `https://adminconsole.adobe.com/enterprise/`. Consulte também [Gerenciar usuários e produtos da Experience Cloud](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/administration/admin-getting-started). |
| Gerenciar perfis de produtos, usuários e permissões do Adobe Analytics | Consulte [Analytics no Adobe Admin Console](/help/admin/admin-console/home.md). |

<!---
## User Management Descriptions {#section_7C19842A3D4249109A9399D4DF18DE75}

The following table describes elements on the [!UICONTROL Users] tab in [!UICONTROL User Management].

<table id="table_6F81D1095EB945D8995FF971B65BA52A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins available</span> </td> 
   <td colname="col2"> The maximum number of user accounts you can create for this company. If necessary, you can contact your Account Representative or Customer Care to increase this number at no charge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins in use</span> </td> 
   <td colname="col2"> The number of user accounts currently in use for this company. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins Remaining</span> </td> 
   <td colname="col2"> The difference between the user account maximum and the number of existing user accounts. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add New User</span> </td> 
   <td colname="col2"> <p>Lets you add a user account to the company. This link is available only if the Number of User Logins Remaining is greater than 0. </p> <p>See <a href="/help/admin/user-management/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Download Report</span> </td> 
   <td colname="col2">Exports the contents of the <span class="wintitle"> Users</span> table to a tab-delimited file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Login</span> </td> 
   <td colname="col2"> <p>The user name. You can click the user name to edit the user account properties. </p> <p>See <a href="/help/admin/user-management/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> First Name</span> </td> 
   <td colname="col2"> The user's first (given) name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Name</span> </td> 
   <td colname="col2"> The user's surname (family name). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Title</span> </td> 
   <td colname="col2"> The user's job title. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Admin</span> </td> 
   <td colname="col2"> Specifies if the user account has administrative privileges. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Login</span> </td> 
   <td colname="col2"> Displays a timestamp of the last login for this user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Create Time</span> </td> 
   <td colname="col2"> Shows the date and time when the login account was created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expires</span> </td> 
   <td colname="col2"> Displays the account expiration account, if applicable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Manage</span> </td> 
   <td colname="col2"> Provides links for user account management. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit</span> </td> 
   <td colname="col2"> <p>Edit user account settings. </p> <p>See <a href="/help/admin/user-management/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Delete</span> </td> 
   <td colname="col2"> Delete the user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transfer</span> </td> 
   <td colname="col2">Assign the privileges (permissions and resource access) of one user account to another. <p>See <a href="/help/admin/user-management/c-user-management/t-transfer-user-accout-privileges.md"> Transfer user account privileges</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Login as this user</span> </td> 
   <td colname="col2"> <p>Allows admins to impersonate and log in as a non-admin account. Admin accounts cannot be impersonated. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->