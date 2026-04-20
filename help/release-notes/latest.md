---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7a245e2c24e8763c93150aa5b9f3ac2d197f6f1f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Analytics (abril de 2026)

**Última atualização**: 9 de abril de 2026

Essas notas de versão abrangem o período de lançamento de abril de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Servidores MCP para o Adobe Analytics** <br/>Agora é possível vincular o Adobe Analytics aos fluxos de trabalho agênticos existentes com o MCP (Model Context Protocol). É possível solicitar relatórios e insights usando linguagem natural.<p>(Link para a documentação a seguir).</p> | | Final de abril de 2026 |
| **Serviços de mídia de streaming: compatibilidade com dados de programação** <br/>Agora é possível fazer upload de dados de programação de conteúdo ao vivo anterior de mídia de streaming para acompanhar o número de visualizadores de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |
| **Formatação adicional do intervalo de datas da API**<br/> Dois novos formatos agora são compatíveis com a especificação de intervalos de datas nas solicitações de relatório de API do Analytics 2.0. Isso inclui uma fórmula de data e um formato misto. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | Março de 2026 |
| **Dimensão opcional nas solicitações de relatório da API**<br/> Não é necessário um objeto de dimensão nas solicitações da API de relatório. Se nenhuma dimensão for especificada, a resposta mostrará os dados de um relatório de Totais. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | Março de 2026 |
| **Relatório de API avançado com tendência de data**<br/> Novo Guia de relatório avançado com tendência de data da API 2.0 do Adobe Analytics Crie relatórios avançados de API com tendência de data usando comparações e segmentos de intervalos de datas. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | Março de 2026 |

## Correções no Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-442813, AN-442410, AN-441943, AN-441717, AN-434855, AN-431409, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Classificações**: AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-440716, AN-440511, AN-440496, AN-432100
**Feeds de dados e Data Warehouse**: AN-442211, AN-441719, AN-441183, AN-441011, AN-440625, AN-438953
**Migração**: AN-442467, AN-440380, AN-440357
**Exportações**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Relatórios**: AN-441506, AN-440919, AN-440545, AN-440300
**Conjuntos de relatórios**: AN-439429, AN-439423, AN-430988
**Relatórios agendados**:
**Segmentação**:
**Outros**: AN-423359, AN-406242, AN-397985


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
* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
