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

1. Clique em **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Gerenciamento de usuários]**.
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Fornecer as seguintes informações do grupo:

   Por exemplo, `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. Na seção **Acesso ao report suite**, selecione os report suites aos quais você deseja que os membros do grupo tenham acesso.
1. Em [!UICONTROL Ferramentas]**, ative[!UICONTROL Todas as ferramentas]**.

   Como opção, clique em **[!UICONTROL Personalizar]** e ative **[!UICONTROL Personalizar o relatório do Data Warehouse]**.

1. Em [!UICONTROL Atribuir logons de usuário], adicionar os logons de usuário desejados.
1. Clique em **[!UICONTROL Salvar grupo]**.

   Na próxima vez em que os usuários adicionarem a esse logon de grupo, será possível visualizar a opção de Data Warehouse adicionada ao menu de [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >Em caso de permissões conflitantes (como um usuário atribuído a dois grupos, um dos quais nega acesso a um recurso e o outro concede o mesmo acesso), o sistema restringe a permissão. Os usuários que pertencem a grupos que negam acesso ao data warehouse podem ter de ser removidos de tais grupos.

>[!MORELIKETHIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

