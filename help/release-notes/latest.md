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
source-git-commit: 0d5c4866332fcbc8195e59babd01abc95444ffac
workflow-type: tm+mt
source-wordcount: 959
ht-degree: 59%

---

# Notas de versão atuais do Adobe Analytics (julho de 2026)

**Última atualização**: 8 de julho de 2026

Essas notas de versão abrangem o período de julho de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Análise de subocorrência** <br/>A análise de subocorrência permite analisar os dados do produto em um nível mais granular do que o nível de ocorrência. Em vez de filtrar em ocorrências inteiras, você pode segmentar em produtos individuais nas ocorrências. <p>Por exemplo, você pode segmentar em uma categoria de produto específica sem incluir todos os outros produtos comprados na mesma ordem.</p><p>Para obter mais informações, consulte [Análise de subocorrência](/help/components/segmentation/sub-hit.md).</p> | 8 de julho | Final de julho de 2026 |
| **Extensão do Activity Map: Atualização da interface e do suporte do Web SDK** <br/>As implementações do Web SDK do Adobe Analytics agora podem usar a extensão de sobreposição do Activity Map para exibir dados de cliques sobrepostos em seus sites.<p>Anteriormente, a extensão de sobreposição do Activity Map estava disponível somente para implementações do AppMeasurement.</p> <p>Além do suporte ao Web SDK, a extensão de sobreposição do Activity Map também inclui uma aparência atualizada.</p><p>(Link para a documentação a seguir).</p> | | Final de julho de 2026 |
| **Guia de recursos de pesquisa de API do AA 2.0** <br/>Use recursos de pesquisa para [retornar um subconjunto de itens de dimensão em relatórios](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters).<p>Para obter mais informações, consulte [Pesquisar recursos](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters) no manual de ponto de extremidade de relatórios no Adobe Developer. | | 1 de julho de 2026 |
| **Automatização de relatórios recorrentes com APIs do AA** <br/>Configure relatórios recorrentes e automáticos do Adobe Analytics para o seu pipeline de dados com métricas novas em um agendamento com a API de relatórios. <p>Para obter mais informações, consulte o [manual de ponto de extremidade de automatização de relatórios recorrentes do Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring) no Adobe Developer.</p> | | 1 de julho de 2026 |
| **Novos parâmetros de expansão para o AA** <br/>Use novos parâmetros de expansão da API do Dimension para recuperar campos de configuração do eVar para tipos de alocação, expirações, tipos de dados e merchandising. <p>Para obter mais informações, consulte a [Referência da API](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions) e o [manual de ponto de extremidade de dimensões](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/) no Adobe Developer.</p> | | 1 de julho de 2026 |

### Correções no Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-449890, AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Classificações**: AN-453318, AN-456739, AN-455828, AN-455270, AN-460272, AN-459367, AN-459239, AN-458418, AN-458417
**Feeds de dados e Data Warehouse**: AN-456945, AN-460700
**Migração**:
**Exportações**:
**Report Builder**: AN-457533, AN-453683
**Relatórios**: AN-447692, AN-451259, AN-455713
**Conjuntos de relatórios**:
**Relatórios agendados**: AN-450715
**Segmentação**:
**Outros**: AN-453982, AN-455771

### Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Report Builder legado** | 18 de junho de 2025 | O complemento do Report Builder legado será removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](/help/analyze/report-builder/rb-overview.md). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](/help/analyze/report-builder/convert-workbooks.md#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obter respostas a perguntas comuns e mais orientações.</p> |

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Recursos adiados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Serviços de mídia de streaming: compatibilidade com dados de programação** <br/>Agora é possível fazer upload de dados de programação de conteúdo ao vivo anterior de mídia de streaming para acompanhar o número de visualizadores de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data) | 29 de outubro de 2025 | A ser determinado<p>(Planejado originalmente para 29 de outubro de 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notas de versão anteriores para 2026](/help/release-notes/2026.md)
>* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
>* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/release-notes/release-notes)
>* As atualizações de versão mais recentes para [produtos Adobe CX Enterprise](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

