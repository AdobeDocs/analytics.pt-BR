---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c86e1ef4a93591e7623fe5a9f2f9d92529773516
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 51%

---

# Notas de versão atuais do Adobe Analytics (março de 2026)

**Última atualização**: quinta-feira, 11 de março de 2026

Essas notas de versão abordam o período de lançamento de março de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ---- |
| **Detalhamento do painel**<br/> A área de lançamento de um painel agora oferece o recurso adicional para [analisar](/help/analyze/analysis-workspace/c-panels/panels.md#break-down-a-panel) (em vez de segmentar) um painel baseado em uma dimensão. | quarta-feira, 31 de março de 2026 | quarta-feira, 31 de março de 2026 |
| **Classificar tabelas por várias colunas** <br/>Agora é possível classificar os dados de uma tabela de forma livre por várias colunas no Analysis Workspace, sejam elas dimensões ou métricas.<p>Ao classificar dados para várias colunas, os dados são classificados de acordo com a prioridade atribuída a cada coluna. A numeração de prioridade é exibida ao lado do ícone de classificação.</p><p>Para obter mais informações, consulte [Filtrar e classificar tabelas de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | quinta-feira, 28 de janeiro de 2026 | quinta-feira, 4 de março de 2026 <p>(Planejado originalmente para 18 de fevereiro de 2026)</p> |
| **Report Builder: visibilidade de administrador para todas as pastas de trabalho agendadas**<br/> O suplemento do Report Builder Excel inclui uma nova opção de filtro que permite que os administradores vejam todas as pastas de trabalho agendadas para uma determinada organização, independentemente de quem as agendou. Essa opção de filtro está disponível somente para administradores do Analytics. Está disponível nas guias Pasta de trabalho e Herdado ao exibir pastas de trabalho programadas.<p>A capacidade de exibir todas as pastas de trabalho agendadas é especialmente útil ao migrar pastas de trabalho entre equipes distribuídas, pois permite que os administradores localizem facilmente todas as pastas de trabalho herdadas antes de migrá-las.</p><p>Anteriormente, os administradores podiam visualizar somente as pastas de trabalho agendadas, não aquelas agendadas por outros usuários.</p><p>Para obter mais informações, consulte [Pastas de trabalho agendadas gerenciadas](/help/analyze/report-builder/manage-schedules-reportbuilder.md).</p> | | quarta-feira, 10 de março de 2026 |
| **Atualização para a função distinta de contagem aproximada**<br/> O algoritmo probabilístico HLL usado na função distinta de contagem aproximada será atualizado em breve. A saída resultante para números que utilizam essa função pode mudar ligeiramente de números históricos, da seguinte maneira:</p><ul><li>Ao contar quantidades muito pequenas de valores únicos, os resultados serão aprimorados para usar contagens exatas em vez de usar estimativas.</li><li>Ao contar qualquer coisa maior, as estimativas de contagem manterão a mesma precisão de antes dessa atualização (as estimativas são precisas dentro de 5% do número exato, 95% do tempo).</li></ul><p>Para obter mais informações sobre a função Contagem distinta aproximada, consulte [Contagem distinta aproximada](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) em [Funções avançadas](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> | | quarta-feira, 10 de março de 2026 |
| **Tutorial prático para o Analysis Workspace**<br/> Um novo tutorial prático está disponível para orientar novos usuários sobre as noções básicas de uso de painéis, visualizações e componentes no Analysis Workspace. <p>Para obter mais informações, consulte [Página de aterrissagem do Adobe Analytics](/help/analyze/landing.md).</p> | | quinta-feira, 18 de março de 2026 |
| **Aplicar um detalhamento a um painel**<br/> Agora é possível aplicar um detalhamento a um painel. Ao aplicar um detalhamento no nível do painel, o detalhamento é aplicado a todas as colunas em todas as tabelas de forma livre no painel. | Março de 2026 | Maio de 2026 |
| **Serviços de mídia de streaming: Suporte a dados de agendamento** <br/>Agora você pode carregar dados agendados de conteúdo de mídia de streaming ao vivo anterior de forma a rastrear a audiência com mais facilidade e precisão.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |

## Correções no Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-440336, AN-440216, AN-440121, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**Classificações**: AN-440143, AN-439891, AN-439844, AN-438994, AN-438057, AN-438052, AN-437986, AN-437896, AN-435387, AN-435335, AN-435150, AN-433050, AN-432062, AN-431873, AN-429642
**Feeds de dados e Data Warehouse**: AN-439441, AN-437086, AN-433064, AN-432121, AN-431755, AN-428239, AN-427049, AN-425036, AN-424972, AN-423509, AN-335417, AN-283958, AN-256948
**Migração**:
**Exportações**: AN-432030
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**Relatórios**: AN-434545, AN-431206, AN-428043
**Relatórios agendados**:
**Segmentação**:
**Outros**: AN-440076, AN-434783, AN-434542, AN-434233, AN-433368, AN-432138, AN-431322, AN-431012, AN-429067, AN-423285


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Melhorias no processamento do Livestream** | quinta-feira, 14 de janeiro de 2026 | A Adobe planeja fazer melhorias e alterações na formatação dos conteúdos do LiveStream. Essas atualizações fornecem melhor paridade entre o LiveStream e outros recursos do Adobe Analytics, como o Analysis Workspace. Um ponto de acesso de visualização está disponível e permite testar as alterações planejadas. Consulte as [notas de versão do LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) para obter a lista completa de alterações e detalhes do ponto de acesso de visualização. A Adobe planeja uma transferência forçada para o formato de conteúdo atualizado em 13 de abril de 2026. |
| **Remoção de conjuntos de cifras do TLS 1.2** | quinta-feira, 11 de fevereiro de 2026 | Aviso aos administradores: a Adobe planeja remover o suporte aos seguintes conjuntos de cifras TLS 1.2 dos servidores de coleta de dados da Adobe em 27 de maio de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Nenhuma ação do cliente é necessária para a maioria das implementações. Essa alteração afeta principalmente os dados do Analytics enviados de aplicativos nativos herdados que usam bibliotecas TLS desatualizadas e um pequeno número de visitantes da Web em navegadores ou sistemas operacionais obsoletos. A remoção do suporte para esses conjuntos de cifras melhora a segurança e alinha o Adobe aos padrões de criptografia modernos. Menos de 0,1% do tráfego da coleta de dados atualmente depende desses conjuntos de cifras.</p> |
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
