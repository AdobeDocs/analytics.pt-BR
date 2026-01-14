---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6bbaf402199d3fadbfad0729533b4668bb7035e3
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 49%

---

# Notas de versão atuais do Adobe Analytics (janeiro de 2026)

**Última atualização**: quinta-feira, 14 de janeiro de 2026

Essas notas de versão abordam o período de lançamento de janeiro de 2026. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Construtor de regras de conjuntos de classificação** | A funcionalidade do construtor de regras agora está disponível nos conjuntos de classificações. As regras são definidas no contexto de um conjunto de classificações. As regras são aplicadas (quando ativadas) a todos os conjuntos de relatórios e combinações de dimensões principais que estão inscritos no conjunto de classificações.<p>(Link para a documentação a seguir).</p> |  | sábado, 30 de janeiro de 2026 |
| **Feeds de dados aprimorados** | Os seguintes aprimoramentos estão disponíveis para feeds de dados:<ul><li>Experiência do usuário aprimorada.</li><li>Nova experiência para criar e gerenciar modelos de coluna.</li><li>Agora é possível escolher quando criar um modelo de coluna para reutilização em feeds de dados futuros. Também é possível excluir, editar e copiar modelos.<br/>Anteriormente, cada feed de dados criado resultava em um novo modelo de coluna, que resultava em um grande número de modelos de coluna não utilizados e não era possível excluí-los ou gerenciá-los.</li><li>Adicionar e filtrar por tags.</li><li>Exibir o histórico de trabalhos do feed de dados. (Quando o período de solicitação começou, quando começou, terminou e assim por diante.)</li><li>Reenviar ou reprocessar feeds de dados. (Na página Histórico de tarefas)</li><li>Permitir ocorrências de chegada tardia. Agora é possível incluir dados que chegaram depois que a tarefa de feed de dados terminou de processar dados na frequência de relatório definida.</li><li>Ao escolher uma data de término para um feed de dados, a data de término escolhida é incluída como o último dia do feed de dados.<br/>Anteriormente, a data final era excluída do feed de dados.</li><li>Uma frequência de exportação de 15 minutos agora é possível, mas não está disponível por padrão. Para que essa opção fique disponível em seu ambiente, primeiro entre em contato com o Atendimento ao cliente da Adobe e solicite que seu conjunto de relatórios seja configurado para oferecer suporte a exportações de 15 minutos.</li></ul><p>**Observação:** com essas melhorias, as URLs das páginas de feed de dados no Adobe Analytics também estão sendo atualizadas. Atualize todos os marcadores existentes para apontar para as novas páginas dos feeds de dados até 30 de abril de 2026.</p>(Link para a documentação a seguir).</p> | quarta-feira, 20 de janeiro de 2026 | quarta-feira, 10 de fevereiro de 2026 |
| **Classificar tabelas por várias colunas** | Agora é possível classificar os dados de uma tabela de forma livre por várias colunas no Analysis Workspace, sejam dimensões ou métricas.<p>Quando você classifica dados para várias colunas, os dados são classificados de acordo com a prioridade atribuída a cada coluna. A numeração de prioridade é exibida ao lado do ícone de classificação.</p><p>(Link da documentação em breve).<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | quinta-feira, 28 de janeiro de 2026 | quinta-feira, 18 de fevereiro de 2026 |
| **Serviços de mídia de streaming: suporte aos dados do cronograma** | Agora é possível fazer upload de dados agendados de conteúdo antigo de mídias de streaming ao vivo para acompanhar com mais facilidade e precisão o número de visualizadores.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |

## Correções no Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-423389, AN-422636, AN-422482, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-402523, AN-396149, AN-390990, AN-390728, AN-390646, AN-383484, AN-376980, AN-371729, AN-347570
**Classificações**: AN-423985, AN-423092, AN-423067, AN-422913, AN-422908, AN-422793, AN-422785, AN-422745, AN-422705, AN-422422, AN-422126, AN-422098, AN-422077, AN-422058, AN-421999, AN-421698, AN-421351, AN-406583, AN-406295, AN-406123, AN-406052, AN-404743, AN-404372
**Coleta de dados**: AN-422488
**Feeds de dados e Data Warehouse**: AN-423186, AN-422789, AN-422239, AN-421552, AN-421393, AN-421339, AN-421231, AN-420149, AN-406345, AN-406217, AN-405073, AN-404822, AN-404774, AN-389691
**Privacidade**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Relatórios**:
**Relatórios agendados**: AN-423087, AN-422686
**Comparação de segmentos**:
**Outros**: AN-423401, AN-422819, AN-422775, AN-422626, AN-42238, AN-422160, AN-422071, AN-421687, AN-420045, AN-404891, AN-404608, AN-390912


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Melhorias no processamento do Livestream** | quinta-feira, 14 de janeiro de 2026 | O Adobe planeja fazer melhorias e alterações na formatação das cargas do LiveStream. Essas atualizações fornecem melhor paridade entre o LiveStream e outros recursos do Adobe Analytics, como o Analysis Workspace. Um endpoint de visualização está disponível e permite testar as alterações planejadas. Consulte as [notas de versão do LiveStream] para obter a lista completa de alterações e detalhes do ponto de extremidade de visualização. O Adobe planeja uma transferência forçada para o formato de carga útil atualizado em 13 de abril de 2026. |
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
