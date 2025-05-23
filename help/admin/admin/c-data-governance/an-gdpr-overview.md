---
description: Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão do GDPR para titulares de dados.
title: Adobe Analytics e o GDPR
feature: Data Governance
role: Admin
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: ht
source-wordcount: '580'
ht-degree: 100%

---

# Adobe Analytics e o GDPR

Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão do GDPR para titulares de dados.

## Visão geral da Adobe {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>O conteúdo deste documento não é um aconselhamento jurídico e não se destina a substituir tal aconselhamento. Consulte o departamento jurídico da sua empresa para obter aconselhamento a respeito do GDPR.

Em 25 de maio de 2018, o Regulamento Geral sobre a Proteção de Dados (GDPR) da União Europeia entrou em vigor. Para obter mais informações sobre a resposta da Adobe e o que isso significa para você como cliente da Adobe, consulte [GDPR e a sua empresa.](https://www.adobe.com/br/privacy/general-data-protection-regulation.html)

Quando a Adobe fornece software e serviços a uma empresa, ela atua como um processador de dados para os dados pessoais que recebe e armazena em nome dos clientes como parte da prestação dos serviços. Como Processador de dados, a Adobe processa dados pessoais de acordo com a permissão e as instruções de sua empresa (por exemplo, como definido em seu contrato com a Adobe).

Como o controlador de dados, você determinará os dados pessoais que a Adobe processa e armazena em seu nome. Se você usa as soluções da Adobe Experience Cloud, a Adobe pode hospedar dados pessoais, dependendo das soluções usadas e das informações que você escolher enviar para a sua conta da Adobe Experience Cloud. Para obter uma lista de exemplos, consulte [Privacidade na Adobe Experience Cloud.](https://www.adobe.com/br/privacy/experience-cloud.html#collect)

![](assets/privacy_ready.png)

## Como a Adobe lida com dados do GDPR {#section_A20BCC08A80B410D97601BFB1CAF83F1}

A Adobe Experience Platform fornece uma solução integrada que conecta a infraestrutura de governança de dados da sua marca às ferramentas da Adobe usadas para criar e gerenciar as experiências do consumidor. Os recursos de governança de dados da Adobe Experience Cloud permitem uma vinculação direta da política de governança de dados ao uso dos dados.

Familiarize-se com a maneira [como o Adobe Analytics lida com o GDPR](https://www.adobe.com/br/data-analytics-cloud/analytics/general-data-protection-regulation.html), que apresenta as etapas de preparação para GDPR e como fazer a integração com a API do GDPR da Adobe Experience Cloud.

## Preparação para o GDPR e dados do Adobe Analytics {#section_9A47CDCD614C42238F6E05CFF0180195}

A Adobe sabe que você está mais familiarizado com os dados personalizados nos seus conjuntos de relatórios e oferecemos a oportunidade de definir suas preferências e configurações de governança de dados.

Para isso, o Adobe Analytics fornece uma interface de Governança de dados que permite a você, como controlador de dados, definir [rótulos de privacidade](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels) em seus conjuntos de relatórios do Analytics e em todas as dimensões e métricas desses conjuntos de relatórios. É possível identificar as colunas em seu conjunto de dados que contêm os dados direta ou indiretamente identificáveis para que você possa enviar suas solicitações de acesso e de exclusão para tratar esses dados. Para cada solicitação, os rótulos definidos na interface do usuário de Governança de dados do Analytics serão aplicados para o identificador específico que corresponde a essa solicitação.

Consulte [Rotular dados do conjunto de relatórios](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md) para mais informações sobre como definir os rótulos.

## Pré-requisitos {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Familiarizar-se com a [terminologia do GDPR.](/help/admin/c-data-governance/gdpr-terminology.md)
* Vincular sua empresa de logon a uma organização da Experience Cloud, se ainda não estiver vinculada. Entrar em contato com o Atendimento ao cliente da Adobe e consultar [Vinculação de organizações e contas.](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=pt-BR)
* Definir uma política de retenção de dados para cada conjunto de relatórios para que as solicitações de exclusão e de acesso do GDPR possam ser atendidas.

  >[!NOTE]
  >
  >O Adobe Analytics não pode ajudá-lo com o processamento de solicitações para a API do GDPR, ou seja, com o processamento de solicitações de acesso ou de exclusão recebidas dos usuários finais, se um período de retenção de dados não tiver sido definido no Adobe Analytics. Entre em contato com a equipe de contas da Adobe para definir o período de retenção de dados.

* Verifique as suas permissões: para usar a interface de gerenciamento de governança de dados no Adobe Analytics, você precisa ser um administrador do Adobe Analytics.

