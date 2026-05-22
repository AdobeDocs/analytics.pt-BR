---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
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
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 1365
ht-degree: 60%

---

# Notas de versão atuais do Adobe Analytics (maio de 2026)

**Última atualização**: 13 de maio de 2026

Essas notas de versão abordam o período de lançamento de maio de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Servidores MCP para Adobe Analytics** <br/>Os servidores MCP (Model Context Protocol) do Analytics permitem conectar um cliente MCP com suporte ao Adobe Analytics. Depois de conectado, o cliente MCP poderá invocar ferramentas específicas do produto para recuperar dados, executar consultas ou executar operações compatíveis como parte de um fluxo de trabalho AGENT ou LLM. Para obter mais informações, consulte [Servidores MCP do Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Se você usou esses servidores MCP durante o período beta, observe que há URLs diferentes entre os endpoints beta e de produção. Verifique se todos os workflows de agente criados durante o período beta foram atualizados para usar os endpoints de produção antes de 31 de maio.</p> | | 5 de maio de 2026 |
| **Tela do Jornada no Adobe Analytics** <br/>A tela do Jornada é uma visualização no Analysis Workspace que permite obter insights profundos sobre uma jornada de usuário definida ao analisar como as pessoas avançam ou saem da jornada. Ele permite criar um gráfico flexível de nós e setas representando qualquer combinação de eventos, itens de dimensão e segmentos incluídos na jornada. Os dados são atualizados à medida que você arrasta nós para a tela ou reorganiza os eventos e as condições da jornada.<p>A tela de Jornada estava disponível anteriormente somente para o Customer Journey Analytics.</p><p>Para saber mais sobre a tela do Jornada no Adobe Analytics, consulte [visão geral da tela do Jornada](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md). </p><p>Para saber como criar uma visualização da tela de Jornada no Adobe Analytics, consulte [Configurar tela de Jornada](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).</p> | 18 de maio de 2026 | 5 de junho de 2026 |
| **Guia de relatórios da API de modelo de atribuição** <br/>Um novo Guia de relatório do Modelo de atribuição da API do Adobe Analytics 2.0 está disponível. O guia aborda como incluir dados do objeto de modelo de atribuição nos relatórios da API do Dimension.<p>Para obter mais informações, consulte [modelos de atribuição da API do Dimension](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/attmodel).</p> | | Maio de 2026 |
| **Serviços de mídia de streaming: compatibilidade com dados de programação** <br/>Agora é possível fazer upload de dados de programação de conteúdo ao vivo anterior de mídia de streaming para acompanhar o número de visualizadores de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |

{style="table-layout:auto"}

## Correções no Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-440599, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Classificações**: AN-447743, AN-447296, AN-447130, AN-446552, AN-446324, AN-446040, AN-445841, AN-445753, AN-444992, AN-444979, AN-44428, AN-444332, AN-443507, AN-442906, AN-442232, AN-442207, AN-442133, AN-442035, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441267, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-440716, AN-440496, AN-440429, AN-432100
**Feeds de dados e Data Warehouse**: AN-447344, AN-446654, AN-445126, AN-444492, AN-442802, AN-442211, AN-442048, AN-441719, AN-441534, AN-441300, AN-441183, AN-441011, AN-440625
**Migração**: AN-442467, AN-440380, AN-440357
**Exportações**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Relatórios**: AN-445123, AN-444869, AN-443453, AN-443275, AN-443148, AN-442464, AN-442148, AN-441811, AN-441506, AN-441149, AN-441119, AN-440545, AN-440511, AN-440300, AN-431409, AN-423359, AN-406242
**Conjuntos de relatórios**:
**Relatórios agendados**:
**Segmentação**:
**Outros**: AN-449159, AN-444661, AN-439429, AN-439423, AN-430988, AN-397985


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Melhorias no processamento do Livestream** | quinta-feira, 14 de janeiro de 2026 | A Adobe planeja fazer melhorias e alterações na formatação dos conteúdos do LiveStream. Essas atualizações fornecem melhor paridade entre o LiveStream e outros recursos do Adobe Analytics, como o Analysis Workspace. Um ponto de acesso de visualização está disponível e permite testar as alterações planejadas. Consulte as [notas de versão do LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) para obter a lista completa de alterações e detalhes do ponto de acesso de visualização. A Adobe planeja uma transferência forçada para o formato de conteúdo atualizado em 13 de abril de 2026. |
| **Remoção dos conjuntos de criptografia TLS 1.2** | 11 de fevereiro de 2026 | Aviso aos admins: a Adobe planeja remover o suporte aos seguintes conjuntos de criptografia TLS 1.2 dos seus servidores de coleção de dados em 27 de maio de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Nenhuma ação do cliente é necessária para a maioria das implementações. Essa alteração afeta principalmente os dados do Analytics enviados de aplicativos nativos herdados que usam bibliotecas TLS desatualizadas e um pequeno número de visitantes da web em navegadores ou sistemas operacionais obsoletos. A remoção do suporte a esses conjuntos de criptografia melhora a segurança e alinha a Adobe aos padrões de criptografia modernos. Menos de 0,1% do tráfego de coleção de dados atualmente depende desses conjuntos de criptografia.</p> |
| **Report Builder legado** | 18 de junho de 2025 | O complemento do Report Builder legado será removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](/help/analyze/report-builder/rb-overview.md). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](/help/analyze/report-builder/convert-workbooks.md#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **Acesso via domínios herdados ou via SSO herdado** | 10 de abril de 2025 | A Adobe planeja atualizar como os usuários acessam o Adobe Analytics para melhorar a segurança e simplificar a sua experiência de logon. Como parte dessa iniciativa, o acesso por meio de domínios herdados ou de um SSO herdado, incluindo `my.omniture.com`, será descontinuado permanentemente em **2 de janeiro de 2026**. Após essa data, as credenciais de logon herdadas e o SSO herdado não funcionarão mais. Todos os usuários precisarão fazer logon via `experience.adobe.com`, usando suas IDs da Adobe Experience Cloud. Se precisar de assistência com o sua ID da Experience Cloud, entre em contato com o administrador do Adobe Analytics da sua organização ou com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/contact.html). |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de versão anteriores para 2025](/help/release-notes/2025.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/release-notes/release-notes)
* As últimas atualizações de versão para [produtos Adobe CX Enterprise](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
