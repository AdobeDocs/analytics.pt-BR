---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 80e7241fd35e5c745c2341182983613f537ce224
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 32%

---

# Notas de versão atuais do Adobe Analytics (abril de 2022)

**Last update**: April 20, 2022

* For March 2022 release notes, go [here](/help/release-notes/2022.md).

* For Customer Journey Analytics release notes, go [here](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR).

* Para obter as notas de versão do Media Analytics, acesse [here](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en).

* Saiba mais sobre as atualizações de versão mais recentes para [produtos Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html). Obtenha a documentação de autoajuda, os tutoriais e os cursos mais recentes da Experience League.

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Adobe Analytics landing page updates | Atualizações na página de aterrissagem conjunta do Workspace/Reports &amp; Analytics que melhora a usabilidade e a facilidade de navegação. [Saiba mais](/help/analyze/landing.md) | 20 de abril de 2022 |
| [!UICONTROL Próximo item] ou [!UICONTROL Item anterior] Painel Área de trabalho | O [!UICONTROL Item seguinte ou anterior] permite explorar itens que seguem ou precedem um item de dimensão de sua escolha. For example, use it if you want to see the next or previous pages to a specific product page, or marketing channel, or even device type. This panel goes beyond legacy next/previous reporting because it allows you to look at any dimension and does not require any new implementation to get insights. [Saiba mais](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 20 de abril de 2022 |
| [!UICONTROL Resumo da página] Painel Área de trabalho | O [!UICONTROL Resumo da página] O painel fornece uma análise detalhada para uma página de sua escolha. Ela fornece os mesmos detalhes que os Relatórios e análises herdados [!UICONTROL Resumo da página] , mais muito mais. [Saiba mais](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 20 de abril de 2022 |
| Requisito de `x-proxy-global-company-id` cabeçalho para chamadas de API 2.0 | As APIs do Adobe Analytics 2.0 não exigem mais o `x-proxy-global-company-id` , já que essas informações fazem parte do URL do ponto de extremidade. You can still include this header, but you no longer get an error if it is missing. | 20 de abril de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Fixed an issue in Data Feeds, where the Start and End Dates changed automatically after saving the Data Feed when creating from Data Feed UI. The dates were updating themselves by 1 day. (AN-281262)

* Correção de um problema que impedia a renovação de projetos agendados por link de email. (AN-283622)

### Outras correções no Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761;

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Cross-Device Analytics (CDA) entitlement** | 13 de abril de 2022 | Efetivo **1 de maio de 2022**, qualquer nova implementação de [CDA](/help/components/cda/overview.md) são limitadas a três IDs de conjunto de relatórios (RSIDs) por cliente. |
| **Alteração na forma como o Adobe Analytics processa os dados do A4T coletados pelo Experience Edge** | March 31, 2022 | Em 7 de março de 2022, o Analytics alterou a maneira como manipula algumas chamadas provenientes do Experience Edge que incluem o conteúdo do Target destinado aos relatórios do Analytics for Target (A4T). A partir de 7 de março, todas as ocorrências com conteúdo de relatório A4T serão modificadas para não serem tratadas como Exibição de página ou Eventos de link. Starting **March 31, 2022**, the logic is more selective so that standard Page View and Click events are not modified. A partir de agora, os únicos eventos modificados são chamadas somente de personalização que têm apenas conteúdo A4T. |
| **Atualização de métodos de criptografia de navegador compatíveis com determinados clientes** | March 28, 2022 | Adobe offers two cipher security levels to meet varying customer needs for security on first-party data collection. Ligado **23 de junho de 2022** O suporte é removido para determinados algoritmos de criptografia HTTPS, conhecidos como cifras, para clientes com seu nível de segurança definido como &quot;Alto&quot;. This action means that some older operating systems are no longer be able to send data to Analytics because they do not support modern encryption methods. Clientes que usam as configurações padrão de segurança de criptografia &quot;Padrão&quot; não são afetados. All customers currently using the “High” setting have already been contacted directly. A detailed list of the ciphers affected by this change can be found here. |
| **Pausing older scheduled reports** | 12 de abril de 2022 | Efetivo **20 de abril de 2022**, o Adobe pretende pausar todos os relatórios agendados com uma data de criação superior a dois anos (criados antes de 31 de janeiro de 2020). Nenhum relatório ou dado é excluído. Somente os relatórios identificados como com mais de dois anos são pausados e nenhum relatório agendado adicional é enviado. Saiba mais |
| **Atualizações da região ISO 2022** | 11 de março de 2021 | Adobe plans to perform 2022 ISO region updates on **June 10, 2022**. Espera-se ver pequenas atualizações de informações geográficas após esta versão. |
| **Pausa de tarefas agendadas mais antigas do Report Builder** | 12 de abril de 2022 | Effective **April 20, 2022**, Adobe intends to pause all scheduled Report Builder tasks that were created more than two years ago. Essa pausa se aplica especificamente a qualquer tarefa criada antes de 31 de janeiro de 2020. Nenhuma tarefa, pasta de trabalho ou dados é excluída. No entanto, as tarefas identificadas como com mais de dois anos são pausadas e nenhuma tarefa agendada adicional é enviada. Saiba mais |
| **Expiração de lista de permissões de extensão EOL para integrações OAuth/JWT herdadas do Analytics** | 14 de janeiro de 2022 | Ligado **25 de maio de 2022**, o [API do Analytics 1.3, API SOAP 1.4 e EOL herdado do Analytics OAuth/JWT](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) lista de permissões extensão de  expira. Ela era fornecida para que os clientes que usavam credenciais herdadas do [!DNL Adobe Analytics] OAuth/JWT tivessem mais tempo para migrar suas integrações de clientes para as [credenciais do Adobe IMS](https://developer.adobe.com/console). Essa expiração afeta (mas não se limita a) [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] clientes que não concluíram as migrações de IMS necessárias. Clientes que estão usando o herdado no momento [!DNL Analytics] As credenciais do OAuth/JWT por meio da extensão da  de lista de permissões e que não concluírem a migração para credenciais do IMS até 25 de maio de 2022 perderão o acesso aos serviços da Adobe. Os clientes do Livestream podem se referir a essas [instruções](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) ao migrar seus aplicativos de clientes para as credenciais IMS. [!DNL Campaign] os clientes podem entrar em contato com a equipe da conta da Adobe para saber como atualizar para a versão mais recente do [!DNL Campaign]. |
| **Fim da vida útil do[!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] notas de versão](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
