---
description: Descrições dos conjuntos de relatórios globais
title: Conjuntos de relatórios globais
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 100%

---

# Conjuntos de relatórios globais

Um conjunto de relatórios global coleta dados de todos os domínios e aplicativos que a organização possui. Ele requer implementação para enviar todas as solicitações de imagem para um único conjunto de relatórios.

A Adobe recomenda implementar um conjunto de relatórios global na maioria dos casos. Consulte “[Considerações sobre o conjunto de relatórios global](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=pt-BR)” para conhecer as vantagens de implementar um conjunto de relatórios global.

É possível fornecer subconjuntos dos dados do conjunto de relatórios global da sua empresa para diferentes usuários finais usando as abordagens *marcação de vários relatórios* e *conjunto de relatórios virtual*:

* **Marcação de vários relatórios**: permite enviar solicitações de imagem não apenas para um conjunto de relatórios global, mas também para conjuntos de relatórios secundários individuais. Os dados do relatório global são desduplicados em todos os conjuntos de relatórios.

  Por exemplo, é possível coletar todos os dados em um conjunto de relatórios global e também configurar conjuntos de relatórios secundários com base na marca, região ou outro diferencial. As diferentes equipes na empresa podem então se concentrar nos dados dos conjuntos de relatórios que são relevantes para elas.

  Para usar a marcação de vários relatórios, implemente conjuntos de relatórios secundários e um conjunto de relatórios global que inclua todos os dados dos secundários. O código de rastreamento de suas páginas da web e aplicativos incluirá a ID de conjunto de relatórios (RSID) do conjunto de relatórios global e também as RSIDs dos conjuntos de relatórios secundários aplicáveis.<!-- Wording/be more specific? And include any links? -->

  É feita uma chamada de servidor separada para cada conjunto de relatórios na solicitação de imagem. As chamadas para os conjuntos de relatórios secundários são chamadas secundárias.

* **Conjunto de relatórios virtual**: um [conjunto de relatórios virtual](/help/components/vrs/vrs-about.md) é uma consulta de segmentos especificados coletados em um conjunto de relatórios global e disponível para grupos específicos de usuários. Os conjuntos de relatórios virtuais permitem preparar elementos de relatório para diferentes usuários finais sem usar a marcação de vários relatórios, evitando assim chamadas de servidor secundárias.

  Para usar conjuntos de relatórios virtuais, implemente um conjunto de relatórios global e analise os dados para criar conjuntos de relatórios virtuais com segmentos específicos aplicados e com permissões de grupo específicas. É possível criar conjuntos de relatórios virtuais no Gerenciador de conjuntos de relatórios virtuais ([!UICONTROL Componentes] > [!UICONTROL Conjuntos de relatórios virtuais]). Consulte “[Fluxo de trabalho dos conjuntos de relatórios virtuais](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)” para obter mais informações.

O uso de conjuntos de relatórios virtuais em vez da marcação de vários relatórios é geralmente uma prática recomendada, mas conjuntos de relatórios virtuais têm algumas limitações. Consulte “[Considerações sobre os conjuntos de relatórios virtuais e a marcação de vários relatórios](/help/components/vrs/vrs-considerations.md)” para determinar qual abordagem de conjunto de relatórios é a melhor opção para suas necessidades comerciais. Para uma comparação detalhada dos conjuntos de relatórios virtuais e da funcionalidade de marcação de vários relatórios, consulte “[Conjuntos de relatórios virtuais vs. marcação de vários relatórios](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)”.

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->
