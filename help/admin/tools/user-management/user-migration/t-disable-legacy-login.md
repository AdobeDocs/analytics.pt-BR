---
description: Saiba como desativar logons herdados para usuários do Analytics.
title: Desabilitar logons herdados
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
TQID: https://experienceleague.adobe.com/xwLXKuaeoKB5-TSVC7FLQXdUsBEeOg-zuITMa8Z3OIo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 52%

---

# Desabilitar logons herdados

Saiba como desativar logons herdados para usuários do Analytics.

Depois que os usuários migrarem do sistema de gerenciamento de usuários herdado do Analytics para o Adobe Admin Console, você poderá desativar os logons herdados. A desativação de logons herdados redireciona os usuários para o login do CX Enterprise se eles tentarem usar o login herdado.

1. Abra a ferramenta de Migração em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Migração de ID de usuário]**.
1. Na seção [!DNL User Information], localize o domínio que contém os usuários com os quais deseja trabalhar e clique em **[!UICONTROL Selecionar usuários]**.
1. Selecione os usuários com logons antigos que deseja desativar.

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

   Os usuários elegíveis terão um status de *`Migrated`* na coluna Status de migração. Não será possível desabilitar o logon antigo de um usuário até que ele tenha sido migrado.
1. Clique em **[!UICONTROL Desabilitar logon herdado]** e em **[!UICONTROL Concluído]**.

   Desativar o login herdado indica quais dos seus usuários podem continuar usando o nome de usuário e a senha herdada de [!DNL my.omniture.com].

   Não é possível desabilitar logons herdados para um usuário que ainda não foi migrado. Depois de desativado, o usuário deve usar a Experience Cloud ID para fazer logon e acessar o Analytics.
