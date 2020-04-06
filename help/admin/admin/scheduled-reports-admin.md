---
description: Permite que os usuários de nível administrativo vejam e gerenciem relatórios agendados dentro da organização.
title: Relação de relatórios agendados
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Relação de relatórios agendados

Permite que os usuários de nível administrativo vejam e gerenciem relatórios agendados dentro da organização.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**

Os recursos de nível administrativo no Gerenciador de relatórios agendados incluem:

* A opção de [Mostrar todos os relatórios](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) agendados em sua organização.
* [Recursos](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) de filtragem avançada na sua organização.
* A nova guia Fila [de](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) relatórios que lista todos os relatórios que estão na fila para execução nos servidores de relatórios.
* Exposição da ID [de](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) agendamento na interface da Fila de relatórios.

## Mostrar todos os relatórios agendados {#section_3F167CAAEEC24140B476CF95B7402690}

Na **[!UICONTROL Report List]** guia, você pode fazer parte **[!UICONTROL Show All Scheduled Reports]** de sua organização, além daquelas que você agendou pessoalmente.

>[!NOTE] A **[!UICONTROL Report Name]** coluna exibe o nome do relatório que está sendo programado e a **[!UICONTROL File Name]** coluna exibe qualquer nome de arquivo personalizado definido por você nas Opções avançadas de Delivery. Como resultado, se você agendar vários relatórios do mesmo tipo de relatório e especificar nomes personalizados para cada um, o Gerenciador de relatórios agendados exibirá várias entradas com o mesmo Nome de relatório, mas com nomes de arquivo diferentes. Isso ocorre porque o relatório de back-end programado é o mesmo, portanto a coluna Nome do relatório teria os mesmos nomes de relatório para todos os nomes de arquivo personalizados (conforme definido).

![](assets/show_all_scheduled_reports.png)

## Recursos de filtragem avançada {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Fila de relatórios {#section_03C866115D354BB182E90BF4D52F1E0B}

Essa fila permite gerenciar e potencialmente excluir quaisquer relatórios agendados que estejam &quot;obstruindo&quot; a fila. (Geralmente, os relatórios expiram após 4 horas.)

![](assets/scheduled_reports_2.png)

A Fila de relatórios também oferece a capacidade de &quot;Ignorar um relatório agendado uma vez&quot;. Just click the blue icon in the **[!UICONTROL Manage]** column.

## ID de agendamento {#section_568B70F4228C4229977CB85D2DCD53A1}

Having the **[!UICONTROL Schedule ID]** exposed in the Report Queue interface helps when you need to contact Adobe Client Care for resolution of a scheduled reports issue.

![](assets/schedule_id.png)
