---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8bfb44d4eeb1812ec9b91a68bd37c2b660eae76e
workflow-type: tm+mt
source-wordcount: 573
ht-degree: 91%

---

# Notas de versão atuais do Adobe Analytics (maio de 2026)

**Última atualização**: 22 de junho de 2026

Essas notas de versão abrangem o período de junho de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Tela da jornada no Adobe Analytics** <br/>A Tela da jornada é uma visualização no Analysis Workspace que permite obter insights profundos sobre uma jornada do usuário definida ao analisar como as pessoas avançam ou abandonam a jornada. Ela permite criar um gráfico flexível de nós e setas representando qualquer combinação de eventos, itens de dimensão e segmentos incluídos na jornada. Os dados atualizam conforme se arrasta os nós para a tela ou se reorganiza os eventos e as condições da jornada.<p>A Tela da jornada estava disponível anteriormente apenas para o Customer Journey Analytics.</p><p>Para saber mais sobre a Tela da jornada no Adobe Analytics, consulte [Visão geral da Tela da jornada](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md). </p><p>Para saber como criar uma visualização da Tela da jornada no Adobe Analytics, consulte [Configurar Tela da jornada](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).</p> | 18 de maio de 2026 | 5 de junho de 2026 |

### Correções no Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-452009, AN-450375, AN-449870, AN-450814, AN-450698
**Classificações**:
**Feeds de dados e Data Warehouse**:
**Migração**:
**Exportações**:
**Report Builder**: AN-440912
**Relatórios**: AN-423516
**Conjuntos de relatórios**: AN-455684
**Relatórios agendados**:
**Segmentação**:
**Outros**:


### Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Report Builder legado** | 18 de junho de 2025 | O complemento do Report Builder legado será removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](/help/analyze/report-builder/rb-overview.md). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](/help/analyze/report-builder/convert-workbooks.md#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


>[!MORELIKETHIS]
>
>* [Notas de versão anteriores para 2026](/help/release-notes/2026.md)
>* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
>* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/release-notes/release-notes)
>* As atualizações de versão mais recentes para [produtos Adobe CX Enterprise](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
