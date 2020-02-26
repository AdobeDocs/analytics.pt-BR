---
description: 'null'
title: APIs afetadas pela migração
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
translation-type: ht
source-git-commit: 1ec080acf65c31b077a3daf3846f233f01e011b8

---


# APIs afetadas pela migração {#apis-affected-by-the-migration}

## APIs afetadas pela migração {#topic-8d34296a67d74b1081c3f7e8f650f3ce}

A Adobe está migrando todas as empresas de login do Analytics do [!DNL my.omniture.com] para a autenticação pela Adobe Experience Cloud. Depois que uma empresa inicia a migração, a criação de usuários programática e o gerenciamento pelas permissões específicas do Analytics e os métodos `GetLoginKey` disponíveis pela v1.3 e v1.4 da API de administração do Analytics não serão mais suportadas. Essas ações serão habilitadas na Experience Cloud pelo [!DNL adobe.io].

## Métodos de API afetados {#section-d19051ac26cc49aeb124f767c4760254}

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

## Ações possíveis {#section-8b0b89a862614f729ebdbe092ce99027}

Se a empresa usa esses métodos, procure uma notificação pré-migração a partir de 31 de março de 2018. A notificação será enviada pelo menos 30 dias antes da empresa iniciar a migração para a autenticação pela Experience Cloud e, durante esse período, esses métodos não serão mais suportados.

Se a empresa não usar esses métodos, nenhuma ação é necessária, exceto garantir que eles não serão usados.

Para obter mais informações:

* [Informações gerais de gerenciamento de usuário](https://helpx.adobe.com/br/enterprise/help/users.html)
* [APIs de gerenciamento de usuário pelo adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [Fórum de API de gerenciamento de usuário](https://forums.adobe.com/community/umapi/overview)
* [Migração do acesso do usuário do Analytics e gerenciamento para a Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/experience-cloud/admin-console/analytics-migration/)

