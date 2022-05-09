---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 43869c683ca30c94157c6822b53f02a917f6e3ff
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 95%

---

# Notas de versão atuais do Adobe Analytics (abril de 2022)

**Última atualização**: 9 de maio de 2022

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

## Novos recursos no Adobe Analytics

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Página de aterrissagem do Adobe Analytics | Atualizações na página de aterrissagem conjunta do Espaço de trabalho/Reports &amp; Analytics que melhoram a usabilidade e a facilidade de navegação. [Saiba mais](/help/analyze/landing.md) | 20 de abril de 2022 |
| [!UICONTROL Próximo item] ou [!UICONTROL Item anterior] no painel Espaço de trabalho | O painel [!UICONTROL Próximo item ou Item anterior] permite explorar itens que seguem ou precedem um item de dimensão de sua escolha. Por exemplo, use-o se desejar visualizar as páginas anteriores ou seguintes de uma página de produto específica, de um canal de marketing ou até mesmo de um tipo de dispositivo. Esse painel vai além dos relatórios legados anteriores/seguintes, pois permite que você analise qualquer dimensão e não exige nenhuma nova implementação para obter insights. [Saiba mais](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 20 de abril de 2022 |
| [!UICONTROL Resumo da página] no painel Espaço de trabalho | O painel [!UICONTROL Resumo da página] fornece uma análise detalhada de uma página de sua escolha. Ele fornece os mesmos detalhes que o relatório [!UICONTROL Resumo da página] do Reports &amp; Analytics e muito mais. [Saiba mais](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 20 de abril de 2022 |
| Removido o requisito de cabeçalho `x-proxy-global-company-id` para chamadas de API 2.0 | As APIs do Adobe Analytics 2.0 não exigem mais o cabeçalho `x-proxy-global-company-id`, já que essas informações fazem parte do URL do endpoint. Você ainda pode incluir esse cabeçalho, mas não receberá mais um erro se ele estiver ausente. | 20 de abril de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Correção de um problema nos feeds de dados, em que as datas de início e término eram alteradas automaticamente após salvar o feed de dados ao criar a partir da interface do feed de dados. As datas estavam sendo atualizadas em 1 dia. (AN-281262)
* Correção de um problema que impedia a renovação de projetos agendados por link de email. (AN-283622)
* Correção de um problema que fazia com que versões recentes do Apple Safari e do Microsoft Edge não fossem identificadas corretamente na tabela de pesquisa do tipo de navegador da Adobe. Semelhante a quando [as versões do navegador são atualizadas](/help/components/dimensions/browser.md), as atualizações das tabelas de pesquisa do tipo de navegador corrigem apenas os dados daquele ponto em diante. As tabelas de pesquisa da versão do navegador foram atualizadas em 20 de abril e as tabelas de pesquisa do tipo de navegador foram atualizadas em 28 de abril. (AN-284872; AN-285753; AN-286257)

### Outras correções no Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualização SFTP** | 9 de maio de 2022 | Anteriormente, informamos que o Adobe atualizaria seus serviços de Protocolo de transferência segura de arquivo (SFTP) em maio de 2022 para oferecer segurança aprimorada para transferência de arquivos. Adiamos essa atualização para o verão de 2022. Quando essa alteração ocorrer, determinadas configurações de cliente SFTP não serão mais suportadas. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| **Direito do Cross-Device Analytics (CDA)** | 13 de abril de 2022 | A partir de **1 de maio de 2022**, qualquer nova implementação do [CDA](/help/components/cda/overview.md) será limitada a no máximo três IDs de conjunto de relatórios (RSIDs) por cliente. |
| **Alteração no modo como o Adobe Analytics lida com dados do A4T coletados pelo Experience Edge** | 31 de março de 2022 | Em 7 de março de 2022, o Analytics alterou a maneira como lida com algumas chamadas provenientes do Experience Edge que incluem conteúdo do Target destinado aos relatórios do Analytics for Target (A4T). A partir de 7 de março, todas as ocorrências com conteúdo de relatório do A4T foram modificadas para não serem tratadas como Exibição de página ou Eventos de link. A partir de **31 de março de 2022**, a lógica se tornou mais seletiva para que os eventos padrão de Exibição de página e Clique não sejam modificados. A partir de agora, os únicos eventos que serão modificados serão chamadas somente de personalização que contenham apenas conteúdo do A4T. |
| **Atualização de métodos de criptografia de navegador compatíveis de determinados clientes** | 28 de março de 2022 | A Adobe oferece dois níveis de segurança de criptografia para atender às diversas necessidades de segurança do cliente na coleta de dados primários. Em **23 de junho de 2022**, removeremos o suporte para determinados algoritmos de criptografia HTTPS, conhecidos como cifras, para clientes com o nível de segurança definido como “Alto”. Essa ação significa que alguns sistemas operacionais mais antigos não poderão mais enviar dados para o Analytics porque eles não são compatíveis com métodos de criptografia modernos. Os clientes que usam as configurações de segurança de criptografia “Padrão” não serão afetados. Todos os clientes que atualmente usam a configuração “Alto” já foram contatados diretamente. Uma lista detalhada das cifras afetadas por essa alteração pode ser encontrada aqui. |
| **Pausa em relatórios agendados mais antigos** | 12 de abril de 2022 | A partir de **20 de abril de 2022**, a Adobe pretende pausar todos os relatórios agendados com uma data de criação superior a dois anos (criados antes de 31 de janeiro de 2020). Nenhum relatório ou dado é excluído. Somente os relatórios identificados como tendo mais de dois anos serão pausados, e nenhum relatório agendado adicional será enviado. Saiba mais |
| **Atualizações da região ISO 2022** | 11 de março de 2021 | A Adobe planeja realizar as atualizações da região ISO 2022 em **10 de junho de 2022**. Você poderá ver pequenas atualizações de informações geográficas após esta versão. |
| **Pausa de tarefas agendadas mais antigas do Report Builder** | 12 de abril de 2022 | A partir de **20 de abril de 2022**, a Adobe pretende pausar todas as tarefas agendadas do Report Builder que foram criadas há mais de dois anos. Essa pausa se aplica especificamente a qualquer tarefa criada antes de 31 de janeiro de 2020. Nenhuma tarefa, pasta de trabalho ou dado é excluído. No entanto, as tarefas identificadas como tendo mais de dois anos serão pausadas e nenhuma tarefa agendada adicional será enviada. Saiba mais |
| **Expiração de lista de permissões de extensão EOL para integrações OAuth/JWT herdadas do Analytics** | 14 de janeiro de 2022 | Em **25 de maio de 2022**, a [API do Analytics 1.3, a API SOAP 1.4 e a extensão de lista de permissões do Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) herdadas expirará. Ela era fornecida para que os clientes que usavam credenciais herdadas do [!DNL Adobe Analytics] OAuth/JWT tivessem mais tempo para migrar suas integrações de clientes para as [credenciais do Adobe IMS](https://developer.adobe.com/console). Essa expiração afeta (mas não se limita a) clientes [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] que não concluíram as migrações de IMS necessárias. Atualmente, os clientes que estão usando as credenciais OAuth/JWT do [!DNL Analytics] herdadas por meio da extensão da lista de permissões e que não concluírem a migração para credenciais do IMS até o dia 25 de maio de 2022, perderão o acesso aos serviços da Adobe. Os clientes do Livestream podem se referir a essas [instruções](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) ao migrar seus aplicativos de clientes para as credenciais IMS. [!DNL Campaign] os clientes podem entrar em contato com a equipe da conta da Adobe para saber como atualizar para a versão mais recente do [!DNL Campaign]. |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] notas de versão](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
