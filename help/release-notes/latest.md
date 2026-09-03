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
source-git-commit: 2258ee4b539ec7ce7366c427fede2c5b8483db7f
workflow-type: tm+mt
source-wordcount: 1246
ht-degree: 43%

---

# Notas de versão atuais do Adobe Analytics (agosto de 2026)

**Última atualização**: 5 de agosto de 2026

Essas notas de versão abrangem o período de agosto de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Extensão do Activity Map: atualização da interface** <br/>A extensão de sobreposição do Activity Map tem uma aparência atualizada, juntamente com melhorias subjacentes que oferecem suporte a aprimoramentos futuros.<p>Para obter informações sobre a extensão de sobreposição do Activity Map, consulte [interface de extensão do Activity Map](/help/analyze/activity-map/overlay/overview.md).</p> | | 5 de agosto de 2026<p>(Planejado originalmente para o final de julho)</p> |
| **Aprimoramentos na tela de Jornada**<br> Os seguintes aprimoramentos na tela de Jornada estão disponíveis:<ul><li>Compare a jornada a um intervalo de tempo anterior. Compare a jornada atual com a jornada 4 semanas antes, 2 trimestres antes, 1 ano antes ou com um intervalo de datas personalizado.</li><li>Para um nó selecionado, mostre os itens de dimensão principais que vêm após o nó selecionado em qualquer ponto da jornada. Use-a quando o nó selecionado for o evento principal na análise e você quiser ver o que as pessoas fazem em qualquer ponto depois.<p>Anteriormente, somente os nós imediatos principais podiam ser exibidos antes ou depois do nó selecionado. </p></li><li>Alterar a forma e o estilo das setas entre os nós. Arraste as setas entre os nós para alterar a forma (curvatura) da seta e clique com o botão direito do mouse em uma seta para alterar seu estilo para qualquer um dos seguintes: sólido, tracejado, pontilhado, tracejado-ponto ou animado.</li></ul><p></p>Para  mais informações, consulte [Configurar uma visualização da tela de jornada](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). | | 18 de agosto de 2026 |
| **Limitar segmentos ao intervalo de datas do relatório**<br/> Os dados em um relatório do Workspace podem se estender além do intervalo de datas do relatório quando um segmento inclui componentes de intervalo de datas.<p>Uma nova opção está disponível e permite limitar os resultados ao intervalo de datas do relatório, independentemente de quaisquer componentes de data incluídos no segmento. <p>Essa opção está disponível ao criar ou modificar um segmento cujo contêiner de nível superior é Visitante.</p><p>Para obter mais informações, consulte [Criar segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | 26 de agosto de 2026 | 9 de setembro de 2026 |
| **Referência de canais de marketing da API do Analytics**<br/> Use a referência de canais de marketing da API do Adobe Analytics 2.0 para recuperar informações de canais de marketing do Analytics. Consulte a [Referência de canais de marketing da API do Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/apis/marketing-channels). | | 1 de agosto de 2026 |
| **manual de ponto de extremidade de canais de marketing da API do Analytics**<br/> O manual de ponto de extremidade de canais de marketing da API do Adobe Analytics 2.0 fornece instruções e exemplos para usar o ponto de extremidade. Consulte o [Guia de endpoint de canais de marketing da API do Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/marketing-channels). | | 1 de agosto de 2026 |
| **Perguntas frequentes sobre clientes com API EOL do Analytics 1.4**<br/> As perguntas frequentes sobre clientes com API EOL do Analytics 1.4 fornecem informações sobre o desenvolvimento recente da API 2.0 para ajudar os clientes que deixam as APIs 1.4. | | 10 de agosto de 2026 |

### Correções no Adobe Analytics

**Activity Map**: AN-404862
**Analysis Workspace**: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671, AN-457760, AN-443594
**Classificações**: AN-467138, AN-467118, AN-467069, AN-466054, AN-465987, AN-465636, AN-465380, AN-464650, AN-464286, AN-463688, AN-462413, AN-462252, AN-462141, AN-462063, AN-462005, AN-461862, AN-461806, AN-461777, AN-46158, AN-460954, AN-460905, AN-460850, AN-460803, AN-460272, AN-460023, AN-459814, AN-459367, AN-459328, AN-459300, AN-459279, AN-459006, AN-458417, AN-458403, AN-457829, AN-457400, AN-454408, AN-449670, AN-460956, AN-459269, AN-458789, AN-461778, AN-461191, AN-460996, AN-460506, AN-459988, AN-459854, AN-458994, AN-457561, AN-457055, AN-454224, AN-454172, AN-459473, AN-459277, AN-459026, AN-455270
**Feeds de dados e Data Warehouse**: AN-465273, AN-464245, AN-462435, AN-461000, AN-460700, AN-459225, AN-459192
**Migração**: AN-458185, AN-454285, AN-459239
**Exportações**:
**Report Builder**: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**Relatórios**: AN-467107, AN-459010, AN-455619, AN-459530, AN-454103
**Conjuntos de relatórios**: AN-464246, AN-463756, AN-462101
**Relatórios agendados**: AN-455009, AN-460037, AN-462093
**Segmentação**: AN-459002, AN-457730, AN-457146
**Outros**: AN-467386, AN-466935, AN-462116, AN-458836, AN-451292, AN-454160, AN-458354, AN-455771, AN-426869, AN-437975

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
| **Serviços de mídia de streaming: compatibilidade com dados de programação** <br/>Agora é possível fazer upload de dados de programação de conteúdo ao vivo anterior de mídia de streaming para acompanhar o número de visualizadores de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Carregar dados de agendamento para rastrear o conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 de outubro de 2025 | A ser determinado<p>(Planejado originalmente para 29 de outubro de 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notas de versão anteriores para 2026](/help/release-notes/2026.md)
>* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
>* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/release-notes/release-notes)
>* As atualizações de versão mais recentes para [produtos Adobe CX Enterprise](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

