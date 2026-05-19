---
description: Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão da CCPA para titulares de dados.
title: Adobe Analytics e a CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
TQID: https://experienceleague.adobe.com/medgbA9EBG0fE2xttZ7HLKT42-RBr7rlMGGGGrAyoKw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 63%

---

# Adobe Analytics e a CCPA

Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão da CCPA para titulares de dados.

## Visão geral da Adobe

>[!IMPORTANT]
>
>O conteúdo deste documento não é um aconselhamento jurídico e não se destina a substituir tal aconselhamento. Consulte o departamento jurídico da sua empresa para obter aconselhamento a respeito da CCPA.

Em 1º de janeiro de 2020, a lei de Privacidade do consumidor da Califórnia (CCPA) entra em vigor. Para obter mais informações sobre a resposta da Adobe e o que isso significa para você como cliente da Adobe, consulte [Centro de privacidade da Adobe.](https://www.adobe.com/br/privacy.html)

Quando a Adobe fornece software e serviços a uma empresa, ela atua como um processador de dados para os dados pessoais que recebe e armazena em nome dos clientes como parte da prestação dos serviços. Como Processador de dados, a Adobe processa dados pessoais de acordo com a permissão e as instruções de sua empresa (por exemplo, como definido em seu contrato com a Adobe).

Como o controlador de dados, você determinará os dados pessoais que a Adobe processa e armazena em seu nome. Se você usa as soluções Adobe CX Enterprise, a Adobe pode hospedar dados pessoais, dependendo das soluções usadas e das informações que você escolher enviar para a sua conta Adobe CX Enterprise. Para obter uma lista de exemplos, consulte [privacidade corporativa do Adobe CX.](https://www.adobe.com/br/privacy/experience-cloud.html#collect)

## Como a Adobe lida com dados da CCPA

O Adobe CX Enterprise fornece uma solução integrada que conecta a infraestrutura de governança de dados da sua marca com as ferramentas da Adobe que ela usa para criar e gerenciar as experiências do consumidor. Os recursos de controle de dados do Adobe CX Enterprise permitem uma vinculação direta da política de controle de dados ao uso de dados.

Familiarize-se com a [maneira como o Adobe Analytics lida com o GDPR](https://www.adobe.com/br/data-analytics-cloud/analytics/general-data-protection-regulation.html), que apresenta as etapas de preparação da privacidade e como fazer a integração com a API do Adobe CX Enterprise Privacy Service.

## Preparação para a CCPA e dados do Adobe Analytics

A Adobe sabe que você está mais familiarizado com os dados personalizados nos seus conjuntos de relatórios e oferecemos a oportunidade de definir suas preferências e configurações de governança de dados.
Para isso, o Adobe Analytics fornece uma interface de Governança de dados que permite a você, como controlador de dados, definir [rótulos de privacidade](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) em seus conjuntos de relatórios do Analytics e em todas as dimensões e métricas desses conjuntos de relatórios. Você pode identificar as colunas do conjunto de dados que contêm dados direta ou indiretamente identificáveis para poder enviar o acesso e excluir solicitações para lidar com esses dados. Para cada solicitação, os rótulos definidos na interface do usuário da Governança de dados do Analytics serão honrados para o identificador específico que corresponde a essa solicitação.

Consulte [Rotular dados do conjunto de relatórios](/help/admin/tools/privacy-labeling/labeling-overview.md) para mais informações sobre como definir os rótulos.
