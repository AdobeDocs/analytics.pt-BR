---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 47f102662e5887b3df456a3db88038cec61a6fb2
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 76%

---

# Notas de versão atuais do Adobe Analytics (Julho de 2023)

**Última atualização**: 10 de julho de 2023

As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Configurar locais de armazenamento de conta na nuvem para assimilar dados de classificação** | Agora é possível gerenciar os locais de armazenamento da conta em nuvem usados para a automação do conjunto de classificações.[Saiba mais](/help/components/locations/configure-import-accounts.md)<p> | N/D | 10 de julho de 2023 |
| **Melhorias no filtro de Reparo de dados** | Três melhorias de filtragem foram adicionadas ao Reparo de dados:<ul><li>Filtre por uma variável para modificar uma segunda variável. Por exemplo, se `eVar2` contém &quot;@&quot; e, em seguida, exclui `eVar3`.</li><li>Filtro para valores numéricos ou não numéricos</li><li>Aplique vários filtros com um AND. Por exemplo, onde `eVar2="a"` E `eVar3="b"`</li></ul>[Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 21 de junho de 2023 | 12 de julho de 2023 |
| **Destinos seguros para exportação de feed de dados** | Os feeds de dados agora podem ser enviados para os seguintes destinos de armazenamento na nuvem:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Os destinos que estavam disponíveis anteriormente (FTP, SFTP, S3 e Azure Blob) não são mais recomendados. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=pt-BR) | 12 de junho de 2023 | 15 de julho de 2023 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

AN-307816; AN-318111; AN-318584; AN-318828; AN-320440; AN-320568; AN-320616; AN-321013; AN-321513; AN-321520; AN-321757; AN-321820; AN-321917; AN-322034; AN-322135; AN-322140; AN-322142; AN-322251; AN-322353; AN-322378; AN-322383; AN-322427; AN-322458; AN-322543; AN-322630; AN-322637; AN-322638; AN-322647; AN-322728; AN-322732; AN-322777; AN-322817; AN-322957; AN-322958; AN-323035; AN-323074; AN-323150; AN-323196; AN-323197; AN-323205; AN-323206; AN-323217; AN-323224; AN-323225; AN-323244; AN-323257; AN-323277; AN-323280; AN-323293; AN-323309; AN-323318; AN-323468; AN-323476; AN-323514; AN-323572; AN-323592; AN-323782; AN-323835

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Expiração de 37 meses de IDs de compra e IDs de evento (serialização de eventos)** | Julho de 10,2023 | Uma versão futura do mecanismo de processamento de ocorrências do Analytics, direcionada para lançamento em **13 de julho de 2023**, começará a impor uma expiração de 37 meses de IDs de compra e IDs de evento (serialização de eventos). Atualmente, as IDs de compra e as IDs de evento nunca expiram no Adobe Analytics. Depois que uma ID de compra ou ID de evento for vista/usada, qualquer ocorrência futura, independente de quando, terá essa compra ou evento marcado como duplicado. Com a nova versão do mecanismo de processamento:<ul><li>IDs de compra e IDs de evento sempre expirarão após 37 meses.</li><li>Se tiver passado 37 meses desde que a ID de compra ou a ID de evento foi vista, ela não será mais considerada uma compra ou um evento duplicado.</li><li> Se você estiver “reutilizando” IDs de compra ou IDs de evento de mais de 37 meses atrás, elas não serão mais consideradas duplicatas.</li></ul> |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API do Adobe Analytics e do Livestream que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor do Adobe I/O OAuth até **1º de janeiro de 2025**. Para mais detalhes e linhas do tempo, consulte o aviso de fim de vida útil na tabela abaixo. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para credenciais de servidor para servidor do OAuth do Adobe I/O** | 11 de maio de 2023 | Os clientes da API Adobe Analytics e do Livestream que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor do Adobe I/O OAuth ao **1 de janeiro de 2025**. O Adobe I/O não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 7 de março de 2023 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil.<p>Em 31 de dezembro de 2023, encerraremos muitos dos recursos associados do Reports &amp; Analytics, incluindo, entre outros: Relatórios agendados, Extrações de dados e Relatórios DL. Após 31 de dezembro de 2023, os relatórios agendados não serão mais enviados. Em **abril de 2023**, todos os relatórios agendados para expirar após o dia 31 de dezembro de 2023 serão atualizados e revertidos automaticamente para expirar no dia 31 de dezembro de 2023. Além disso, não será mais possível agendar relatórios para depois de 31 de dezembro de 2023. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, as [!UICONTROL Listas de publicação] estão programadas para serem descontinuadas em **dezembro de 2023**. Você não poderá criar novas nem acessar [!UICONTROL Listas de publicação] já existentes para enviar ou agendar projetos do [!UICONTROL Analysis Workspace]. |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.23.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
