---
description: Gerenciar alertas.
title: Visão geral do gerenciador de alertas
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 86580b3c149c0feb1d70d9ba197cf0810e472586
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# Gerenciador de alertas

É possível gerenciar alertas existentes no gerenciador de alertas. É possível executar várias tarefas de gerenciamento em alertas, como aplicar tags, renomear, excluir e mais.

A estrutura do gerenciador de alertas é semelhante à do [gerenciador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=pt-BR) e do [gerenciador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=pt-BR).

![](assets/alert-manager.png)

## Criar alertas

Para criar alertas a partir do gerenciador de alertas:

1. Selecione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acessar o gerenciador de alertas no Adobe Analytics.

   ![](assets/alert-manager.png)

1. Selecione [!UICONTROL **Adicionar**] (ou [!UICONTROL **Criar novo alerta**] se não houver um alerta existente).

1. Selecione o tipo de alerta que você deseja criar:

   * [!UICONTROL **Alerta de dados do Analytics**]: um alerta para notificar sobre a ocorrência de eventos anormais nos dados.

     Ao selecionar esta opção, continue lendo a seção [Criar alertas](/help/components/c-alerts/alert-builder.md) para obter mais detalhes sobre o assunto.

   * [!UICONTROL **Alerta de uso de chamadas do servidor**]: um alerta para notificar sobre o risco ou a ocorrência de um excesso nos dados de consumo e de compromisso de chamadas do servidor.

     Ao selecionar esta opção, leia a seção sobre [Alertas de uso de chamadas do servidor](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Você deve ser um(a) admin do Analytics ou possuir a permissão de uso de chamadas do servidor para ter acesso às chamadas do servidor.

## Gerenciar alertas existentes

É possível executar várias ações nos alertas existentes, como aplicar tags, renomear, excluir e assim por diante.

Para gerenciar alertas existentes no gerenciador de alertas:

1. Selecione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acessar o gerenciador de alertas no Adobe Analytics.

   ![](assets/alert-manager.png)

1. Selecione um ou mais alertas que deseja gerenciar.

   ![](assets/alert-manager-tasks.png)

1. Na barra de ações, selecione qualquer uma das seguintes opções:

   | Ação | Função |
   |---------|----------|
   | [!UICONTROL **Tag**] | Aplica uma tag em um alerta. Isso ajuda a organizar alertas para facilitar o uso. |
   | [!UICONTROL **Excluir**] | Exclui o alerta. |
   | [!UICONTROL **Renomear**] | Renomeia o alerta. |
   | [!UICONTROL **Aprovar**] | Marca o alerta como Aprovado. |
   | [!UICONTROL **Copiar**] | Cria uma cópia (duplicata) do alerta. |
   | [!UICONTROL **Desabilitar**] | Desabilita um alerta que está habilitado. |
   | [!UICONTROL **Habilitar**] | Habilita um alerta que está desabilitado. |
   | [!UICONTROL **Renovar**] | Renova a data de expiração do alerta. Isso estende a data de expiração em um ano a partir do dia em que essa opção foi selecionada, independentemente da data de expiração original. |
   | [!UICONTROL **Exportar para CSV**] | Exporta o alerta como um arquivo .CSV. |

## Editar um alerta

Para editar um alerta existente:

1. Selecione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acessar o gerenciador de alertas no Adobe Analytics.

   ![](assets/alert-manager.png)

1. Selecione o nome do alerta na coluna [!UICONTROL **Título e descrição**].

1. Edite o alerta como preferir.

   Veja a seguir algumas das coisas que é possível fazer ao editar um alerta:

   * Adicionar alertas a outros conjuntos de relatórios
   * Adicionar ou modificar a descrição
   * Modificar a granularidade do tempo
   * Modificar os destinatários
   * Modificar a data de expiração
   * Modificar métricas e filtros

1. Selecione [!UICONTROL **Salvar**].

## Configurar colunas

É possível definir as informações exibidas para cada alerta no gerenciador de alertas por configurar as colunas exibidas.

Para configurar as colunas visíveis no gerenciador de alertas:

1. No Adobe Analytics, selecione a guia **[!UICONTROL Componentes]** e escolha **[!UICONTROL Alertas]**.

1. No gerenciador de alertas, selecione o ícone **Personalizar colunas** ![Ícone Personalizar colunas](assets/customize-columns-icon.png) e escolha as colunas que deseja exibir.

   As seguintes colunas estão disponíveis:

   | Título da coluna | Descrição |
   |---|---|
   | Título e descrição | Esses valores são fornecidos no criador de alertas. Para editar o título e a descrição, clique no link de título para abrir o criador de alertas.  |
   | Favoritos | Exibe ícones de estrela ao lado de cada alerta, permitindo marcar os alertas como favoritos. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Tipo | Mostra se o alerta é um alerta de dados do Analytics ou um alerta de uso de chamadas do servidor. |
   | Ativado | Mostra se o alerta está habilitado ou desabilitado no momento. |
   | Conjunto de relatórios | Indica em qual conjunto de relatórios o alerta foi salvo pela última vez. |
   | Proprietário | Indica o(a) proprietário(a) do alerta. Usuários não admins podem visualizar apenas alertas de sua propriedade ou aqueles que foram compartilhados com eles(as). |
   | Tags | Mostra as tags que foram aplicadas ao alerta por você ou pelas pessoas que compartilharam o alerta. |
   | Data de expiração | Mostra a data e a hora em que o alerta está definido para expirar. |
   | Data de modificação | Indica a data em que o alerta foi modificado pela última vez. |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


