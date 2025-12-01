---
title: Criar E Editar Consolidações De Classificação
description: Explica como criar, validar, executar, aprovar e cancelar consolidações de classificação.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: cabddc619e0d2ddaba6b232eb4d72c60301f76bb
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 1%

---

# Criar e editar consolidações de classificação

Uma consolidação de conjuntos de classificações permite pegar classificações de vários conjuntos de classificações e combiná-las em um. Use essa interface para criar uma consolidação do conjunto de classificações do início ao fim. Essa interface é mais valiosa para organizações que mudam de classificações herdadas para conjuntos de classificações. As organizações que usam conjuntos de classificações já não precisam usar esse fluxo de trabalho de consolidação.

## Criar uma consolidação {#create-a-consolidation}


>[!CONTEXTUALHELP]
>id="classificationsets_consolidation_setpriority"
>title="Prioridade do conjunto de classificações"
>abstract="O ![conjunto de classificações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Key_18_N.svg) *Chave* é o conjunto de classificações base e define o esquema geral, tendo precedência em qualquer conflito de mesclagem. Os outros conjuntos de classificações são aplicados em ordem de cima para baixo."


Para criar uma consolidação de classificação, na interface principal do Adobe Analytics:

1. Selecione **[!UICONTROL Conjuntos de classificações]** no menu **[!UICONTROL Componentes]**.
1. No gerenciador **[!UICONTROL Conjuntos de classificações]**, selecione a guia **[!UICONTROL Consolidações]**.
1. No gerenciador **[!UICONTROL Conjuntos de Classificações - Consolidações]**, selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**.
1. Na caixa de diálogo **[!UICONTROL Nova Consolidação]**,

   ![Conjuntos de classificações - Nova consolidação](assets/classifications-sets-consolidations-new.png)
   1. Insira um **[!UICONTROL Nome]**. Por exemplo: `Consolidation Example`.
   1. Insira uma **[!UICONTROL Descrição (opcional)]**. Por exemplo, `Example classification set`.
   1. Insira um ou mais endereços de email (separados por vírgula) em **[!UICONTROL Notificação de problemas]**. Notificações por email são enviadas a esses usuários sobre problemas.
   1. Selecione um conjunto de classificações no menu suspenso **[!UICONTROL Conjunto de classificações para correspondência]**.

      A lista esquerda **[!UICONTROL Conjunto de Classificações do Source]** foi preenchida com conjuntos de classificações semelhantes à lista de classificações selecionada e disponíveis para consolidação. A lista direita é preenchida automaticamente com o conjunto de classificações ![Chave](/help/assets/icons/Key.svg) selecionado. Esse conjunto de base definiu o esquema geral e sempre tem prioridade em qualquer conflito de mesclagem.

   1. Selecione os conjuntos de classificações que deseja consolidar na lista à esquerda e solte os conjuntos selecionados na lista à direita abaixo do ![Conjunto de classificações ](/help/assets/icons/Key.svg)base **[!UICONTROL _selecionado_]**.

      Os conjuntos de classificações adicionais são consolidados em ordem crescente quando você executa a consolidação. Se uma chave existir em vários conjuntos adicionais, o valor da chave do conjunto de classificação de classificação superior será usado. Se uma chave existir no conjunto base ![Key](/help/assets/icons/Key.svg) e em qualquer conjunto adicional, o valor do conjunto base será usado.

      Para gerenciar quais valores de teclas são usados, mova os conjuntos de classificações individuais e selecionados na lista por meio da ação de arrastar e soltar. Você também pode substituir a ![Chave](/help/assets/icons/Key.svg) **[!UICONTROL _conjunto de classificações_]** por um conjunto de classificações selecionado por meio da ação de arrastar e soltar.

   1. Selecione **[!UICONTROL Salvar]** para salvar a consolidação de classificação. Selecione **[!UICONTROL Cancelar]** para cancelar.

Depois de salva, uma consolidação de classificação é validada automaticamente para consolidação. Essa validação garante que cada conjunto de classificações individual seja válido para essa consolidação. Depois de bem-sucedida, a entrada na lista de consolidação de Classificações mostra o status **[!UICONTROL Validado]**.

Depois de criar uma consolidação, as próximas etapas são:

