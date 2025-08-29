---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Analytics (versão de agosto de 2025)

**Última atualização**: 13 de agosto de 2025

Essas notas de versão abrangem o período de lançamento de 13 de agosto a 16 de setembro de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analisar o tráfego de IA com um novo item de dimensão do Tipo Referenciador** | Em outubro, um novo item de dimensão do tipo Referenciador estará disponível para ajudar a analisar o tráfego proveniente das ferramentas de IA. <p>Esse novo item de dimensão do tipo Referenciador, chamado Ferramentas de IA de conversa, agrupará domínios de referência das principais ferramentas de IA, permitindo que você analise as tendências do grupo como um todo. A lista inicial de domínios referenciadores nesta nova categoria inclui (mas não se limita a):</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>O novo item de dimensão estará disponível em todas as ferramentas relacionadas ao Adobe Analytics, incluindo Analysis Workspace, Report Builder, Data Warehouse, feeds de dados e assim por diante.</p><p>Considere o seguinte ao usar esse novo item de dimensão:</p><ul><li>Nem sempre é possível distinguir o tráfego do referenciador que veio dos resultados fornecidos no “modo IA” em um mecanismo de pesquisa daqueles que vieram de click-throughs dos resultados de pesquisa tradicionais.</li><li>O novo item de dimensão Ferramentas de IA de conversa se concentra nos principais provedores com mais tráfego. Uma nova tendência revela um número crescente de sites impostores com domínios semelhantes aos principais provedores de ferramentas de IA. Isso provavelmente se deve à facilidade com que indivíduos ou grupos podem criar suas próprias ferramentas de IA e hospedá-las na Internet. Como esse é um espaço em rápida evolução, entre em contato com a equipe de suporte da Adobe se você achar que um site popular não está incluído.</li><li>A dimensão do tipo Referenciador, incluindo o novo item de dimensão Ferramentas de IA de conversa, está disponível somente para dados processados pelo Adobe Analytics. </li></ul><p>(Link da documentação em breve).</p> |   | Outubro de 2025 |
| **Projetos baixados como PDFs são baixados na sua estação de trabalho** | Ao baixar um projeto como PDF, ele é enviado para a pasta de downloads na sua estação de trabalho.  <p>Anteriormente, o download de um projeto como PDF iniciava o PDF em uma nova guia do navegador com um URL exclusivo. </p><p>Para obter mais informações, consulte [Baixar projetos e dados](/help/analyze/analysis-workspace/curate-share/download-send.md)</p> |  | 25 de agosto de 2025 |
| **Os projetos excluídos ficam imediatamente indisponíveis por URL e são excluídos das entregas agendadas** | Os projetos excluídos são imediatamente excluídos das entregas agendadas e não podem mais ser acessados pelo URL.<p>Anteriormente, os projetos eram incluídos em entregas agendadas e podiam ser acessados com seus URLs por 60 dias após a exclusão.</p><p>Para obter mais informações sobre como excluir projetos, consulte [Visão geral de projetos](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Final de agosto de 2025 |
| **Serviços de mídia de streaming: campos XDM atualizados para coleta de dados de mídia de streaming na Adobe Experience Platform** | Ao coletar dados de mídia de streaming na Adobe Experience Platform, os caminhos do campo XDM mostrados no cabeçalho de “Caminho de campo XDM” da documentação de parâmetros de mídia de streaming não devem mais ser usados. Em vez disso, os clientes que implementaram o conector de origem do Analytics para coletar dados de mídia de streaming na Platform antes de 9 de maio de 2025 devem migrar suas configurações para os caminhos de campo mediaReporting, conforme mostrado no cabeçalho de “Caminho de campo XDM do relatório” da documentação de parâmetros da mídia de streaming.<p> Esses caminhos de campo são encontrados nas páginas a seguir e são marcados como “Obsoletos”: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncio](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do player](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/quality-parameters). (Nenhuma ação é necessária para clientes que implementaram o conector de origem do Analytics após 9 de maio de 2025 e já estão usando somente os caminhos XDM do mediaReporting.)</p><p>A assimilação de dados nos caminhos de campo XDM obsoletos continuará até o final de outubro de 2025. Após esse período, os caminhos de campo obsoletos serão totalmente removidos e não serão mais visíveis na interface de esquema da Adobe Experience Platform, e os dados serão enviados usando somente os caminhos de campo do mediaReporting.</p><p>Para obter mais informações, consulte [Migrar uma implementação do conector de origem do Analytics para campos de mídia de streaming XDM atualizados](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Entre em contato com os serviços da Adobe Consulting ou com a equipe de conta para obter suporte à migração.  </p> |  | Outubro de 2025 |

## Correções no Adobe Analytics

**Activity Map**: AN-389205; AN-384186
**Analysis Workspace**: AN-390102; AN-389066; AN-388841; AN-388687; AN-388478; AN-387089; AN-387044; AN-384560; AN-379213; AN-351639
**Classificações**: AN-390442; AN-390385; AN-389953; AN-389703; AN-389321; AN-389116; AN-388833; AN-388717; AN-387987; AN-383329
**Coleção de dados**: AN-389320
**Feeds de dados e Data Warehouse**: AN-389702; AN-388136; AN-387779; AN-384369; AN-383075; AN-380307
**Privacidade**:
**Report Builder**: AN-389336; AN-382775
**Relatórios**: AN-390398
**Relatórios agendados**:
**Comparação de segmentos**:
**Outros**: AN-388180; AN-383164; AN-366532


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Report Builder legado** | 18 de junho de 2025 | O complemento do Report Builder legado será removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/report-builder/rb-overview). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **Acesso via domínios herdados ou via SSO herdado** | 10 de abril de 2025 | A Adobe planeja atualizar como os usuários acessam o Adobe Analytics para melhorar a segurança e simplificar a sua experiência de logon. Como parte dessa iniciativa, o acesso por meio de domínios herdados ou de um SSO herdado, incluindo `my.omniture.com`, será descontinuado permanentemente em **2 de janeiro de 2026**. Após essa data, as credenciais de logon herdadas e o SSO herdado não funcionarão mais. Todos os usuários precisarão fazer logon via `experience.adobe.com`, usando suas IDs da Adobe Experience Cloud. Se precisar de assistência com o sua ID da Experience Cloud, entre em contato com o administrador do Adobe Analytics da sua organização ou com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/contact.html). |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de versão anteriores para 2025](/help/release-notes/2025.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão dos serviços de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
