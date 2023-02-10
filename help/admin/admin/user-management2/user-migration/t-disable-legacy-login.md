---
description: Saiba como desabilitar os logins herdados para usuários do Analytics.
title: Desabilitar logons herdados
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
source-git-commit: d78489cd87b59e4dda40d9975e1ce643507f2f69
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 100%

---

# Desabilitar logons herdados{#disable-legacy-logins}

Saiba como desabilitar os logins herdados para usuários do Analytics.

Depois que seus usuários migrarem do antigo sistema de gerenciamento de usuários do Analytics para o Adobe Admin Console, você poderá desabilitar seus logons antigos. A desativação de logins herdados redireciona os usuários para o login da Experience Cloud se eles tentarem usar o login herdado.

1. Abra a ferramenta de Migração em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Migração de ID de usuário]**.
1. Na seção [!DNL User Information], localize o domínio que contém os usuários com os quais deseja trabalhar e clique em **[!UICONTROL Selecionar usuários]**.
1. Selecione os usuários com logons antigos que deseja desativar.

   ![](/help/admin/admin/user-management2/user-migration/assets/user-info.png)

   Os usuários elegíveis terão um status de *`Migrated`* na coluna Status de migração. Não será possível desabilitar o logon antigo de um usuário até que ele tenha sido migrado.
1. Clique em **[!UICONTROL Desabilitar logon herdado]** e em **[!UICONTROL Concluído]**.

   Desativar o login herdado indica quais dos seus usuários podem continuar usando o nome de usuário e a senha herdada de [!DNL my.omniture.com].

   Você não pode desativar logins herdados de um usuário que ainda deve ser migrado. Depois de desativado, o usuário deve usar a Experience Cloud ID para fazer login e acessar o Analytics.
