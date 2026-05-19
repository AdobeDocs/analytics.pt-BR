---
description: Lista as APIs afetadas pela migração de usuários
title: APIs afetadas pela migração de usuários
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 32%

---

# APIs afetadas pela migração de usuários{#apis-affected-by-the-migration}

A Adobe está migrando todas as empresas de logon do Analytics do [!DNL my.omniture.com] para a autenticação via Adobe CX Enterprise. Depois que uma empresa inicia a migração, a criação de usuários programática e o gerenciamento pelas permissões específicas do Analytics e os métodos `GetLoginKey` disponíveis pela v1.3 e v1.4 da API de administração do Analytics não serão mais suportadas. Essas ações serão habilitadas na CX Enterprise via `adobe.io`.

## Métodos de API afetados {#methods}

Os seguintes métodos de API nas v1.3 e v1.4 da API de administração não serão mais compatíveis depois que você iniciar a migração do usuário:

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

Se sua empresa usa esses métodos no momento, procure uma notificação de pré-migração a partir de 31 de março de 2018. A notificação será enviada pelo menos 30 dias antes de sua empresa iniciar a migração para a autenticação do CX Enterprise e, nesse momento, esses métodos não serão mais compatíveis.

Se a empresa não usar nenhum desses métodos, nenhuma ação será necessária, a não ser garantir que você não comece a usar esses métodos.

Para obter informações adicionais:

* [Informações gerais de gerenciamento de usuários](https://helpx.adobe.com/br/enterprise/help/users.html)
* [Fórum da API de gerenciamento de usuários](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migração de acesso e gerenciamento de usuários do Analytics para o CX Enterprise](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
