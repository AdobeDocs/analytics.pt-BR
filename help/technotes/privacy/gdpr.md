---
description: Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e exclusão de GDPR dos titulares de dados.
title: Adobe Analytics e o RGPD
feature: Data Governance
role: Admin
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
TQID: 'https://experienceleague.adobe.com/G-3emGJR0FMicoTI8WUlWdM3SSoWjGb7sr6lxqceBdg'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 55%

---

# Adobe Analytics e o RGPD

Este documento descreve o que precisa ser feito no Adobe Analytics para oferecer suporte aos direitos de acesso e exclusão de GDPR dos titulares de dados.

>[!IMPORTANT]
>
>O conteúdo deste documento não é um aconselhamento jurídico e não se destina a substituir tal aconselhamento. Consulte o departamento jurídico da sua empresa para obter aconselhamento a respeito do RGPD.

Em 25 de maio de 2018, o Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia entrou em vigor. Para obter mais informações sobre a resposta da Adobe e o que isso significa para você como cliente da Adobe, consulte [RGPD e a sua empresa.](https://www.adobe.com/br/privacy/general-data-protection-regulation.html)

Quando a Adobe fornece software e serviços a uma empresa, ela atua como um processador de dados para os dados pessoais que recebe e armazena em nome dos clientes como parte da prestação dos serviços. Como Processador de dados, a Adobe processa dados pessoais de acordo com a permissão e as instruções de sua empresa (por exemplo, como definido em seu contrato com a Adobe).

Como o controlador de dados, você determinará os dados pessoais que a Adobe processa e armazena em seu nome. Se você usa as soluções Adobe CX Enterprise, a Adobe pode hospedar dados pessoais, dependendo das soluções usadas e das informações que você escolher enviar para a sua conta Adobe CX Enterprise. Para obter uma lista de exemplos, consulte [privacidade corporativa do Adobe CX.](https://www.adobe.com/br/privacy/experience-cloud.html#collect)

![](assets/privacy_ready.png)

## Como a Adobe lida com dados do RGPD

O Adobe CX Enterprise fornece uma solução integrada que conecta a infraestrutura de governança de dados da sua marca com as ferramentas da Adobe que ela usa para criar e gerenciar as experiências do consumidor. Os recursos de controle de dados do Adobe CX Enterprise permitem uma vinculação direta da política de controle de dados ao uso de dados.

Familiarize-se com a [maneira como o Adobe Analytics lida com o GDPR](https://www.adobe.com/br/data-analytics-cloud/analytics/general-data-protection-regulation.html), que apresenta as etapas de preparação do GDPR e como fazer a integração com a API do GDPR corporativo do Adobe CX.

## Preparação para o RGPD e dados do Adobe Analytics

A Adobe sabe que você está mais familiarizado com os dados personalizados nos seus conjuntos de relatórios e oferecemos a oportunidade de definir suas preferências e configurações de governança de dados.

Para isso, o Adobe Analytics fornece uma interface de Governança de dados que permite a você, como controlador de dados, definir [rótulos de privacidade](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) em seus conjuntos de relatórios do Analytics e em todas as dimensões e métricas desses conjuntos de relatórios. Você pode identificar as colunas do conjunto de dados que contêm dados direta ou indiretamente identificáveis para poder enviar o acesso e excluir solicitações para lidar com esses dados. Para cada solicitação, os rótulos definidos na interface do usuário da Governança de dados do Analytics serão honrados para o identificador específico que corresponde a essa solicitação.

Consulte [Rotular dados do conjunto de relatórios](/help/admin/tools/privacy-labeling/labeling-overview.md) para mais informações sobre como definir os rótulos.
