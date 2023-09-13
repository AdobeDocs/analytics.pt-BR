---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2adc2ba45fb7ce740ff9dc9e376b60da7a84ea4e
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 68%

---

# Notas de versão atuais do Adobe Analytics (setembro de 2023)

**Última atualização**: 13 de setembro de 2023

As notas de versão de setembro abrangem o período de lançamento de 13 de setembro de 2023 a 3 de outubro de 2023. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Classificações na API 2.0** | Fornece métodos da API 2.0 do Adobe Analytics para salvar, excluir, recuperar, importar e exportar dados do conjunto de classificações. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | N/D | 13 de setembro de 2023 |
| **Suporte para novos `correlationID` campo para classificações do A4T** | A variável `_experience.decisioning.propositions.scopeDetails.correlationID` agora está disponível no esquema do conector de origem do Adobe Analytics. Estamos adicionando essa ID para facilitar o ingresso dos dados de classificação das atividades do Adobe Target e dos eventos de experiência. | N/D | 13 de setembro de 2023 |
| **Melhorias no Data Warehouse** | Ao criar uma solicitação Data Warehouse, agora é possível configurar uma conta na nuvem para usar como destino do relatório. Os seguintes tipos de conta de nuvem estão disponíveis para enviar dados:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Email (esta opção estava disponível anteriormente)</li></ul>FTP, SFTP, Azure Blob e S3 ainda estão disponíveis como destinos de relatório, mas não são mais recomendados.<p>A experiência do usuário ao criar e gerenciar solicitações do Data Warehouse também foi aprimorada. Para obter mais informações, consulte [Criar uma solicitação Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/create-request/t-dw-create-request.html) e [Gerenciar solicitações de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=pt-BR). | 13 de setembro de 2023 | 4 de outubro de 2023 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção de um problema que impedia que os dados de Classificação fossem exibidos no Workspace. (AN-326827)

## Outras correções

AN-314882; AN-315591; AN-318165; AN-318559; AN-319031; AN-319244; AN-321657; AN-321759; AN-323099; AN-323596; AN-323640; AN-324442; AN-324921; AN-324953; AN-324977; AN-324979; AN-325124; AN-325395; AN-325433; AN-325535; AN-325693; AN-325720; AN-325835; AN-325880; AN-325957; AN-325984; AN-326054; AN-326065; AN-326136; AN-326155; AN-326162; AN-326235; AN-326317; AN-326344; AN-326357; AN-326359; AN-326433; AN-326438; AN-326440; AN-326461; AN-326464; AN-326523; AN-326553; AN-326606; AN-326635; AN-326642; AN-326652; AN-326678; AN-326769; AN-32677; AN-326830; AN-326938; AN-326949; AN-327081; AN-327082; AN-327085; AN-327103; AN-327198; AN-327225; AN-327275; AN-327358; AN-327423; AN-327561; AN-327755; AN-327896; AN-327922; AN-328128; AN-328300; AN-328428; AN-328518; AN-328554

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| N/D | N/D | N/D |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 7 de março de 2023 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil.<p>Em 31 de dezembro de 2023, encerraremos muitos dos recursos associados do Reports &amp; Analytics, incluindo, entre outros: Relatórios agendados, Extrações de dados e Relatórios DL. Após 31 de dezembro de 2023, os relatórios agendados não serão mais enviados. Entrada **Abril de 2023**, todos os relatórios programados para expirar além de 31 de dezembro de 2023 foram atualizados e revertidos automaticamente para expirar em 31 de dezembro de 2023. Além disso, não será mais possível agendar relatórios para depois de 31 de dezembro de 2023. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, as [!UICONTROL Listas de publicação] estão programadas para serem descontinuadas em **dezembro de 2023**. Você não poderá criar novas nem acessar [!UICONTROL Listas de publicação] já existentes para enviar ou agendar projetos do [!UICONTROL Analysis Workspace]. |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.24.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
