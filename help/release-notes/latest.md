---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 77a83fdb8d805f8a3ca6128a9a0d3628833eb863
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 77%

---

# Notas de versão atuais do Adobe Analytics (fevereiro de 2022)

**Última atualização**: 25 de fevereiro de 2022

Saiba mais sobre as atualizações de versão mais recentes para [produtos Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html). Obtenha a documentação de autoajuda, os tutoriais e os cursos mais recentes da Experience League.

## Novos recursos no Adobe Analytics {#aa-features}

| Recurso | Descrição | [Data alvo](releases.md) |
| ----------- | ---------- | ------- |
| Modo de visualização do projeto do cartão de pontuação para dispositivos móveis | Inicie uma visualização de como o cartão de pontuação para dispositivos móveis ficará no aplicativo de painéis do Analytics, diretamente do construtor do cartão de pontuação. O modo de visualização permite que os usuários interajam com filtros e gráficos da mesma forma que fazem no aplicativo, permitindo que visualizem a experiência antes de salvarem e compartilharem o cartão de pontuação. Os usuários também podem usar o seletor de dispositivos no modo de visualização para ver como o cartão de pontuação será exibido em diferentes dispositivos. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=pt-BR#preview) | 16 de fevereiro de 2022 |
| Ponto de extremidade de projetos de API | Adicione, edite ou exclua projetos da Analysis Workspace usando a API. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 1 de fevereiro de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Correção de vários problemas com o [!UICONTROL Uso de chamadas do servidor]. (AN-279134, AN-279878, AN-280802, AN-279097, AN-191284, AN-269720)
* Correção de um problema que fazia com que o Data Warehouse exportasse arquivos CSV vazios. (AN-280291)
* Correção de um problema que fazia com que nomes de audiência não fossem preenchidos em segmentos recentes. (AN-279715)
* Correção de um problema com tempos lentos de relatório. (AN-280055)
* Correção de problemas com Classificações que não classificavam todos os itens de dimensão. (AN-280031)

### Outras correções no Adobe Analytics

AN-268093, AN-273820, AN-274435, AN-274904, AN-275356, AN-275947, AN-276160, AN-276258, AN-276705, AN-277051, AN-277957, AN-278693, AN-278882, AN-279000, AN-279046, AN-279362, AN-279460, AN-279488, AN-279554, AN-279572, AN-279663, AN-279755, AN-279825, AN-280002, AN-280013, AN-280019, AN-280033, AN-280086, AN-280232, AN-280264, AN-280288, AN-280342, AN-280347, AN-280360, AN-280370, AN-280724, AN-280830, AN-280941, AN-281353, AN-281424, AN-281533

## Avisos importantes para administradores do [!DNL Analytics]

**Atualizado em 25 de janeiro de 2022**

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| Alteração de como o Analytics lida com dados A4T coletados pelo Experience Edge | 25 de fevereiro de 2022 | Ligado **8 de março de 2022**, alteraremos a forma como lidamos com alguns dados relacionados ao Target enviados para o Adobe Analytics pelo Experience Edge. Ao usar o SDK da Web da Adobe Experience Platform com o Analytics e o Target, alguns eventos de personalização eram contados em [!DNL Adobe Analytics] as [!UICONTROL Exibições de página]. Isso resultou em contagens inflacionadas de exibições de página e chamadas de servidor adicionais. Com a alteração, as chamadas de personalização sem conteúdo do Analytics serão desconsideradas. As chamadas de personalização com dados A4T registrarão os dados do A4T, mas não serão registradas como chamadas de servidor faturáveis, nem afetarão as exibições de página ou as métricas de evento do link. |
| Pausando tarefas Report Builder agendadas mais antigas | 24 de fevereiro de 2022 | **Em vigor em 15 de abril de 2022**, o Adobe pretende pausar todas as tarefas Report Builder programadas que foram criadas há mais de dois anos. Especificamente, essa pausa se aplica a qualquer tarefa criada antes de 31 de janeiro de 2020. Nenhuma tarefa, pasta de trabalho ou dados será excluída. No entanto, as tarefas identificadas como com mais de dois anos serão pausadas e nenhuma tarefa agendada adicional será enviada. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Expiração de lista de permissões de extensão EOL para integrações OAuth/JWT herdadas do Analytics | 14 de janeiro de 2022 | Em **25 de maio de 2022**, a [API do Analytics 1.3, a API SOAP 1.4 e a extensão de lista de permissões do Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) herdado irá expirar. Ela era fornecida para que os clientes que usavam credenciais herdadas do [!DNL Adobe Analytics] OAuth/JWT tivessem mais tempo para migrar suas integrações de clientes para as [credenciais do Adobe IMS](https://developer.adobe.com/console). Essa expiração afeta (mas não se limita a) [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] clientes que não concluíram as migrações de IMS necessárias. Atualmente, os clientes que estão usando as [!DNL Analytics] credenciais OAuth/JWT herdadas por meio da extensão da lista de permissões e que não concluírem a migração para credenciais do IMS até o dia 25 de maio de 2022, perderão o acesso aos serviços da Adobe. Os clientes do Livestream podem se referir a essas [instruções](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) ao migrar seus aplicativos de clientes para as credenciais IMS. [!DNL Campaign] os clientes podem entrar em contato com a equipe da conta da Adobe para saber como atualizar para a versão mais recente do [!DNL Campaign]. |
| Fim da vida útil do [!DNL Reports & Analytics] | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |
| Atualização de serviços do Protocolo de transferência segura de arquivo (SFTP) | 13 de janeiro de 2022 | Em **2 de maio de 2022**, o [!DNL Adobe Analytics] atualizará os seus serviços de Protocolo de transferência segura de arquivo (SFTP) para oferecer maior segurança às transferências de arquivos. Com essa alteração, não haverá mais suporte para algumas configurações de cliente SFTP. Também adicionaremos algumas opções de conexão que estarão disponíveis em **1 de março de 2022**. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |

## AppMeasurement {#appm}

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] notas de versão](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
