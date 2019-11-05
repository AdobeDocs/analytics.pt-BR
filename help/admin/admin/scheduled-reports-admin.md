---
description: Permite que os usuários de nível administrativo vejam e gerenciem relatórios agendados dentro da organização.
seo-description: Permite que os usuários de nível administrativo vejam e gerenciem relatórios agendados dentro da organização.
seo-title: Relação de relatórios agendados
solution: Analytics
title: Relação de relatórios agendados
topic: Relatórios
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Relação de relatórios agendados

Permite que os usuários de nível administrativo vejam e gerenciem relatórios agendados dentro da organização.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Componentes]** &gt; Relatórios **[!UICONTROL agendados]**

Os recursos de nível administrativo no Gerenciador de relatórios agendados incluem:

* A opção para [Mostrar todos os relatórios agendados](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) na sua organização.
* [Recursos de filtragem avançada](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) dentro na sua organização.
* A nova aba [Fila de relatórios](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B), que lista todos os relatórios em fila para execução nos servidores de relatório.
* Exposição da [ID de agendamento](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) na interface da Fila de relatórios.

## Mostrar todos os relatórios agendados {#section_3F167CAAEEC24140B476CF95B7402690}

Na guia **[!UICONTROL Lista de relatórios]**, você pode **Mostrar todos os relatórios agendados]na organização, além daqueles que você agendou pessoalmente.[!UICONTROL **

> [!NOTE] A coluna Nome **[!UICONTROL do]** relatório exibe o nome do relatório que está sendo programado e a coluna Nome **[!UICONTROL do]** arquivo exibe qualquer nome de arquivo personalizado definido por você nas Opções avançadas de entrega. Como resultado, se você agendar vários relatórios de um mesmo tipo de relatório e especificar nomes personalizados para cada um, o Gerente de relatórios agendados exibe várias entradas com o mesmo Nome de relatório, mas com nomes de arquivo diferentes. Isso ocorre porque o relatório de back end agendado é o mesmo. Por esse motivo, a coluna Nome do relatório teria os mesmos nomes de relatório para todos os nomes de arquivo personalizados (como definido).

![](assets/show_all_scheduled_reports.png)

## Recursos de filtragem avançada {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Fila de relatórios {#section_03C866115D354BB182E90BF4D52F1E0B}

Essa relação permite que você gerencie e até exclua qualquer relatório agendado que estiver "obstruindo" a relação. (Geralmente, o relatório expira depois de 4 horas.)

![](assets/scheduled_reports_2.png)

A Relação de relatório também possibilita "Pular um relatório agendado uma vez". Basta clicar no ícone azul na coluna **[!UICONTROL Gerenciar.]**

## ID de agendamento {#section_568B70F4228C4229977CB85D2DCD53A1}

Ter a **[!UICONTROL ID de agendamento]na interface da Relação de relatório é útil quando é necessário entrar em contato com o Atendimento ao cliente da Adobe para solucionar um problema com relatórios agendados.**

![](assets/schedule_id.png)
