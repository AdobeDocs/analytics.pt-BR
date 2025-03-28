---
description: Lista as APIs afetadas pela migração de usuários
title: APIs afetadas pela migração de usuários
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
source-git-commit: b90356050a6ff39e1688a10f6aa0af284284e2a6
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# APIs afetadas pela migração de usuários{#apis-affected-by-the-migration}

A Adobe está migrando todas as empresas de login do Analytics do [!DNL my.omniture.com] para a autenticação pela Adobe Experience Cloud. Depois que uma empresa inicia a migração, a criação de usuários programática e o gerenciamento pelas permissões específicas do Analytics e os métodos `GetLoginKey` disponíveis pela v1.3 e v1.4 da API de administração do Analytics não serão mais suportadas. Essas ações serão habilitadas na Experience Cloud pelo [!DNL adobe.io].

## Métodos de API afetados {#methods}

Os métodos de API a seguir na v1.3 e v1.4 da API de administrador não serão mais suportados depois de iniciar a migração do usuário:

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## Ações possíveis {#actions}

Se a empresa usa esses métodos, procure uma notificação pré-migração a partir de 31 de março de 2018. A notificação será enviada pelo menos 30 dias antes da empresa iniciar a migração para a autenticação pela Experience Cloud e, durante esse período, esses métodos não serão mais suportados.

Se a empresa não usar esses métodos, nenhuma ação é necessária, exceto garantir que eles não serão usados.

Para obter mais informações:

* [Informações gerais de gerenciamento de usuário](https://helpx.adobe.com/br/enterprise/help/users.html)
* [Fórum de API de gerenciamento de usuário](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migração do acesso do usuário do Analytics e gerenciamento para a Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=pt-BR)
