---
description: Etapas que descrevem como os administradores podem ativar o acesso aos relatórios do Data Warehouse para um grupo de usuários.
title: Adicionar grupo de usuários do Data Warehouse
feature: Data Warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
exl-id: 8737ab60-2ad1-4795-808b-d0200078a333
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 100%

---

# Adicionar grupo de usuários do Data Warehouse

Etapas que descrevem como os administradores podem ativar o acesso aos relatórios do Data Warehouse para um grupo de usuários.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Gerenciamento de usuários]**.
1. Clique em **[!UICONTROL Editar grupos]**.
1. Clique em **[!UICONTROL Adicionar novo grupo de usuários]**.
1. Na seção **[!UICONTROL Definir grupo de usuários]**, digite um nome no campo Nome do grupo. Fornecer as seguintes informações do grupo:

   Por exemplo, `Data Warehouse Access`.
1. Digite uma descrição no campo **[!UICONTROL Descrição do grupo.]**
1. Na seção **[!UICONTROL Acesso ao conjunto de relatórios]**, selecione os conjuntos de relatórios aos quais você deseja que os membros do grupo tenham acesso.
1. Em [!UICONTROL Ferramentas], ative **[!UICONTROL Todas as ferramentas]**.

   Como opção, clique em **[!UICONTROL Personalizar]** e ative **[!UICONTROL Personalizar o relatório do Data Warehouse]**.

1. Em [!UICONTROL Atribuir logons de usuário], adicionar os logons de usuário desejados.
1. Clique em **[!UICONTROL Salvar grupo]**.

   Na próxima vez em que os usuários adicionarem a esse logon de grupo, será possível visualizar a opção de Data Warehouse adicionada ao menu de [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >No caso de permissões em conflito (como um usuário atribuído a dois grupos, um dos quais nega acesso a um recurso e o outro concede o mesmo acesso), o sistema restringe a permissão. Os usuários que pertencem a grupos que negam acesso ao data warehouse podem ter de ser removidos de tais grupos.

>[!MORELIKETHIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

