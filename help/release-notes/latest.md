---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 20080ff877ef14ce6fead2702febe7d2b06a9283
workflow-type: tm+mt
source-wordcount: '1278'
ht-degree: 93%

---

# Notas de versão atuais do Adobe Analytics (versão de setembro de 2025)

**Última atualização**: 11 de setembro de 2025

Estas notas de versão abrangem o período de lançamento de setembro até o início de outubro de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Melhorias ao migrar projetos e componentes para o Customer Journey Analytics** | Os seguintes aprimoramentos estão disponíveis ao migrar projetos e componentes do Adobe Analytics para o Customer Journey Analytics:<ul><li>Migrar vários projetos de uma vez.<p>É possível migrar até 20 projetos de uma só vez.</p><p>Anteriormente, só era possível migrar um projeto por vez.</p></li><li>Atualize mapeamentos para dimensões e métricas que já foram mapeadas com uma migração de projeto anterior.<p>Agora é possível atualizar esses mapeamentos sempre que migrar um projeto, mesmo que as mesmas dimensões e métricas tenham sido mapeadas anteriormente em uma migração anterior.</p><p>Anteriormente, quaisquer mapeamentos escolhidos eram permanentes para todas as migrações futuras do projeto.</p></li><li>Desempenho aprimorado para organizações com um grande número de projetos.</li></ul><p>Para mais informações, consulte [Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](/help/admin/tools/component-migration/component-migration.md).</p> | 15 de setembro de 2025 | 18 de setembro de 2025 |
| **Analisar o tráfego de IA com um novo item de dimensão do Tipo Referenciador** | Um novo item de dimensão do tipo Referenciador estará disponível para ajudar a analisar o tráfego proveniente das ferramentas de IA. <p>Esse novo item de dimensão do tipo Referenciador, chamado Ferramentas de IA de conversa, agrupará domínios de referência das principais ferramentas de IA, permitindo que você analise as tendências do grupo como um todo. A lista inicial de domínios referenciadores nesta nova categoria inclui (mas não se limita a):</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>O novo item de dimensão estará disponível em todas as ferramentas relacionadas ao Adobe Analytics, incluindo Analysis Workspace, Report Builder, Data Warehouse, feeds de dados e assim por diante.</p><p>Considere o seguinte ao usar esse novo item de dimensão:</p><ul><li>Nem sempre é possível distinguir o tráfego do referenciador que veio dos resultados fornecidos no “modo IA” em um mecanismo de pesquisa daqueles que vieram de click-throughs dos resultados de pesquisa tradicionais.</li><li>O novo item de dimensão Ferramentas de IA de conversa se concentra nos principais provedores com mais tráfego. Uma nova tendência revela um número crescente de sites impostores com domínios semelhantes aos principais provedores de ferramentas de IA. Isso provavelmente se deve à facilidade com que indivíduos ou grupos podem criar suas próprias ferramentas de IA e hospedá-las na Internet. Como esse é um espaço em rápida evolução, entre em contato com a equipe de suporte da Adobe se você achar que um site popular não está incluído.</li><li>A dimensão do tipo Referenciador, incluindo o novo item de dimensão Ferramentas de IA de conversa, está disponível somente para dados processados pelo Adobe Analytics. </li></ul><p>(Link da documentação em breve).</p> |   | quinta-feira, 15 de outubro de 2025 |
| **Serviços de mídia de streaming: suporte aos dados de programação** | Agora é possível fazer upload dos dados agendados do conteúdo de streaming de mídia ao vivo anterior para rastrear as visualizações com mais facilidade e precisão.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. Você pode até coletar dados de audiência de tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo, e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>(Link da documentação em breve).<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | quinta-feira, 29 de outubro de 2025 |
| **Serviços de mídia de streaming: campos XDM atualizados para coleta de dados de mídia de streaming na Adobe Experience Platform** | Ao coletar dados de mídia de streaming na Adobe Experience Platform, os caminhos do campo XDM mostrados no cabeçalho de “Caminho de campo XDM” da documentação de parâmetros de mídia de streaming não devem mais ser usados. Em vez disso, os clientes que implementaram o conector de origem do Analytics para coletar dados de mídia de streaming na Platform antes de 9 de maio de 2025 devem migrar suas configurações para os caminhos de campo mediaReporting, conforme mostrado no cabeçalho de “Caminho de campo XDM do relatório” da documentação de parâmetros da mídia de streaming.<p> Esses caminhos de campo são encontrados nas páginas a seguir e são marcados como “Obsoletos”: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncio](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do player](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/quality-parameters). (Nenhuma ação é necessária para clientes que implementaram o conector de origem do Analytics após 9 de maio de 2025 e já estão usando somente os caminhos XDM do mediaReporting.)</p><p>A assimilação de dados nos caminhos de campo XDM obsoletos continuará até o final de outubro de 2025. Após esse período, os caminhos de campo obsoletos serão totalmente removidos e não serão mais visíveis na interface de esquema da Adobe Experience Platform, e os dados serão enviados usando somente os caminhos de campo do mediaReporting.</p><p>Para obter mais informações, consulte [Migrar uma implementação do conector de origem do Analytics para campos de mídia de streaming XDM atualizados](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Entre em contato com os serviços da Adobe Consulting ou com a equipe de conta para obter suporte à migração.  </p> |  | Outubro de 2025 |

## Correções no Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-386791, AN-380838, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Classificações**: AN-391364, AN-393014, AN-393882, AN-394346, AN-394333, AN-390201
**Coleta de dados**: AN-388127
**Feeds de dados e Data Warehouse**: AN-391243
**Privacidade**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Relatórios**: AN-392863, AN-371871, AN-393640, AN-391334
**Relatórios agendados**: AN-391150, AN-390474
**Comparação de segmentos**:
**Outros**: AN-387858, AN-393985, AN-393287


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Report Builder legado** | 18 de junho de 2025 | O complemento do Report Builder legado será removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](/help/analyze/report-builder/rb-overview.md). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](/help/analyze/report-builder/convert-workbooks.md#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **Acesso via domínios herdados ou via SSO herdado** | 10 de abril de 2025 | A Adobe planeja atualizar como os usuários acessam o Adobe Analytics para melhorar a segurança e simplificar a sua experiência de logon. Como parte dessa iniciativa, o acesso por meio de domínios herdados ou de um SSO herdado, incluindo `my.omniture.com`, será descontinuado permanentemente em **2 de janeiro de 2026**. Após essa data, as credenciais de logon herdadas e o SSO herdado não funcionarão mais. Todos os usuários precisarão fazer logon via `experience.adobe.com`, usando suas IDs da Adobe Experience Cloud. Se precisar de assistência com o sua ID da Experience Cloud, entre em contato com o administrador do Adobe Analytics da sua organização ou com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/contact.html). |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de versão anteriores para 2025](/help/release-notes/2025.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
