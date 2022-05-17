---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 31387d369428727a486a19b986bf9d891a36e714
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 86%

---

# Notas de versão atuais do Adobe Analytics (maio de 2022)

**Última atualização**: 17 de maio de 2022

>[!NOTE]
>
>Esta página contém informações de pré-lançamento e está sujeita a alterações.

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

## Novos recursos no Adobe Analytics

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Nenhum recurso novo este mês | N/D | N/D |

{style=&quot;table-layout:auto&quot;}

### Correções no Adobe Analytics

(Correções para vários clientes)

N/D

### Outras correções no Adobe Analytics

(Correções para clientes individuais)

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualização SFTP** | 9 de maio de 2022 | Anteriormente, informamos que o Adobe atualizaria seus serviços de Protocolo de transferência segura de arquivo (SFTP) em maio de 2022 para oferecer segurança aprimorada para transferência de arquivos. Adiamos essa atualização para o verão de 2022. Quando essa alteração ocorrer, determinadas configurações de cliente SFTP não serão mais suportadas. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| **Direito do Cross-Device Analytics (CDA)** | 13 de abril de 2022 | Efetivo **1 de maio de 2022**, quaisquer novas implementações de [CDA](/help/components/cda/overview.md) são limitadas a três IDs de conjunto de relatórios (RSIDs) por cliente. |
| **Alteração no modo como o Adobe Analytics lida com dados do A4T coletados pelo Experience Edge** | 31 de março de 2022 | Em 7 de março de 2022, o Analytics alterou a maneira como lida com algumas chamadas provenientes do Experience Edge que incluem conteúdo do Target destinado aos relatórios do Analytics for Target (A4T). A partir de 7 de março, todas as ocorrências com conteúdo de relatório do A4T foram modificadas para não serem tratadas como Exibição de página ou Eventos de link. A partir de **31 de março de 2022**, a lógica se tornou mais seletiva para que os eventos padrão de Exibição de página e Clique não sejam modificados. A partir de agora, os únicos eventos que serão modificados serão chamadas somente de personalização que contenham apenas conteúdo do A4T. |
| **Atualização de métodos de criptografia de navegador compatíveis de determinados clientes** | 28 de março de 2022 | A Adobe oferece dois níveis de segurança de criptografia para atender às diversas necessidades de segurança do cliente na coleta de dados primários. Em **23 de junho de 2022**, removeremos o suporte para determinados algoritmos de criptografia HTTPS, conhecidos como cifras, para clientes com o nível de segurança definido como “Alto”. Essa ação significa que alguns sistemas operacionais mais antigos não poderão mais enviar dados para o Analytics porque eles não são compatíveis com métodos de criptografia modernos. Os clientes que usam as configurações de segurança de criptografia “Padrão” não serão afetados. Todos os clientes que atualmente usam a configuração “Alto” já foram contatados diretamente. Uma lista detalhada das cifras afetadas por essa alteração pode ser encontrada aqui. |
| **Pausa em relatórios agendados mais antigos** | 12 de abril de 2022 | A partir de **20 de abril de 2022**, a Adobe pretende pausar todos os relatórios agendados com uma data de criação superior a dois anos (criados antes de 31 de janeiro de 2020). Nenhum relatório ou dado é excluído. Somente os relatórios identificados como tendo mais de dois anos serão pausados, e nenhum relatório agendado adicional será enviado. Saiba mais |
| **Atualizações da região ISO 2022** | 11 de março de 2021 | A Adobe planeja realizar as atualizações da região ISO 2022 em **10 de junho de 2022**. Você poderá ver pequenas atualizações de informações geográficas após esta versão. |
| **Pausa de tarefas agendadas mais antigas do Report Builder** | 12 de abril de 2022 | A partir de **20 de abril de 2022**, a Adobe pretende pausar todas as tarefas agendadas do Report Builder que foram criadas há mais de dois anos. Essa pausa se aplica especificamente a qualquer tarefa criada antes de 31 de janeiro de 2020. Nenhuma tarefa, pasta de trabalho ou dado é excluído. No entanto, as tarefas identificadas como tendo mais de dois anos serão pausadas e nenhuma tarefa agendada adicional será enviada. Saiba mais |
| **Expiração de lista de permissões de extensão EOL para integrações OAuth/JWT herdadas do Analytics** | 14 de janeiro de 2022 | Em **25 de maio de 2022**, a [API do Analytics 1.3, a API SOAP 1.4 e a extensão de lista de permissões do Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) herdadas expirará. Ela era fornecida para que os clientes que usavam credenciais herdadas do [!DNL Adobe Analytics] OAuth/JWT tivessem mais tempo para migrar suas integrações de clientes para as [credenciais do Adobe IMS](https://developer.adobe.com/console). Essa expiração afeta (mas não se limita a) clientes [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] que não concluíram as migrações de IMS necessárias. Atualmente, os clientes que estão usando as credenciais OAuth/JWT do [!DNL Analytics] herdadas por meio da extensão da lista de permissões e que não concluírem a migração para credenciais do IMS até o dia 25 de maio de 2022, perderão o acesso aos serviços da Adobe. Os clientes do Livestream podem se referir a essas [instruções](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) ao migrar seus aplicativos de clientes para as credenciais IMS. [!DNL Campaign] os clientes podem entrar em contato com a equipe da conta da Adobe para saber como atualizar para a versão mais recente do [!DNL Campaign]. |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

