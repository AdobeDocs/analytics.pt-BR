---
description: Lista as APIs afetadas pela migração de usuários
title: APIs afetadas pela migração de usuários
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 95%

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
* [Migração do acesso e gerenciamento de usuários do Analytics para o Experience Cloud](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
