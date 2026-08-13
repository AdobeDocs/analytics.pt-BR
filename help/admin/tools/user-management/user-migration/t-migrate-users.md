---
description: Migre usuários do sistema de gerenciamento de usuário herdado do Analytics para o Admin Console.
title: Migrar contas de usuário do Analytics para Adobe IDs
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
TQID: https://experienceleague.adobe.com/bD-qiEI3KbDBNe4aO01-MqzjoZ-OMcGAnd9vnMTBmZs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 405
ht-degree: 72%

---

# Migrar contas de usuário do Analytics para Adobe IDs

Migre usuários do sistema de gerenciamento de usuário herdado do Analytics para o Admin Console.

>[!NOTE]
>
>Se um Administrador que não tenha feito logon no CX Enterprise tentar acessar a ferramenta de Migração de IDs de usuários, ele será redirecionado para a página de logon do CX Enterprise.

1. Navegue até **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Migração de ID de usuário]**.

   ![](/help/admin/tools/user-management/user-migration/assets/migration-progress.png)

   A página Migração de IDs de Usuários tem duas seções: *Progresso da Migração* e *Informações do Usuário*.

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
      <td colname="col1"> <p>Logon herdado desativado </p> </td> 
      <td colname="col2"> <p>O logon antigo usando uma ID de empresa está desativado. Os usuários agora acessam o CX Enterprise usando sua Adobe ID ou Enterprise ID. Quando todos os usuários tiverem atingido essa fase, você terá concluído a migração. </p> <p>Na migração, o logon antigo é desativado. Os usuários são redirecionados para <span class="filepath"> experiencecloud.adobe.com</span> e devem fazer logon usando a Adobe ID ou Enterprise ID. </p> </td> 
   </tr> 
   </tbody> 
   </table>

## Informações do usuário

As Informações do usuário descrevem os usuários em sua organização, separados por nome de domínio.

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
   <td colname="col2"> <p>Os domínios são específicos às IDs de email da base de usuários atual do Analytics. Um domínio pode ser reivindicado apenas por uma única organização, e somente os administradores de sistema podem reivindicar um domínio. Para obter mais informações, consulte <a href="https://helpx.adobe.com/br/enterprise/help/request-access-to-claimed-domain.html">Solicitar acesso a um domínio reivindicado</a>. </p> </td> 
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

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

1. Especifique o tipo de ID para a qual você deseja migrar a (Adobe ID ou Enterprise ID) dos usuários

   Depois de migrar os usuários, o status na coluna Status da migração muda de *`Not Initiated`* para *`Migrated`*.

   Se *`Failed`* for exibido, passe o mouse sobre o ícone para obter uma descrição sobre por que a migração falhou.
