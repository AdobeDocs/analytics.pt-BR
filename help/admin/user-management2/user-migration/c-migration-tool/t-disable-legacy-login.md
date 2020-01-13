---
description: Saiba como desabilitar os logins herdados para usuários do Analytics.
title: Desabilitar logons herdados
uuid: 085874b2-10bf-4a56-a337-f3104428d71e
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Desabilitar logons herdados {#disable-legacy-logins}

Saiba como desabilitar os logins herdados para usuários do Analytics.

Depois que seus usuários migrarem do antigo sistema de gerenciamento de usuários do Analytics para o Adobe Admin Console, você poderá desabilitar seus logons antigos. A desativação de logins herdados redireciona os usuários para o login da Experience Cloud se eles tentarem usar o login herdado.

1. Abra a ferramenta de Migração em **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admininstração]** &gt; **[!UICONTROL Migração de ID de usuário]**.
1. Na seção [!DNL User Information], localize o domínio que contém os usuários com os quais deseja trabalhar e clique em **[!UICONTROL Selecionar usuários]**.
1. Selecione os usuários com logons antigos que deseja desativar.

   ![](assets/user-info.png)

   Os usuários elegíveis terão um status de *`Migrated`* na coluna Status de migração. Não será possível desabilitar o logon antigo de um usuário até que ele tenha sido migrado.
1. Clique em **[!UICONTROL Desabilitar logon herdado]** e em **[!UICONTROL Concluído]**.

   Desativar o login herdado indica quais dos seus usuários podem continuar usando o nome de usuário e a senha herdada de [!DNL my.omniture.com].

   Você não pode desativar logins herdados de um usuário que ainda deve ser migrado. Depois de desativado, o usuário deve usar a Experience Cloud ID para fazer login e acessar o Analytics.

