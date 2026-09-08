---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
hold: true
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8645907799594d2eb2d6bcf56f93ac1cc42578f8
workflow-type: tm+mt
source-wordcount: 1098
ht-degree: 50%

---

# Notas de versão atuais do Adobe Analytics (setembro de 2026)

**Última atualização**: 8 de setembro de 2026

Essas notas de versão abordam o período de lançamento de setembro de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Limitar segmentos ao intervalo de datas do relatório**<br/> Os dados em um relatório do Workspace podem se estender além do intervalo de datas do relatório quando um segmento inclui componentes de intervalo de datas.<p>Uma nova opção está disponível e permite limitar os resultados ao intervalo de datas do relatório, independentemente de quaisquer componentes de data incluídos no segmento. <p>Essa opção está disponível ao criar ou modificar um segmento cujo contêiner de nível superior é Visitante.</p><p>Para obter mais informações, consulte [Criar segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | 26 de agosto de 2026 | 9 de setembro de 2026 |
| **Atualizações da detecção de bot**<br/> Ao usar a Coleção de dados da Edge com o Web SDK, as seguintes atualizações de detecção de bot estão disponíveis:<ul><li>Agora é possível criar regras de detecção de bot para identificar exceções no tráfego que, de outra forma, seriam tratadas como geradas por bot. As regras atuais e futuras continuarão a ser padronizadas para marcar o tráfego correspondente como gerado por bot.</li><li>Agora as regras de bot personalizadas são executadas antes das regras de detecção de bot IAB. Essa alteração não afeta as pontuações de bot, mas os nomes de regra de bot associados a um evento podem ser alterados.</li></ul><p>Observação: essa atualização se aplica somente às implementações da Coleta de dados do Edge que usam o Web SDK. Isso não se aplica a bibliotecas mais antigas, como a AppMeasurement.</p></p><p>(Link para a documentação a seguir).</p> | | Início de setembro de 2026 |
| **Integração com o Adobe Brand Visibility**<br/> Conecte o Adobe Brand Visibility aos dados do Adobe Analytics de sua organização para que você possa medir como a descoberta orientada por IA se traduz em envolvimento real com o site e em resultados comerciais.<p>(Link para a documentação a seguir).</p> | | Setembro de 2026 |
| **Atualizações da API dos conjuntos de classificação**<br/> A documentação da API dos conjuntos de classificação agora inclui informações atualizadas de parâmetro e ponto de extremidade para configurar solicitações de API dos conjuntos de classificação.<p>Para obter mais informações, consulte o [manual de ponto de extremidade de classificações](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/).</p> | 5 de setembro de 2026 | 30 de setembro de 2026 |
| **Orientação para a codificação de date itemId nos guias do relatório da API 2.0**<br/> Os guias do relatório de tendência de data da API do Adobe Analytics 2.0 agora incluem novas seções que explicam como os parâmetros e valores da data `itemId` são codificados. Isso pode ajudá-lo a configurar e migrar para os serviços de API 2.0 a partir das APIs 1.4 que foram descontinuadas.<p>Para obter mais informações, consulte o [guia de relatório de KPI](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi) e o [guia de relatório avançado](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced).</p> | 5 de setembro de 2026 | 30 de setembro de 2026 |

### Correções no Adobe Analytics

**Activity Map**: AN-488579, AN-487247
**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373
**Classificações**: AN-490825, AN-490802, AN-490549, AN-490472, AN-487782, AN-487286, AN-486531, AN-478859, AN-469929, AN-469033, AN-468944, AN-468827, AN-468592, AN-468326, AN-467115, AN-466995, AN-465636, AN-465616, AN-465380, AN-464911, AN-464338, AN-463677, AN-462729, AN-462577, AN-461040, AN-459316
**Feeds de dados e Data Warehouse**: AN-487624, AN-487287, AN-479923, AN-479166, AN-479109, AN-468483
**Migração**:
**Exportações**: AN-467131
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695
**Relatórios**: AN-468621, AN-465383, AN-463924
**Conjuntos de relatórios**: AN-468484, AN-468460, AN-465385
**Relatórios agendados**:
**Segmentação**: AN-486561
**Outros**: AN-488549, AN-467426, AN-465265, AN-464645, AN-459714, AN-459323, AN-454514

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

