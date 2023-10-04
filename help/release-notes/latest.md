---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5785629376b8ae528535629a77a29dcdd2ca80b8
workflow-type: tm+mt
source-wordcount: '1215'
ht-degree: 58%

---

# Notas de versão atuais do Adobe Analytics (outubro de 2023)

**Última atualização**: 4 de outubro de 2023

As notas de versão de outubro abrangem o período de 4 de outubro de 2023 a 25 de outubro de 2023. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Novas colunas disponíveis ao gerenciar componentes** | As novas colunas a seguir estão disponíveis ao gerenciar componentes:<ul><li>Usado em<p>Essa coluna está disponível no [Gerenciador de métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) e a variável [Gerenciador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Última utilização<p>Essa coluna está disponível no [Gerenciador de métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), o [Gerenciador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md), e o [Gerenciador de alertas](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>Essas informações podem ajudar a determinar se um componente é relevante para usuários(as) em sua organização, onde é usado e se precisa ser excluído ou modificado. É possível usar o Dicionário de dados junto com essas informações para ajudar a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> | 20 de setembro de 2023 | 4 de outubro de 2023 |
| **Melhorias no Gerenciador de atividades de relatórios** | O Gerenciador de atividades de relatórios permite ver a capacidade de gerar relatórios para cada conjunto de relatórios na sua organização.  Ele oferece aos administradores visibilidade detalhada do consumo de relatórios, a fim de diagnosticar e corrigir problemas de capacidade facilmente durante os horários de pico de relatórios. Veja a seguir alguns dos aprimoramentos disponíveis no Gerenciador de atividades de relatórios: <ul><li>Restringir solicitações subsequentes: além de cancelar solicitações atuais, os administradores agora podem restringir solicitações por um período definido. Os administradores podem restringir solicitações por Solicitação, Projeto e Usuário.</li><li>Além das métricas de Utilização e Capacidade, o Gerente de atividades de relatórios agora inclui mais dados sobre a atividade de relatórios: coluna Complexidade, coluna Usuário e coluna Conexão.</li><li>Todos os cancelamentos e restrições feitos no Gerenciador de atividades de relatórios agora estão visíveis no Log de auditoria. Os administradores podem usar o Log de auditoria para visualizar o que está cancelado no momento. Os cancelamentos não podem ser revertidos no Gerenciador de atividades de relatórios ou no Log de auditoria.</li></ul>Saiba mais (em breve) | 17 de outubro de 2023 | 23 de outubro de 2023 |
| **Melhorias no Data Warehouse** | Ao criar uma solicitação do Data Warehouse, agora é possível configurar uma conta na nuvem para usar como destino do relatório. Os seguintes tipos de conta de nuvem estão disponíveis para enviar dados:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Email (esta opção estava disponível anteriormente)</li></ul>FTP, SFTP, Azure Blob e S3 ainda estão disponíveis como destinos de relatório, mas não são mais recomendados.<p>A experiência do usuário ao criar e gerenciar solicitações do Data Warehouse também foi aprimorada. Para obter mais informações, consulte [Criar uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) e [Gerenciar solicitações do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=pt-BR). | 12 de setembro de 2023 | 25 de outubro de 2023 |
| **Migrar projetos do Adobe Analytics e quaisquer componentes incluídos para o Customer Journey Analytics** | Agora você pode migrar seus projetos do Adobe Analytics para o Customer Journey Analytics. Esse processo simplifica a transição do Adobe Analytics para o Customer Journey Analytics. Ao migrar projetos para o Customer Journey Analytics, os ativos são mapeados de um conjunto de relatórios do Adobe Analytics para uma visualização de dados do Customer Journey Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | 11 de outubro de 2023 | 25 de outubro de 2023 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção de problemas em que os relatórios do A4T não apareciam na interface do usuário do Target/Analytics. (AN-329375, AN-329745, AN-330026)

AN-313983; AN-324189; AN-325095; AN-325677; AN-325886; AN-326068; AN-326360; AN-326458; AN-327290; AN-327315; AN-327353; AN-327505; AN-327589; AN-327609; AN-327922; AN-328110; AN-32822; AN-328261; AN-328496; AN-328577; AN-328629; AN-328736; AN-328888; AN-328899; AN-328902; AN-328921; AN-328958; AN-329208; AN-329277; AN-32932; AN-329334; AN-329335; AN-329336; AN-329357; AN-329385; AN-329387; AN-329397; AN-329463; AN-329501; AN-329504; AN-329505; AN-329515; AN-329524; AN-329526; AN-329534; AN-329539; AN-329541; AN-329543; AN-329545; AN-329564; AN-329570; AN-329623; AN-329624; AN-329636; AN-329646; AN-329647; AN-329668; AN-329701; AN-329737; AN-329741; AN-329751; AN-329812; AN-329813; AN-329821; AN-329824; AN-329833; AN-329848; AN-329852; AN-329861; AN-329863; AN-329874; AN-329882; AN-329911; AN-329917; AN-329942; AN-329954; AN-329968; AN-329971; AN-329982; AN-330044; AN-330052; AN-330131; AN-330132; AN-330230; AN-330352; AN-330367; AN-330541; AN-330599

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Ofuscação de IP completo para ocorrências do Adobe Experience Edge** | 27 de setembro de 2023 | A ofuscação de IP para ocorrências provenientes do Experience Edge será atualizada posteriormente em outubro de 2023. Em abril, a Experience Edge adicionou a capacidade de ofuscar endereços IP. Na época, o Adobe Analytics só oferecia suporte à ofuscação parcial de IPs, devido à forma como o Analytics processa ocorrências do Experience Edge. Quando os clientes optavam pela ofuscação completa para o Experience Edge, o Analytics recebia apenas IPs parcialmente ofuscados. Quando essa alteração for implementada, o Analytics receberá o IP totalmente ofuscado. |
| **Livestream do Adobe Analytics - APIs do Analytics 2.0** | 27 de setembro de 2023 | Os clientes agora podem acessar o [Guia de endpoint para Livestream do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) nas APIs do Adobe Analytics 2.0, em vez de no local anterior, com as APIs 1.4. Observe que os clientes que usam as credenciais de JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor do Adobe I/O OAuth até 1º de janeiro de 2025. (Consulte os detalhes em Avisos de fim de vida útil abaixo.) |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 7 de março de 2023 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil.<p>Em 31 de dezembro de 2023, encerraremos muitos dos recursos associados do Reports &amp; Analytics, incluindo, entre outros: Relatórios agendados, Extrações de dados e Relatórios DL. Após 31 de dezembro de 2023, os relatórios agendados não serão mais enviados. Em **abril de 2023**, todos os relatórios agendados para expirar após o dia 31 de dezembro de 2023 foram atualizados e revertidos automaticamente para expirar no dia 31 de dezembro de 2023. Além disso, não será mais possível agendar relatórios para depois de 31 de dezembro de 2023. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, as [!UICONTROL Listas de publicação] estão programadas para serem descontinuadas em **dezembro de 2023**. Você não poderá criar novas nem acessar [!UICONTROL Listas de publicação] já existentes para enviar ou agendar projetos do [!UICONTROL Analysis Workspace]. |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.25.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
