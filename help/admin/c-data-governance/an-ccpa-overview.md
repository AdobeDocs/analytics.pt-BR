---
description: Este documento descreve o que você precisa fazer no Adobe Analytics para oferecer suporte ao acesso CCPA e aos direitos de exclusão das pessoas em questão.
seo-description: Este documento descreve o que você precisa fazer no Adobe Analytics para oferecer suporte ao acesso CCPA e aos direitos de exclusão das pessoas em questão.
seo-title: Adobe Analytics e CCPA
title: Adobe Analytics e CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# Adobe Analytics e CCPA

Este documento descreve o que você precisa fazer no Adobe Analytics para oferecer suporte ao acesso CCPA e aos direitos de exclusão das pessoas em questão.

## Visão geral da Adobe

>[!IMPORTANT] O conteúdo deste documento não é um aconselhamento jurídico e não se destina a substituir tal aconselhamento. Consulte o departamento jurídico da sua empresa para obter assistência sobre a CCPA.

Em 1º de janeiro de 2020, a lei de privacidade do consumidor da Califórnia (CCPA) entra em vigor. For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

Quando a Adobe fornece software e serviços a uma empresa, ela atua como um processador de dados para os dados pessoais que recebe e armazena em nome dos clientes como parte da prestação dos serviços. Como um processador de dados, a Adobe processa dados pessoais de acordo com as permissões e instruções de sua empresa (por exemplo, conforme estabelecido em seu contrato com a Adobe).

Como o controlador de dados, você determinará os dados pessoais que a Adobe processa e armazena em seu nome. Se você usa as soluções da Adobe Experience Cloud, a Adobe pode hospedar dados pessoais, dependendo das soluções usadas e das informações que você escolher enviar para a sua conta da Adobe Experience Cloud. Para obter uma lista de exemplos, consulte [Privacidade na Adobe Experience Cloud.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## Como a Adobe lida com dados CCPA

A Adobe Cloud Platform (ACP) fornece uma solução integrada que conecta a infraestrutura de governança de dados da sua marca às ferramentas da Adobe usadas para criar e gerenciar as experiências do consumidor. Os recursos de governança de dados da Adobe Cloud Platform permitem uma vinculação direta da política de governança de dados ao uso dos dados.

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe Experience Cloud Privacy Service API.

## Prontidão para CCPA e seus dados do Adobe Analytics

A Adobe sabe que você está mais familiarizado com os dados personalizados nos seus conjuntos de relatórios e oferecemos a oportunidade de definir suas preferências e configurações de governança de dados.
To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. É possível identificar as colunas em seu conjunto de dados que contêm os dados direta ou indiretamente identificáveis para que você possa enviar suas solicitações de acesso e de exclusão para tratar esses dados. Para cada solicitação, os rótulos definidos na interface do usuário de Governança de dados do Analytics serão aplicados para o identificador específico que corresponde a essa solicitação.

Consulte [Rotular dados do conjunto de relatórios](/help//admin/c-data-governance/gdpr-setup-reportsuite.md) para obter mais informações sobre como definir os rótulos.

## Pré-requisitos

* Familiarizar-se com a [terminologia do GDPR.](/help/admin/c-data-governance/gdpr-terminology.md)
* Vincular sua empresa de logon a uma organização da Experience Cloud, se ainda não estiver vinculada. Entrar em contato com o Atendimento ao cliente da Adobe e consultar [Vinculação de organizações e contas.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Mapear qualquer conjunto de relatórios do Adobe Analytics que deseje configurar para governança de dados para a [sua organização da Experience Cloud.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* Defina uma política de retenção de dados para cada conjunto de relatórios para que as solicitações de exclusão e acesso CCPA possam ser atendidas.

   O Adobe Analytics não pode ajudá-lo com solicitações de processamento para a API de Serviços de Privacidade, isto é, solicitações de acesso ou exclusão que você recebe de seus usuários finais, se o período de retenção de dados não tiver sido definido no Adobe Analytics. Entre em contato com o gerente de sucesso do cliente para definir o período de retenção de dados.

* Verifique suas permissões: para usar a interface de Gerenciamento de governança de dados no Adobe Analytics, você deve ser um administrador do Adobe Analytics.
* Considere implementar as Variáveis [de Gerenciamento de](/help/admin/c-data-governance/consent-variables.md) Consentimento para rastrear o status de consentimento em um nível de ocorrência.
