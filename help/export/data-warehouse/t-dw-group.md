---
description: Etapas que descrevem como os administradores podem ativar o acesso aos relatórios do Data Warehouse para um grupo de usuários.
title: Adicionar grupo de usuários do Data Warehouse
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Adicionar grupo de usuários do Data Warehouse

Etapas que descrevem como os administradores podem ativar o acesso aos relatórios do Data Warehouse para um grupo de usuários.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Clique em **[!UICONTROL Edit Groups]**.
1. Clique em **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Fornecer as seguintes informações do grupo:

   Por exemplo, `Data Warehouse Access`.
1. Digite uma descrição no **[!UICONTROL Group Description]** campo.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. Em [!UICONTROL Tools], ative **[!UICONTROL All Tools]**.

   Como alternativa, clique em **[!UICONTROL Customize]**, em seguida, ative **[!UICONTROL Custom Data Warehouse Report]**.

1. Em [!UICONTROL Assign User Logins], adicione os logons de usuário desejados.
1. Clique em **[!UICONTROL Save Group]**.

   Na próxima vez em que os usuários adicionarem a esse logon de grupo, será possível visualizar a opção de Data Warehouse adicionada ao menu de [!UICONTROL Reports & Analytics].

   >[!NOTE]
   >
   >No caso de permissões em conflito (como um usuário atribuído a dois grupos, um dos quais nega acesso a um recurso e o outro concede o mesmo acesso), o sistema restringe a permissão. Os usuários que pertencem a grupos que negam acesso ao data warehouse podem ter de ser removidos de tais grupos.

>[!MORELIKETHIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

