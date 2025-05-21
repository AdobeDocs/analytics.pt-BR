---
description: Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão da CCPA para titulares de dados.
title: Adobe Analytics e a CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: ht
source-wordcount: '593'
ht-degree: 100%

---

# Adobe Analytics e a CCPA

Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão da CCPA para titulares de dados.

## Visão geral da Adobe

>[!IMPORTANT]
>
>O conteúdo deste documento não é um aconselhamento jurídico e não se destina a substituir tal aconselhamento. Consulte o departamento jurídico da sua empresa para obter aconselhamento a respeito da CCPA.

Em 1º de janeiro de 2020, a lei de Privacidade do consumidor da Califórnia (CCPA) entra em vigor. Para obter mais informações sobre a resposta da Adobe e o que isso significa para você como cliente da Adobe, consulte [Centro de privacidade da Adobe.](https://www.adobe.com/br/privacy.html)

Quando a Adobe fornece software e serviços a uma empresa, ela atua como um processador de dados para os dados pessoais que recebe e armazena em nome dos clientes como parte da prestação dos serviços. Como Processador de dados, a Adobe processa dados pessoais de acordo com a permissão e as instruções de sua empresa (por exemplo, como definido em seu contrato com a Adobe).

Como o controlador de dados, você determinará os dados pessoais que a Adobe processa e armazena em seu nome. Se você usa as soluções da Adobe Experience Cloud, a Adobe pode hospedar dados pessoais, dependendo das soluções usadas e das informações que você escolher enviar para a sua conta da Adobe Experience Cloud. Para obter uma lista de exemplos, consulte [Privacidade na Adobe Experience Cloud.](https://www.adobe.com/br/privacy/experience-cloud.html#collect)

## Como a Adobe lida com dados da CCPA

A Adobe Experience Platform fornece uma solução integrada que conecta a infraestrutura de governança de dados da sua marca às ferramentas da Adobe usadas para criar e gerenciar as experiências do consumidor. Os recursos de governança de dados da Adobe Experience Cloud permitem uma vinculação direta da política de governança de dados ao uso dos dados.

Familiarize-se com a maneira [como o Adobe Analytics lida com o GDPR](https://www.adobe.com/br/data-analytics-cloud/analytics/general-data-protection-regulation.html), que apresenta as etapas de preparação da privacidade e como fazer a integração com a API do Serviço de privacidade da Adobe Experience Cloud.

## Preparação para a CCPA e dados do Adobe Analytics

A Adobe sabe que você está mais familiarizado com os dados personalizados nos seus conjuntos de relatórios e oferecemos a oportunidade de definir suas preferências e configurações de governança de dados.
Para isso, o Adobe Analytics fornece uma interface de Governança de dados que permite a você, como controlador de dados, definir [rótulos de privacidade](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels) em seus conjuntos de relatórios do Analytics e em todas as dimensões e métricas desses conjuntos de relatórios. É possível identificar as colunas em seu conjunto de dados que contêm os dados direta ou indiretamente identificáveis para que você possa enviar suas solicitações de acesso e de exclusão para tratar esses dados. Para cada solicitação, os rótulos definidos na interface do usuário de Governança de dados do Analytics serão aplicados para o identificador específico que corresponde a essa solicitação.

Consulte [Rotular dados do conjunto de relatórios](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md) para mais informações sobre como definir os rótulos.

## Pré-requisitos

* Familiarizar-se com a [terminologia do GDPR.](/help/admin/c-data-governance/gdpr-terminology.md)
* Vincular sua empresa de logon a uma organização da Experience Cloud, se ainda não estiver vinculada. Entrar em contato com o Atendimento ao cliente da Adobe e consultar [Vinculação de organizações e contas.](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=pt-BR)
* Defina uma política de retenção de dados para cada conjunto de relatórios para que as solicitações de exclusão e de acesso da CCPA possam ser atendidas.

  O Adobe Analytics não pode ajudá-lo com o processamento de solicitações para a API da Privacidade de dados, ou seja, com o processamento de solicitações de acesso ou de exclusão recebidas dos usuários finais, se um período de retenção de dados não tiver sido definido no Adobe Analytics. Entre em contato com a equipe de contas da Adobe para definir o período de retenção de dados.

* Verifique as suas permissões: para usar a interface de gerenciamento de governança de dados no Adobe Analytics, você precisa ser um administrador do Adobe Analytics.
* Considere implementar as [Variáveis de gerenciamento de consentimento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) para rastrear o status de consentimento em um nível de ocorrência.
