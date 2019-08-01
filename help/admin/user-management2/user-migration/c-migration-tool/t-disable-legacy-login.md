---
description: Saiba como desabilitar os logins herdados para usuários do Analytics.
seo-description: Saiba como desabilitar os logins herdados para usuários do Analytics.
seo-title: Desabilitar logons herdados
title: Desabilitar logons herdados
uuid: 085874 b 2-10 bf -4 a 56-a 337-f 3104428 d 71 e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# Desabilitar logons herdados{#disable-legacy-logins}

Saiba como desabilitar os logins herdados para usuários do Analytics.

Depois que seus usuários migrarem do antigo sistema de gerenciamento de usuários do Analytics para o Adobe Admin Console, você poderá desabilitar seus logons antigos. A desativação de logins herdados redireciona os usuários para o login da Experience Cloud se eles tentarem usar o login herdado.

1. Open the Migration tool in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User ID Migration]**.
1. In the [!DNL User Information] section, locate the domain containing the users you want to work with, then click **[!UICONTROL Select Users]**.
1. Selecione os usuários com logons antigos que deseja desativar.

   ![](assets/user-info.png)

   The users that are eligible will have a status of *`Migrated`* under the Migration Status column. Não será possível desabilitar o logon antigo de um usuário até que ele tenha sido migrado.
1. Click **[!UICONTROL Disable Legacy Login]**, then click **[!UICONTROL Done]**.

   Desativar o login herdado indica quais dos seus usuários podem continuar usando o nome de usuário e a senha herdada de [!DNL my.omniture.com].

   Você não pode desativar logins herdados de um usuário que ainda deve ser migrado. Depois de desativado, o usuário deve usar a Experience Cloud ID para fazer login e acessar o Analytics.

