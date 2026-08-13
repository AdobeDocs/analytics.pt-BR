---
description: Permite que os usuários de nível administrativo vejam e gerenciem relatórios agendados dentro da organização.
title: Relação de relatórios agendados
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
role: Admin
TQID: https://experienceleague.adobe.com/HL78cbB5NqKCjv4NvZ5OiqjfbwBjI0KAC8hEr8Afd2U
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 53%

---

# Relação de relatórios agendados

Permite que os usuários de nível administrativo vejam e gerenciem relatórios agendados dentro da organização.

**[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Todos os componentes]** > **[!UICONTROL Relatórios agendados]**

Os recursos de nível administrativo no Gerenciador de relatórios agendados incluem:

* A opção de [Mostrar todos os Relatórios Agendados](/help/components/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) na organização.
* [Recursos de Filtragem Avançada](/help/components/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) em sua organização.
* A nova guia [Fila de Relatório](/help/components/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B), que lista todos os relatórios que estão na fila de execução nos servidores de relatório.
* Expondo a [ID de Agendamento](/help/components/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) na interface da Fila de Relatório.

## Mostrar todos os relatórios agendados {#section_3F167CAAEEC24140B476CF95B7402690}

Na guia **[!UICONTROL Lista de relatórios]**, você pode **[!UICONTROL Mostrar todos os relatórios agendados]** na organização, além daqueles que você agendou pessoalmente.

>[!NOTE]
>
>A coluna **[!UICONTROL Nome do relatório]** exibe o nome do relatório que está sendo agendado, e a coluna **[!UICONTROL Nome do arquivo]** exibe qualquer nome de arquivo personalizado definido por você nas Opções de entrega avançadas. Como resultado, se você agendar vários relatórios do mesmo tipo e especificar nomes personalizados para cada um, o Gerenciador de relatórios agendados exibirá várias entradas com o mesmo Nome de relatório, mas com nomes de arquivo diferentes. Isso ocorre porque o relatório de back-end que está sendo agendado é o mesmo. Portanto, a coluna Nome do relatório teria os mesmos nomes de relatório para todos, exceto os nomes de arquivo personalizados (conforme definido).

![](assets/show_all_scheduled_reports.png)

## Recursos de filtragem avançada {#section_206A52A85DE84947AAB3AD082FBF6275}

Por exemplo, se você deseja filtrar todos os relatórios agendados por hora, você deve especificar a **[!UICONTROL Frequência de hora em hora]** no filtro **[!UICONTROL Avançado]** e clicar em **[!UICONTROL Aplicar]**:

![](assets/advanced_filtering_schedl_reports.png)

## Fila de relatórios {#section_03C866115D354BB182E90BF4D52F1E0B}

Essa fila permite gerenciar e possivelmente excluir quaisquer relatórios agendados que estejam &quot;obstruindo&quot; a fila. (Normalmente, os relatórios expiram após 4 horas.)

![](assets/scheduled_reports_2.png)

A Relação de relatório também oferece a capacidade de &quot;Ignorar um relatório agendado uma vez&quot;. Basta clicar no ícone azul na coluna **[!UICONTROL Gerenciar]**.

## ID de agendamento {#section_568B70F4228C4229977CB85D2DCD53A1}

Expor a **[!UICONTROL ID de agendamento]** na interface da Fila de relatórios é útil quando se é necessário entrar em contato com o Atendimento ao cliente da Adobe para solucionar um problema com relatórios agendados.

![](assets/schedule_id.png)
