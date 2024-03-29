---
description: Etapas que descrevem como configurar eventos bem-sucedidos.
title: Configurar os eventos bem-sucedidos
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%

---

# Configurar os eventos bem-sucedidos

Para configurar eventos bem-sucedidos:

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Eventos bem-sucedidos]**.

   ![Resultado da etapa](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Na coluna **[!UICONTROL Nome]**, marque a caixa de seleção ao lado de cada item para ativar a edição e, em seguida, especifique o nome desejado.
1. Na coluna **[!UICONTROL Tipo]**, marque a caixa de seleção ao lado de cada item para ativar a lista suspensa e, em seguida, selecione o tipo desejado.

   >[!NOTE]
   >
   >Antes de alterar um tipo de evento, consulte [Alterar tipo de evento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md).

   Consulte [Página de eventos bem-sucedidos - Descrições](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) para obter mais informações sobre esses elementos.

1. Na coluna **[!UICONTROL Polaridade]**, especifique se uma tendência acima para essa métrica é boa ou ruim.
1. Na coluna **[!UICONTROL Visibilidade]**, você pode ocultar métricas padrão (incorporadas), eventos personalizados e eventos incorporados no Menu, Seletores de métricas, Construtor de métricas calculadas e o Construtor de segmentos.

   Essa configuração não afeta a coleção de dados da métrica ou do evento, afeta somente a visibilidade na interface do usuário, como mostrado a seguir:


   | Configuração | Visível em | Não visível em |
   |---------|----------|---------|
   | [!UICONTROL **Visível em qualquer lugar**] | <ul><li>Analysis Workspace</li><li>Construtor de segmentos</li><li>Criador de métricas calculada</li></ul> | N/D |
   | [!UICONTROL **Construtores**] | <ul><li>Construtor de segmentos</li><li>Criador de métricas calculada</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Oculto em qualquer lugar**] | N/D | <ul><li>Analysis Workspace</li><li>Construtor de segmentos</li><li>Criador de métricas calculada</li></ul> |

1. Forneça uma descrição.
1. Verifique se o evento sempre deve ser gravado.
1. Ative ou desative as métricas de participação.

   >[!NOTE]
   >
   >Você pode ativar a participação de até 100 eventos personalizados. Além disso, você pode criar métricas de participação no construtor de [Métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md).

1. Clique em **[!UICONTROL Salvar]**.
