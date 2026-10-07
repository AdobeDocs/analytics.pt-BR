---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: b72328485bde3759519f77c1c3e9509ade6ce2d4
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 53%
---
# Notas de versão atuais do Adobe Analytics (outubro de 2026)

**Última atualização**: 7 de outubro de 2026

Essas notas de versão abordam o período de outubro de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Permissão somente leitura para o servidor MCP do Adobe Analytics**<br/> Os administradores agora podem conceder aos usuários acesso somente leitura ao servidor MCP do Adobe Analytics. O novo item de permissão [!UICONTROL MCP Somente Leitura] dá aos usuários acesso a todas as ferramentas somente leitura, sem permitir que eles criem projetos, segmentos ou métricas calculadas.<p>O item de permissão existente [!UICONTROL Acesso ao MCP] foi renomeado para [!UICONTROL Acesso Completo ao MCP]. Os usuários com essa permissão mantêm acesso a todas as ferramentas, incluindo ferramentas que criam, alteram ou excluem componentes.</p><p>Para obter mais informações, consulte [Adobe Analytics MCP server](https://developer.adobe.com/analytics-mcp/docs/aa/).</p> | | 6 de outubro de 2026 |
| **Gerar automaticamente descrições de componentes** <br/>Agora você pode gerar descrições automaticamente para dimensões, métricas, métricas calculadas, segmentos e intervalos de datas. Isso ajuda os usuários do Workspace a entender quais componentes usar, especialmente em organizações com grandes bibliotecas de componentes. <p>Você pode gerar uma descrição para um único componente ou gerar descrições para muitos componentes ao mesmo tempo.</p> <p>(O link da documentação será disponibilizado em breve).<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 de outubro de 2026 |
| **Integração com o Adobe Brand Visibility**<br/> Conecte o Adobe Brand Visibility aos dados do Adobe Analytics de sua organização para que você possa medir como a descoberta orientada por IA se traduz em envolvimento real com o site e em resultados comerciais.<p>(Link para a documentação a seguir).</p> | | Outubro de 2026 |
| **CX Enterprise Coworker: Analisar dados do Adobe Analytics no Chat do Colaborador** <br/>O Chat do Adobe CX Enterprise Coworker agora pode executar a análise avançada de dados que anteriormente só era possível no Analysis Workspace. O Bate-papo com colegas de trabalho acessa os dados dos seus conjuntos de relatórios do Adobe Analytics, permitindo que você explore esses dados e obtenha respostas para prompts em linguagem natural.<p>(Link para a documentação a seguir).</p> | 2 de outubro de 2026 | A ser determinado<p>(Planejado originalmente para 25 de setembro de 2026)</p> |

### Correções no Adobe Analytics

**Activity Map**: AN-494609, AN-493182
**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Classificações**: AN-498043, AN-496619, AN-496468, AN-496217, AN-496133, AN-495567, AN-494651, AN-494345, AN-494312, AN-494261, AN-493645, AN-493507, AN-49336, AN-492869, AN-492812, AN-492751, AN-492750, AN-492741, AN-491032, AN-490802, AN-490796, AN-467849
**Feeds de dados e Data Warehouse**: AN-494937, AN-493065, AN-489796, AN-479109
**Migração**: AN-489850, AN-468014
**Exportações**: AN-494337, AN-486563
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Relatórios**: AN-493637, AN-461260
**Conjuntos de relatórios**: AN-496773, AN-495227, AN-494981, AN-494372, AN-494370, AN-493629
**Relatórios agendados**: AN-491103
**Segmentação**:
**Outros**: AN-496398, AN-494453, AN-492494

### Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Report Builder legado** | 18 de junho de 2025 | O suplemento herdado do Report Builder foi removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](/help/analyze/report-builder/rb-overview.md). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](/help/analyze/report-builder/convert-workbooks.md#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **31 de agosto de 2026**, os seguintes serviços de API herdados do Analytics atingiram seu fim de vida útil e foram encerrados, e todas as integrações criadas usando esses serviços não funcionarão mais:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obter respostas a perguntas comuns e mais orientações.</p> |

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Recursos adiados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Serviços de mídia de streaming: compatibilidade com dados de programação** <br/>Agora é possível fazer upload de dados de programação de conteúdo ao vivo anterior de mídia de streaming para acompanhar o número de visualizadores de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Carregar dados de agendamento para rastrear o conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 de outubro de 2025 | A ser determinado<p>(Planejado originalmente para 29 de outubro de 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notas de versão anteriores para 2026](/help/release-notes/2026.md)
>* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
>* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/release-notes/release-notes)
>* As atualizações de versão mais recentes para [produtos Adobe CX Enterprise](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

