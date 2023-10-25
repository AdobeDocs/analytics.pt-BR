---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 84f6bf068f56b9502a53ab17e71dca00356804d9
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 66%

---

# Notas de versão atuais do Adobe Analytics (outubro/novembro de 2023)

**Última atualização**: 25 de outubro de 2023

Essas notas de versão abrangem o período de lançamento de 23 de outubro de 2023 até o final de novembro de 2023. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Melhorias no Gerenciador de atividades de relatórios** | O Gerenciador de atividades de relatórios permite ver a capacidade de gerar relatórios para cada conjunto de relatórios na sua organização.  Ele oferece visibilidade detalhada do consumo de relatórios à administração para maior facilidade no diagnóstico e na correção de problemas de capacidade durante os horários de pico de relatórios. Veja a seguir alguns dos aprimoramentos disponíveis no Gerenciador de atividades de relatórios: <ul><li>Restringir solicitações subsequentes: além de cancelar solicitações atuais, os administradores agora podem restringir solicitações por um período definido. Os administradores podem restringir solicitações por Solicitação, Projeto e Usuário.</li><li>Além das métricas de Utilização e Capacidade, o Gerente de atividades de relatórios agora inclui mais dados sobre a atividade de relatórios: coluna Complexidade, coluna Usuário e coluna Conexão.</li><li>Todos os cancelamentos e restrições feitos no Gerenciador de atividades de relatórios agora estão visíveis no Log de auditoria. Os administradores podem usar o Log de auditoria para visualizar o que está cancelado no momento. Os cancelamentos não podem ser revertidos no Gerenciador de atividades de relatórios ou no Log de auditoria.</li></ul><p>Para obter mais informações, consulte [Visão geral do Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 17 de outubro de 2023 | 24 de outubro de 2023 |
| **Melhorias no Data Warehouse** | Ao criar uma solicitação do Data Warehouse, agora é possível configurar uma conta na nuvem para usar como destino do relatório. Os seguintes tipos de conta de nuvem estão disponíveis para enviar dados:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Email (esta opção estava disponível anteriormente)</li></ul>FTP, SFTP, Azure Blob e S3 ainda estão disponíveis como destinos de relatório, mas não são mais recomendados.<p>A experiência do usuário ao criar e gerenciar solicitações do Data Warehouse também foi aprimorada. Para obter mais informações, consulte [Criar uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) e [Gerenciar solicitações do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=pt-BR). | 12 de setembro de 2023 | Até 8 de novembro de 2023 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Essas alterações no Mecanismo de processamento e relatório do Analytics serão implantadas durante a última semana de outubro: corrigiremos um problema em que os rótulos das dimensões Página ou Link eram exibidos incorretamente como `Unknown`. Antes da correção, a variável `Unknown` Os rótulos podem ter sido exibidos incorretamente quando um Nome de página ou Nome de link não foi transmitido em uma ocorrência, padronizando como [!UICONTROL URL da página] e [!UICONTROL URL do link], respectivamente. Essas dimensões foram configuradas para não diferenciar maiúsculas de minúsculas. Com essa correção, os relatórios subsequentes estarão corretos. Mas para relatórios sobre dados históricos, alguns resultados de relatórios ainda podem ser rotulados incorretamente como `Unknown`. (AN-328030)

### Outras correções

-315676; AN-; AN-323398; AN-326209; AN-328178; AN-328261; AN-328395; AN-328671; AN-329282; AN-329330; AN-329355; AN-329506; AN-329516; AN-329738; AN-329769; AN-329771; AN-329816; AN-329877; AN-329928; AN-329957; AN-329962; AN-329966; AN-330023; AN-330081; AN-330083; AN-330105; AN-330138; AN-330140; AN-330165; AN-330241; AN-330359; AN-330366; AN-330427; AN-330438; AN-330442; AN-330534; AN-330616; AN-330654; AN-330783; AN-330879; AN-330881; AN-330883; AN-330887; AN-330888; AN-330955; AN-330979; AN-331031; AN-331053; AN-331068; AN-331071; AN-331074; AN-331075; AN-331076; AN-331078; AN-331085; AN-331093; AN-331167; AN-331171; AN-331181; AN-331196; AN-331226; AN-331258; AN-331260; AN-331279; AN-331286; AN-331290; AN-331365; AN-331375; AN-331376; AN-331454; AN-331519; AN-331570; AN-331590; AN-331593; AN-331603; AN-331751; AN-331816; AN-331897; AN-331900; AN-331906; AN-331926; AN-331929; AN-332031; AN-332067; AN-332101; AN-332114; AN-332156; AN-332201; AN-332225; AN-332253; AN-332277; AN-332361; AN-332370; AN-332386

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Ofuscação de IP completo para ocorrências do Adobe Experience Edge** | 27 de setembro de 2023 | A ofuscação de IP para ocorrências provenientes do Experience Edge será atualizada posteriormente em outubro de 2023. Em abril de 2023, a Experience Edge adicionou a capacidade de ofuscar endereços IP. Na época, o Adobe Analytics só oferecia suporte à ofuscação parcial de IPs, devido à forma como o Analytics processa ocorrências do Experience Edge. Quando os clientes optavam pela ofuscação completa para o Experience Edge, o Analytics recebia apenas IPs parcialmente ofuscados. Quando essa alteração for implementada, o Analytics receberá o IP totalmente ofuscado. |
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