* [Revalide](#re-validate) a consolidação de classificação quando tiver feito alterações na configuração inicial.
* [Execute](#run) a consolidação de classificação.
* [Aprovar](#approve) a consolidação da classificação.



<!--
         
  

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

The following fields are available when creating a consolidation:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email addresses that are notified of issues with this consolidation.
* **[!UICONTROL Dataset to match]**: A drop-down list of all classification sets.

Once you select a classification set, a table with two columns appears:

* The right column contains all classification sets that you want to consolidate. It starts with the classification set selected using the above drop-down list.
* The left column contains all classification sets eligible to be merged with the originally selected dataset. **Schemas must exactly match to be eligible for consolidation**. If schemas do not match the selected classification set, they do not appear in this left column.

Drag the desired classification sets from the available column on the left to the consolidation column on the right. Once the consolidation is given a name and two or more classification sets are in the right column, click **[!UICONTROL Save & Continue]**.

-->

## Editar uma consolidação

Para editar uma consolidação de classificação, na interface principal do Adobe Analytics:

1. Selecione **[!UICONTROL Conjuntos de classificações]** no menu **[!UICONTROL Componentes]**.
1. No gerenciador **[!UICONTROL Conjuntos de classificações]**, selecione a guia **[!UICONTROL Consolidações]**.
1. No gerenciador **[!UICONTROL Conjuntos de classificações Consolidações]**:
   1. Selecione o nome da consolidação de classificação. A caixa de diálogo **[!UICONTROL Consolidação: _nome da consolidação de classificação_]**é exibida. A aparência e as ações disponíveis dependem do status atual da consolidação e se você ainda tem a opção de modificar a consolidação de classificação.

      | Ações disponíveis | Descrição |
      |---|---|
      | ![Cancelar](/help/assets/icons/Cancel.svg) **[!UICONTROL Cancelar]** | [Cancelar a consolidação](#cancel). |
      | ![Marca De Seleção](/help/assets/icons/Checkmark.svg) **[!UICONTROL Revalidar]** | [Revalidar a consolidação](#re-validate). |
      | ![Reproduzir](/help/assets/icons/Play.svg) **[!UICONTROL Executar]** | [Executar a consolidação](#run). |
      | ![Miniatura](/help/assets/icons/ThumbUp.svg) **[!UICONTROL Aprovar]** | [Aprove a consolidação](#approve). |



### Revalidar

É possível revalidar uma consolidação de classificação na caixa de diálogo Consolidação: consolidação de classificação. Um ![Alerta](/help/assets/icons/Alert.svg) pode fornecer informações adicionais sobre problemas com sua consolidação que requerem a reconfiguração da consolidação.

![Conjuntos De Classificações - Consolidação Revalidada](assets/classifications-sets-consolidations-validated.png)

Para revalidar a consolidação de classificação:

1. Reconfigure a consolidação usando a mesma interface de arrastar e soltar usada para criar a consolidação.
1. Selecione ![Marca De Seleção](/help/assets/icons/Checkmark.svg) **[!UICONTROL Revalidar]**. A validação garante que cada conjunto de classificações individual seja válido para essa consolidação. Quando bem-sucedido, uma mensagem em caixa de informações é exibida: ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Consolidação enviada com êxito para validação!]**
1. Selecione ![CrossSize400](/help/assets/icons/CrossSize400.svg) para fechar a caixa de diálogo. Ou selecione ![Reproduzir](/help/assets/icons/Play.svg) **[!UICONTROL Executar]** para executar a consolidação ou ![Cancelar](/help/assets/icons/Cancel.svg) **[!UICONTROL Cancelar]** para cancelar a classificação.



<!--
Once you have created a consolidation, a list of source datasets appears on the right. The **[!UICONTROL Validate]** button makes sure that each individual classification set is valid for this consolidation. You can reorder the classification steps here to determine priority in cases of mismatched classification values. **The highest classification set in the list overwrites any mismatched values in other classification sets.**

-->

### Executar 

Depois que uma consolidação de classificação for validada com êxito, você poderá executar a consolidação.

Para executar uma consolidação de classificação:

1. Selecione ![Reproduzir](/help/assets/icons/Play.svg) **[!UICONTROL Executar]**. Uma mensagem em caixa de informações exibe ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Consolidação enviada com êxito para processamento!]**
1. Selecione ![CrossSize400](/help/assets/icons/CrossSize400.svg) para fechar a caixa de diálogo.


### Aprovar {#approve}


>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_mismatch"
>title="Incompatibilidade"
>abstract="A porcentagem de incompatibilidades de chave quando o valor no conjunto de classificações consolidado não corresponde ao conjunto de classificações de origem."

>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_absent"
>title="Ausente"
>abstract="A porcentagem de chaves no conjunto de classificações consolidadas, mas não no conjunto de classificações de origem."

Depois que uma consolidação de classificação for executada com êxito, o status da consolidação será ![StatusOrange](/help/assets/icons/StatusOrange.svg) **[!UICONTROL Aguardando Aprovação]**. A aprovação de uma consolidação de classificações substitui os conjuntos de classificações individuais pelo conjunto de classificações consolidado e os conjuntos de classificações individuais são removidos.

![Conjuntos de classificações - Consolidação Aguardando Aprovação](assets/classifications-sets-consolidations-waitingforapproval.png)

Para aprovar uma consolidação do conjunto de classificações:

1. Use os **[!UICONTROL Relatórios de Similaridade]** para examinar a consolidação. Este relatório mostra uma tabela com as seguintes colunas:

   * **[!UICONTROL Nome do conjunto de classificações]**: o nome do conjunto de classificações.
   * **[!UICONTROL Incompatibilidade]**: a porcentagem de linhas em que os valores de chave não correspondem ao conjunto de classificações de origem. Se a porcentagem de incompatibilidade for alta, a incompatibilidade pode ser uma indicação de que os dados de classificação são muito diferentes. Verifique e certifique-se de que os conjuntos de classificações selecionados tenham dados de classificação semelhantes.
   * **[!UICONTROL Ausente]**: a porcentagem de linhas em que os valores de chave estão no conjunto de classificações ![Chave](/help/assets/icons/Key.svg), mas não no conjunto de classificações de origem. Todas as linhas ausentes são adicionadas ao conjunto de classificações consolidado.

1. Se a consolidação de classificação estiver pronta para aprovação, selecione ![Marca de seleção](/help/assets/icons/Checkmark.svg) **[!UICONTROL Aprovar]**. Uma **[!UICONTROL Aprovar Consolidação?A caixa de diálogo]** solicita confirmação. Selecione **[!UICONTROL Aprovar]** para aprovar a consolidação. Selecione **[!UICONTROL Cancelar]** para cancelar.

Depois de aprovado, o conjunto de classificações consolidado é criado. O status está definido como **[!UICONTROL Concluído]**.


### Cancelar

É possível cancelar uma consolidação de classificação antes da aprovação.

Para cancelar uma consolidação de classificação:

1. Selecione **[!UICONTROL Cancelar]**.

   Você não poderá retomar uma consolidação depois que ela for cancelada.
1. Selecione **[!UICONTROL Cancelar Consolidação]** para cancelar a consolidação. Selecione **[!UICONTROL Voltar]** para reverter o cancelamento.
