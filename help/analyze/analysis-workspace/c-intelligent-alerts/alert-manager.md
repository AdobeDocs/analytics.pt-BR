---
description: Criar, editar ou excluir alertas.
title: Gerenciador de alertas (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: c33a9a30-f53f-443c-96b7-6a87d03573c7
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---


# Gerenciar alertas

Você pode gerenciar alertas existentes no Gerenciador de alertas. Você pode executar várias tarefas de gerenciamento em alertas, como marcar, renomear, excluir e muito mais.

O gerenciador de Alertas está estruturado da mesma forma que o [Gerenciador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=pt-BR) e a variável [Gerenciador de métrica calculada](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=pt-BR).

## Criar alertas

Para criar alertas a partir do Gerenciador de alertas:

1. Selecionar **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acessar o gerenciador de Alertas no Adobe Analytics.

   ![](assets/alert-manager.png)

1. Selecionar [!UICONTROL **Adicionar**] (ou [!UICONTROL **Criar novo alerta**] se você não tiver nenhum alerta existente).

1. Selecione o tipo de alerta que corresponde ao alerta que você deseja criar:

   * [!UICONTROL **Alerta de dados do Analytics**]: um alerta para notificá-lo quando ocorrerem eventos anormais em seus dados.

     Se você selecionar essa opção, continue com [Criar alertas](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) para obter mais detalhes sobre como criar alertas.

   * [!UICONTROL **Alerta de uso de chamadas do servidor**]: um alerta para notificá-lo sobre o risco ou a ocorrência de um excedente no consumo de chamadas do servidor e nos dados de compromisso.

     Se você selecionar essa opção, continue com [Alertas de uso de chamadas do servidor](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Você deve ser um administrador do Analytics ou um usuário com a permissão de Uso de chamadas do servidor para ter acesso ao uso de chamadas do servidor.




## Gerenciar alertas existentes

Para gerenciar alertas existentes no Gerenciador de alertas:

1. Selecionar **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acessar o gerenciador de Alertas no Adobe Analytics.

   ![](assets/alert-manager.png)

1. Selecione um ou mais alertas que deseja gerenciar.

   ![](assets/alert-manager-tasks.png)

1. Na barra de ações, selecione qualquer uma das seguintes opções:

   | Ação | Função |
   |---------|----------|
   | [!UICONTROL **Tag**] | Aplicar uma tag a um alerta. Isso ajuda a organizar alertas para facilitar o uso. |
   | [!UICONTROL **Excluir**] | Exclui o alerta. |
   | [!UICONTROL **Renomear**] | Renomeia o alerta. |
   | [!UICONTROL **Aprovar**] | Marcar o alerta como Aprovado. |
   | [!UICONTROL **Copiar**] | Cria uma cópia (duplicata) do alerta. |
   | [!UICONTROL **Desativar**] | Desativa um alerta atualmente ativado. |
   | [!UICONTROL **Ativar**] | Ativa um alerta desativado no momento. |
   | [!UICONTROL **Renovar**] | Renova a data de expiração do alerta. Essa ação estende a data de expiração para 1 ano a partir do dia em que você selecionou essa opção, independentemente da data de expiração original. |
   | [!UICONTROL **Exportar para CSV**] | Exporta o alerta para um arquivo .CSV. |
