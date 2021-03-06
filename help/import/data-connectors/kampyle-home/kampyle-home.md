---
description: Use o conector de dados do Kampyle com o Adobe Analytics.
title: Conector de dados do Kampyle para Adobe Analytics
uuid: f7733c81-93f5-4c50-b83a-721a6fbd4e8e
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 93%

---


# Conector de dados do Kampyle para Adobe Analytics {#kampyle-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>A vida útil da tecnologia Adobe Data Connector será encerrada em 1 de agosto de 2021. [Saiba mais...](/help/import/data-connectors/data-connectors-eol.md)

O Conector de dados do Kampyle para Adobe Analytics combina o sistema de feedback integrado do Kampyle com os relatórios comportamentais do Adobe Analytics® para criar poderosas oportunidades de análise e otimização para sua organização.

Os profissionais de marketing online estão cada vez mais percebendo a relevância do feedback dos clientes na criação de marcas e na promoção dos resultados comerciais. O Conector de dados do Kampyle para Adobe Analytics® adiciona métricas e dimensões de feedback do visitante ao Adobe Analytics. Ele permite analisar o comportamento do visitante no contexto de suas atitudes e opiniões. Isso ajuda você a se otimizar com base em feedbacks e melhora as taxas de conversão.

## Pré-requisitos de integração {#integration-prerequisites}

Pré-requisitos a serem considerados antes de ativar o conector de dados.

### Pré-requisitos para clientes da Adobe {#section-d9c2e266931249e596de5f4406b5b6f0}

* Você deve ser um cliente atual do Adobe Analytics.
* Você deve ser um usuário administrador.
* Você deve ter uma variável eVar disponível e ativada em seu conjunto de relatórios.
* Você deve ter três eventos personalizados disponíveis e ativados em seu conjunto de relatórios (digite “contador”).

### Pré-requisitos para clientes do Kampyle {#section-4bbbca50e74d4f218414ae0cc535b8e9}

* Você deve ser um cliente atual do Kampyle para sites.
* Você deve ser um usuário administrador da Adobe Experience Cloud com permissões para ativar os conectores de dados.
* Você deve ser capaz de recuperar a chave privada do Kampyle na interface do usuário do gerenciamento de formulários de feedback do Kampyle.

## Recuperar a chave privada do Kampyle {#retrieve-the-kampyle-private-key}

Etapas para recuperar a chave na interface do Kampyle.

1. Faça logon na sua conta do Kampyle em [https://www.kampyle.com/login](https://www.kampyle.com/login).
1. Na navegação à esquerda, vá para **[!UICONTROL Formulário de feedback]** > **[!UICONTROL Personalização do formulário de feedback]**.

   ![](assets/retrieve_key1.png)

1. Localize a Chave privada listada na parte inferior do painel do conteúdo principal.

   ![](assets/retrieve_key2.png)
