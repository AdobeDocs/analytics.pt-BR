---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9c6da2c1ed5bc2c016da16a5bb821f0064e1ae4f
workflow-type: ht
source-wordcount: '689'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Analytics (versão de maio de 2025)

**Última atualização**: 14 de maio de 2025

Essas notas de versão abrangem o período de lançamento de xx de abril a 18 de junho de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **O painel esquerdo do Analysis Workspace não abre e fecha ao passar o mouse** | O painel esquerdo do Analysis Workspace é usado para adicionar componentes, painéis e visualizações ao projeto. A opção de abrir temporariamente o painel esquerdo passando o mouse sobre um dos ícones à esquerda não está mais disponível. Em vez disso, basta clicar em um desses ícones para manter o painel aberto e clicar novamente no ícone para fechá-lo. |  | 29 de maio de 2025 |


## Correções no Adobe Analytics

**Alertas**: AN-378351
**Analysis Workspace**: AN-363521; AN-367366; AN-373575; AN-374238; AN-374295; AN-374382; AN-376938; AN-377176; AN-377467; AN-377942
**Transferência de ativos**: AN-373381
**Classificações**: AN-373166; AN-373479; AN-376074; AN-377337; AN-377505
**Componentes**: AN-314468
**Feeds de dados**: AN-370241; AN-375267; AN-376940
**Fontes de dados**: AN-375259
**Data Warehouse**: AN-370415; AN-372090;
**Plataforma**: AN-365681; AN-372306; AN-372616;
**Relatório em tempo real**: AN-365681
**Report Builder**: AN-371395
**Segmentação**: AN-373576; AN-375858
**Conjuntos de relatórios virtuais**: AN-377948; AN-377952
**Regras VISTA**: AN-373292

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **O painel esquerdo do Analysis Workspace não abre e fecha ao passar o mouse** | O painel esquerdo do Analysis Workspace é usado para adicionar componentes, painéis e visualizações ao projeto. A opção de abrir temporariamente o painel esquerdo passando o mouse sobre um dos ícones à esquerda não está mais disponível. Em vez disso, basta clicar em um desses ícones para manter o painel aberto e clicar novamente no ícone para fechá-lo. |  | 29 de maio de 2025 |


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Acesso via domínios herdados ou via SSO herdado** | 10 de abril de 2025 | A Adobe planeja atualizar como os usuários acessam o Adobe Analytics para melhorar a segurança e simplificar a sua experiência de logon. Como parte dessa iniciativa, o acesso por meio de domínios herdados ou de um SSO herdado, incluindo `my.omniture.com`, será descontinuado permanentemente em **2 de janeiro de 2026**. Após essa data, as credenciais de logon herdadas e o SSO herdado não funcionarão mais. Todos os usuários precisarão fazer logon via `experience.adobe.com`, usando suas IDs da Adobe Experience Cloud. Se precisar de assistência com o sua ID da Experience Cloud, entre em contato com o administrador do Adobe Analytics da sua organização ou com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/contact.html). |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 17 de janeiro de 2025 | Os clientes da API do Adobe Analytics e da transmissão ao vivo que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até **30 de junho de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de versão anteriores para 2025](/help/release-notes/2025.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
