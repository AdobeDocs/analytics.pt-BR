---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ebe6716a3dde89d7212385c25044fb533d7737c2
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 84%

---

# Notas de versão atuais do Adobe Analytics (versão de julho de 2025)

**Última atualização**: quinta-feira, 16 de julho de 2025

Essas notas de versão abrangem o período de 7 de julho a 15 de agosto de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Campos TNT de Livestream com algoritmos** | O Livestream está passando por uma atualização para garantir que a tecnologia continue sendo moderna e estável. Como parte dessa atualização, se o campo TNT contiver um algoritmo, começaremos a incorporar o campo TNT na saída do Livestream. No entanto, isso inclui apenas os elementos compatíveis anteriormente: `campaignId`, `recipeId`, `trafficType`, `actionId` e `actionName`. O esquema TNT geral para Livestream permanecerá inalterado. |   | 7 de julho de 2025 |
| **Navegação atualizada na interface de Atributos do cliente** | A interface de Atributos do cliente agora pode ser acessada diretamente do seletor de aplicativos na Adobe Experience Cloud. | quarta-feira, 1 de julho de 2025 | A ser determinado |

## Correções no Adobe Analytics

**Activity Map**: AN-360987
**Analysis Workspace**: AN-378094; AN-380979; AN-382908; AN-387652;
**Classificações**: AN-382412; AN-383157; AN-384616; AN-384803; AN-385933; AN-387320; AN-387351; AN-387832; AN-387833; AN-387839; AN-387915;
**Coleta de dados**: AN-387661
**Feeds de dados**: AN-375172; AN-384369; AN-387859; AN-387952; AN-388155;
**Plataforma**: AN-382813; AN-386627; AN-386815
**Privacidade**: AN-384390
**Report Builder**: AN-388035
**Relatórios**: AN-380441
**Relatórios agendados**: AN-378280; AN-378331
**Comparação de segmentos**: AN-368766


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Report Builder legado** | 18 de junho de 2025 | O complemento do Report Builder legado será removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/report-builder/rb-overview). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **Acesso via domínios herdados ou via SSO herdado** | 10 de abril de 2025 | A Adobe planeja atualizar como os usuários acessam o Adobe Analytics para melhorar a segurança e simplificar a sua experiência de logon. Como parte dessa iniciativa, o acesso por meio de domínios herdados ou de um SSO herdado, incluindo `my.omniture.com`, será descontinuado permanentemente em **2 de janeiro de 2026**. Após essa data, as credenciais de logon herdadas e o SSO herdado não funcionarão mais. Todos os usuários precisarão fazer logon via `experience.adobe.com`, usando suas IDs da Adobe Experience Cloud. Se precisar de assistência com o sua ID da Experience Cloud, entre em contato com o administrador do Adobe Analytics da sua organização ou com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/contact.html). |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de versão anteriores para 2025](/help/release-notes/2025.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
