---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d7beee25af3551426eb905f0e727545de068b2d9
workflow-type: ht
source-wordcount: '882'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Analytics (versão de janeiro de 2025)

**Última atualização**: 22 de janeiro de 2024

Essas notas de versão abrangem o período de lançamento de 15 de janeiro a meados de fevereiro de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Agendamentos no novo Adobe Report Builder** | O agendamento não só permite agendar suas novas pastas de trabalho do Adobe Report Builder, mas também, permite recuperar os metadados em tarefas agendadas antigas ao converter pastas de trabalho herdadas. Dessa forma, ao converter suas pastas de trabalho herdadas em novas pastas de trabalho e agendá-las, você as envia para os mesmos emails e na mesma cadência que as pastas de trabalho herdadas. [Saiba mais](/help/analyze/report-builder/schedule-reportbuilder.md) |  | 22 de janeiro de 2025 |
| **Melhorias nos relatórios (também conhecidos como modelos) no Analysis Workspace** | Várias melhorias estão disponíveis para os Relatórios (também conhecidos como Modelos):<ul><li>Agora denominados [!UICONTROL Modelos] (não mais conhecidos como [!UICONTROL Relatórios]).</li><li>Experiência do usuário aprimorada para visualizar e localizar modelos, incluindo a opção de visualizar modelos em uma exibição de coluna ou exibição de cartão.</li><li>Novo local mais intuitivo para modelos de Empresa (localizado em **[!UICONTROL Workspace]** > **[!UICONTROL Modelos]**).</li><li>Anteriormente, os modelos de empresa eram acessados na caixa de diálogo ao criar um projeto.</li><li>Modelos pré-criados adicionais estão disponíveis.</li></ul>[Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/templates/use-templates).<p>Administradores podem criar modelos e salvá-los para que outras pessoas na empresa do seu logon os usem. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/templates/create-templates) | 15 de janeiro de 2025 | 30 de janeiro de 2025 |
| **Período de retenção da ID da transação** | O período de retenção de 90 dias da ID da transação será estendido para 25 meses em fevereiro de 2025. A variável `transactionID` atribui uma identificação exclusiva a uma transação para que a ocorrência possa se vincular a dados enviados por meio de Fontes de dados. (Links da documentação em breve) |  | 11 de fevereiro de 2025 |

## Correções no Adobe Analytics

**A4T**: AN-355602; AN-365988
**Activity Map**: AN-365320
**Admin Console**: AN-363884
**Ferramentas administrativas**: AN-356747; AN-358776
**Advertising Analytics**: AN-355488
**Analysis Workspace**: AN-345318; AN-354801; AN-357052; AN-358975; AN-362886; AN-363831; AN-364124; AN-365257; AN-365319; AN-365462; AN-366194
**API do Analytics 1.4**: AN-358059
**Classificações**: AN-360049; AN-360424; AN-360745; AN-362208; AN-362345; AN-362560; AN-362576; AN-362633; AN-362653; AN-362762; AN-362815; AN-362881; AN-362885; AN-362973; AN-363343; AN-363558; AN-363860; AN-364239; AN-364480; AN-364451; AN-364528; AN-364548; AN-364552; AN-364585; AN-364598; AN-364643; AN-364715; AN-364912; AN-364997; AN-365081; AN-365189; AN-365197; AN-365203; AN-365431; AN-365647; AN-365794; AN-366546
**Migração de componentes**: AN-362236; AN-365429
**Análise de contribuição**: AN-360146
**Feeds de dados**: AN-356997; AN-362470; AN-362498; AN-362775; AN-363323; AN-363413; AN-363569; AN-364063; AN-364142; AN-364294; AN-364298; AN-364325; AN-364367; AN-364594; AN-364995; AN-365127; AN-365272; AN-365519; AN-365760; AN-366152;
**API de reparo de dados**: AN-362773; AN-362874
**Fontes de dados**: AN-360745; AN-362202; AN-364566
**Data Warehouse**: AN-361447; AN-362616; AN-364524; AN-365108
**Aplicativo móvel**: AN-362856; AN-365270
**Alertas de excesso**: AN-355594; AN-364547
**Plataforma**: AN-358914; AN-360205; AN-362990; AN-364550; AN-365454; AN-365485
**Report Builder**: AN-363478; AN-364433; AN-365610
**Gerente de atividades de relatórios**: AN-362440
**Segmentação**: AN-359921
**Regras VISTA**: AN-362927

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Clientes de fora do Campaign perderão o acesso aos acionadores** | 16 de outubro de 2023 | Em 30 de janeiro de 2025, os clientes do Adobe Analytics que não tiverem uma licença do Adobe Campaign perderão o acesso à opção de configurar e consumir [Acionadores](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/services/triggers). Os clientes precisam comprar o Campaign, planejar o fim do uso dos acionadores ou procurar outras ferramentas da Adobe que ofereçam recursos de acionador. |

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 17 de janeiro de 2025 | Os clientes da API do Adobe Analytics e da transmissão ao vivo que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até **30 de junho de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/appmeasurement-updates).


## Recursos relacionados

* [Notas de versão anteriores para 2024](/help/release-notes/2024.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
