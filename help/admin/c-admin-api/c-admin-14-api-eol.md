---
description: Link para a API de administração do Adobe Analytics no Github.
title: PERGUNTAS FREQUENTES SOBRE EOL DA API DO Adobe Analytics 1.4
feature: Admin Tools
role: Admin
source-git-commit: da96c049f7cfb73496416c2d8a7f4dcbc8f2303e
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 2%

---

# PERGUNTAS FREQUENTES SOBRE EOL DA API DO Adobe Analytics 1.4

## Aviso de fim de vida útil (EOL)

**O que está sendo removido?**

* APIs do Adobe Analytics 1.4

* Autenticação Adobe Analytics WSSE

**Quando ele está sendo desligado?**

Esses serviços serão removidos em 12 de agosto de 2026. Eles não estarão mais acessíveis após essa data.

## APIs 1.4

**Quais são estes serviços?**

As [APIs do Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) são uma coleção de APIs que fornecem uma grande variedade de ações, como relatórios, classificações, feeds de dados e configurações de conjuntos de relatórios.

**O que preciso fazer para migrar?**

As [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) oferecem um caminho de migração adiante para usuários da API 1.4. Atualmente, os clientes que usam as APIs 1.4 podem migrar suas integrações para as APIs 2.0 (as mesmas APIs das quais o aplicativo do Adobe Analytics depende) e aproveitar os recursos mais recentes.

As APIs 2.0 permitem executar quase todas as ações que você pode executar na interface do usuário do Analytics, como relatar ou gerenciar componentes como segmentos e métricas calculadas.

**As APIs 2.0 oferecem os mesmos recursos que as APIs 1.4?**
Todos os recursos disponíveis nas APIs 1.4 podem ser obtidos usando as [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). Algumas funcionalidades fornecem os mesmos recursos que estão disponíveis nas APIs 1.4, têm os mesmos recursos e permitem executar quase todas as ações que você pode executar na interface do usuário do Analytics, como relatar ou gerenciar componentes como segmentos e métricas calculadas.

## Autenticação WSSE

**Quais são estes serviços?**

A autenticação WSSE é um protocolo de autenticação herdado compatível com as APIs do Analytics 1.4. Ele foi substituído pelas opções de autenticação com base em OAuth fornecidas no [Adobe Developer Console](https://developer.adobe.com/console/home).

**O que preciso fazer para migrar?**

Os clientes do WSSE devem atualizar suas autenticações para usar as credenciais provisionadas na Adobe Developer Console. Para fazer isso, faça logon no [Adobe Developer Console](https://developer.adobe.com/console/home) para criar um projeto para a integração da API do Analytics 2.0. Selecione entre os métodos de autenticação Usuário OAuth e Servidor a Servidor OAuth.

## Perguntas

P: **Isso afeta meus projetos existentes do Adobe IO para as APIs do Analytics?**

R: Qualquer projeto existente que use as APIs do Analytics 1.4 será afetado. Essas integrações devem ser migradas para as [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) antes do prazo de fim da vida útil.

P: **Compartilhei minhas credenciais de Adobe com outro produto ou aplicativo que usa as APIs do Analytics. Eles foram afetados?**

R: Se esse produto ou aplicativo usar sua credencial WSSE e/ou chamar as APIs do Analytics 1.4, ele será afetado e precisará ser migrado antes do prazo de Fim da vida útil. Entre em contato com o fornecedor do produto ou aplicativo para obter mais detalhes sobre os planos de migração e o cronograma.

P: **Não sei qual é a API do Adobe Analytics que estamos usando.**

R: Você pode identificar qual API está usando pelo endereço que está sendo chamado na integração.

As APIs do Adobe Analytics 1.4 são acessadas chamando qualquer um dos URLs abaixo:
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

As [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) são acessadas chamando a seguinte URL:
* https://analytics.adobe.io

Se você estiver usando api*.omniture.com, será necessário migrar para as [APIs do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

P: **As APIs do Adobe Analytics 2.0 são idênticas às APIs 1.4? Caso contrário, quais são as maiores diferenças?**

R: As APIs do Adobe Analytics 2.0 não são idênticas às APIs 1.4, mas oferecem recursos comparáveis, incluindo os seguintes benefícios:

* Tempos de resposta mais rápidos com métodos de consulta mais simples e eficientes, eliminando a necessidade de polling

* Capacidade programática para consultas e atualizações dinâmicas de relatórios

* Tratamento de erros mais adequado

* Funcionamento flexível para realizar qualquer coisa que você possa realizar com o Analysis Workspace

* Consistência e correspondência das chamadas de API às ações da interface

* Acesso a todos os modelos de Attribution IQ usados no Analysis Workspace

* Acesso a todos os algoritmos de Detecção de anomalias usados no Analysis Workspace

* Capacidade de integração com outros produtos Experience Cloud

* Maior capacidade para vários relatórios de detalhamento

* Acesso aos recursos mais recentes do Analytics

O guia [Migrating to Adobe Analytics 2.0 APIs](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) discute as principais diferenças entre as APIs 1.4 e 2.0. Informações adicionais também estão disponíveis nas [Perguntas frequentes sobre a API do Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/).

P: **Isso afeta a coleta de dados?**

R: O fim da vida útil do Adobe Analytics 1.4 não afeta suas soluções de marcação, como Tags (antigo Adobe Launch), WebSDK ou AppMeasurement.js. No entanto, se você usar as APIs de Classificações ou Fontes de dados 1.4 para coletar ou aprimorar os dados, será necessário migrar esses fluxos de trabalho para as APIs do Adobe Analytics 2.0. Consulte o [manual de Pontos de Extremidade de API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/) do {2.0} para obter mais detalhes.

P: **A API de Inserção de Dados será afetada?**

R: Não, a API de inserção de dados não é afetada pelo EOL do Adobe Analytics 1.4.

P: **O que devo fazer se minha pergunta não for respondida nessas Perguntas frequentes?**

R: Se você ainda tiver dúvidas, entre em contato com o representante de conta do Adobe.

