---
description: Etapas que descrevem como os administradores podem ativar o acesso aos relatórios do Data Warehouse para um grupo de usuários.
seo-description: Etapas que descrevem como os administradores podem ativar o acesso aos relatórios do Data Warehouse para um grupo de usuários.
seo-title: Adicionar grupo de usuários do Data Warehouse
solution: Analytics
title: Adicionar grupo de usuários do Data Warehouse
topic: Data Warehouse
uuid: d 89294 db-caa 3-4044-b 70 d -65 b 512 b 0 dc 1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Adicionar grupo de usuários do Data Warehouse

Etapas que descrevem como os administradores podem ativar o acesso aos relatórios do Data Warehouse para um grupo de usuários.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Fornecer as seguintes informações do grupo:

   Por exemplo, `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. Na seção **Acesso ao report suite**, selecione os report suites aos quais você deseja que os membros do grupo tenham acesso.
1. Em [!UICONTROL Ferramentas]**, ative[!UICONTROL Todas as ferramentas]**.

   Como opção, clique em **[!UICONTROL Personalizar]** e ative **[!UICONTROL Personalizar o relatório do Data Warehouse]**.

1. Em [!UICONTROL Atribuir logons de usuário], adicionar os logons de usuário desejados.
1. Click **[!UICONTROL Save Group]**.

   Na próxima vez em que os usuários adicionarem a esse logon de grupo, será possível visualizar a opção de Data Warehouse adicionada ao menu de [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >No caso de permissões conflitantes (como um usuário atribuído a dois grupos, um dos quais nega acesso a um recurso e o outro concede o mesmo acesso), o sistema restringe a permissão. Os usuários que pertencem a grupos que negam acesso ao data warehouse podem ter de ser removidos de tais grupos.

>[!MORE_LIKE_THIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

