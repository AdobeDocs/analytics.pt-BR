---
description: Detalhes do anúncio do fim da vida útil da API do Adobe Analytics 1.4.
title: Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 4%

---

# Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4

A Adobe planeja desativar a API do Adobe Analytics 1.4 em **12 de agosto de 2026**. Eles não estarão mais acessíveis após essa data. Esse anúncio afeta diretamente o seguinte:

* APIs do Adobe Analytics 1.4, excluindo a API de inserção de dados
* Autenticação WSSE do Adobe Analytics

## APIs 1.4

As [APIs do Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) fornecem uma grande variedade de ações, como relatórios, classificações, feeds de dados e configurações de conjuntos de relatórios. Eles estão sendo encerrados em favor das [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). As APIs 2.0 permitem executar quase todas as ações que você pode executar na interface do usuário do Analytics, como relatar ou gerenciar componentes como segmentos e métricas calculadas.

O Adobe oferece um [caminho de migração](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) para usuários da API 1.4. Você pode migrar suas integrações para as APIs 2.0 (as mesmas APIs das quais o aplicativo do Adobe Analytics depende) e aproveitar os recursos mais recentes. Todos os recursos disponíveis nas APIs 1.4 podem ser obtidos usando as [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Autenticação WSSE

A autenticação WSSE é um protocolo de autenticação herdado compatível com as APIs do Analytics 1.4. Ele foi substituído pelas opções de autenticação com base em OAuth fornecidas no [Adobe Developer Console](https://developer.adobe.com/console/home). Os projetos que usam a autenticação WSSE devem atualizar suas credenciais para aquelas provisionadas na Adobe Developer Console. Para fazer isso, faça logon no [Adobe Developer Console](https://developer.adobe.com/console/home) para criar um projeto para a integração da API do Analytics 2.0. Selecione o método de autenticação Usuário OAuth ou Servidor a Servidor OAuth.

## Perguntas frequentes

+++**Isso afeta meus projetos existentes do Adobe IO para as APIs do Analytics?**

Todos os projetos existentes que usam as APIs do Analytics 1.4 serão afetados. Essas integrações devem ser migradas para as [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) antes do prazo de fim da vida útil.

+++

+++**Compartilhei minhas credenciais do Adobe com outro produto ou aplicativo que usa as APIs do Analytics. Eles foram afetados?**

Se esse produto ou aplicativo usar sua credencial WSSE e/ou chamar as APIs do Analytics 1.4, ele será afetado e deverá migrar antes do prazo de EOL. Entre em contato com o fornecedor de produtos ou aplicativos para obter mais detalhes sobre os planos de migração e o cronograma.

+++

+++**Como posso determinar qual API o meu projeto usa?**

O URL de base que a API chama determina qual versão da API o projeto usa. As APIs do Adobe Analytics 1.4 usam os seguintes URLs:
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

As [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) usam esta URL:

* `https://analytics.adobe.io`

Se qualquer um dos projetos de API usar o `api*.omniture.com`, ele usará as APIs do Adobe Analytics 1.4 e deverá migrar para as APIs 2.0.

+++

+++**Este fim da vida útil afeta a coleta de dados?**

O fim da vida útil do Adobe Analytics 1.4 não afeta suas soluções de marcação, como Tags (antigo Adobe Launch), Web SDK ou AppMeasurement. No entanto, se você usar as APIs de Classificações ou Fontes de dados 1.4 para aprimorar seus dados, será necessário migrar esses fluxos de trabalho para as APIs do Adobe Analytics 2.0.

A API de inserção de dados não é afetada por esse anúncio de fim de vida útil. Embora a Adobe planeje continuar a oferecer suporte à API de inserção de dados, a Adobe recomenda usar a [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).

+++

Caso tenha mais dúvidas sobre esse anúncio do fim da vida útil que não foram respondidas nesta página, entre em contato com a equipe de conta da Adobe.
