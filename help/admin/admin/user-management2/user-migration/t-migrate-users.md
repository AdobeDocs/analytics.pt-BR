---
description: Migre usuários do sistema de gerenciamento de usuário herdado do Analytics para o Admin Console.
title: Migrar contas de usuário do Analytics para Adobe IDs
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 99%

---

# Migrar contas de usuário do Analytics para Adobe IDs

Migre usuários do sistema de gerenciamento de usuário herdado do Analytics para o Admin Console.

>[!NOTE]
>
>Se um Administrador que não tenha feito logon por meio da Experience Cloud tentar acessar a ferramenta de Migração de IDs de usuários, ele será redirecionado para a página de logon da Experience Cloud.

1. Navegue até **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Migração de ID de usuário]**.

   ![](/help/admin/admin/user-management2/user-migration/assets/migration-progress.png)

   A página de Migração da ID do usuário tem duas seções: *Processo de migração* e *Informações do usuário*.

## Andamento da migração

<table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Fase </th> 
      <th colname="col2" class="entry"> Descrição </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Migrações concluídas </p> </td> 
      <td colname="col2"> <p>Os usuários aceitaram o convite. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Logon herdado desabilitado </p> </td> 
      <td colname="col2"> <p>O logon antigo que usa uma ID da empresa está desativado. Os usuários passarão a acessar a Experience Cloud usando uma Adobe ID ou uma Enterprise ID. Quando todos os usuários atingirem essa fase, você terá concluído a migração. </p> <p>Na migração, o logon antigo é desativado. Os usuários são redirecionados para <span class="filepath"> experiencecloud.adobe.com</span> e devem fazer logon usando a Adobe ID ou Enterprise ID. </p> </td> 
   </tr> 
   </tbody> 
   </table>

## Informações do usuário

As informações do usuário descrevem os usuários em sua organização, separados por nome de domínio.

<table id="table_3822E27AF81E4A188562FEB5131548A5"> 
<thead> 
<tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
</tr>
</thead>
<tbody> 
<tr> 
   <td colname="col1"> <p>Domínio </p> </td> 
   <td colname="col2"> <p>Os domínios são específicos das IDs de email da base de usuários atual do Analytics. Um domínio pode ser reivindicado apenas por uma única organização, e somente os administradores de sistema podem reivindicar um domínio. Para obter mais informações, consulte <a href="https://helpx.adobe.com/br/enterprise/help/request-access-to-claimed-domain.html">Solicitar acesso a um domínio reivindicado</a>. </p> </td> 
</tr> 
<tr> 
   <td colname="col1"> <p>Domínio reivindicado </p> </td> 
   <td colname="col2"> <p>Caso deseje migrar os usuários como Enterprise ou Federated IDs, você deve ser um Administrador do sistema e reivindicar um domínio disponível pelo Adobe Admin Console antes de migrar os usuários. Saiba mais <a href="https://helpx.adobe.com/br/enterprise/help/identity.html">aqui</a>. </p> <p>Se você não deseja reivindicar domínios para Enterprise or Federated IDs, ignore este passo e migre os usuários como Adobe IDs. Saiba mais sobre os tipos de IDs <a href="https://helpx.adobe.com/br/enterprise/help/identity.html">aqui</a>. </p> </td> 
</tr> 
</tbody> 
</table>

1. Localize o domínio que contém as IDs de usuário que você deseja migrar e, em **[!UICONTROL Migração obrigatória]**, clique em **[!UICONTROL Selecionar usuários]**.
1. Na página [!DNL Users], selecione os usuários que deseja migrar e clique em **[!UICONTROL Migrar]**.

   Ao clicar em **[!UICONTROL Migrar]**, os usuários recebem um convite (Migração iniciada) e devem aceitá-lo. Essa ação mova a ID do usuário para Migração concluída. É possível desativar o acesso herdado para `[!DNL my.omniture.com].`

   ![](/help/admin/admin/user-management2/user-migration/assets/user-info.png)

1. Especifique o tipo de ID para a qual você deseja migrar a (Adobe ID ou Enterprise ID) dos usuários

   Depois de migrar os usuários, o status na coluna Status da migração muda de *`Not Initiated`* para *`Migrated`*.

   Se *`Failed`* for exibido, passe o cursor sobre o ícone para obter uma descrição sobre por que a migração falhou.
