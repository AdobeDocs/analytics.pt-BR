---
description: Adicione ou gerencie todos os alertas de uso de chamadas do servidor. Ao definir um alerta, ele é aplicado a todos os conjuntos de relatórios em todas as empresas de logon de uma empresa de Faturamento.
title: Alertas de uso de chamadas do servidor
uuid: 701fd542-5b24-42df-97a0-08e10929fa48
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Alertas de uso de chamadas do servidor

Ao definir um alerta, ele é aplicado a todos os conjuntos de relatórios em todas as empresas de logon de uma empresa de Faturamento.

## Visão geral

A new alert category called **[!UICONTROL Server Calls Usage Alert]** is part of the existing [Alert Management](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html) user interface.

Ela é pré-preenchida com **1 alerta padrão** que é exibido em qualquer empresa de logon que tem acesso ao recurso de Uso de chamadas do servidor. Esses alertas acionarão uma notificação direcionada a todos os administradores caso um dos seguintes critérios seja atendido:

* “Qualquer” uso de chamada do servidor que “esteja acima ou seja igual” a 100% para qualquer tipo de chamada do servidor à qual você tem direito, OU
* “Qualquer” uso de chamada do servidor que “esteja acima ou seja igual” a 90% para qualquer tipo de chamada do servidor à qual você tem direito, OU
* “Qualquer” uso de chamada do servidor que “esteja acima ou seja igual” a 75% para qualquer tipo de chamada do servidor à qual você tem direito, E “Período de uso gasto” “está abaixo ou é igual” a 75% do período de Uso.

![](assets/alerts.png)

Você pode acessar alertas de uso de chamadas do servidor de duas maneiras:

* Click **[!UICONTROL Manage Alerts]** in the upper right corner on the Current Usage tab or the Report Suite usage tab, or
* Navegue até **[!UICONTROL Components]** > **[!UICONTROL Alerts]** no Adobe Analytics.

## Criar alertas de uso de chamadas do servidor {#section_2A2882C6D48D47C1944D52FB7C766BEC}

Para criar alertas adicionais,

1. Clique **[!UICONTROL + Add]** e selecione **[!UICONTROL Server Call Usage Alert]**.

   ![](assets/server_call_alert.png)

1. Defina o alerta.

   ![](assets/sc_alert.png)

   * **Título**: especifique um nome descritivo. Não é possível salvar o alerta sem um nome.
   * **Granularidade de tempo**: refere-se à frequência com a qual o alerta será verificado. *No momento, oferecemos suporte somente à granularidade Semanal.* Isso significa que o alerta será verificado semanalmente e vai considerar os dados do período de uso atual.
   * **Destinatários**: especifique qualquer pessoa da empresa que deverá receber um email quando o alerta acionar o limite especificado.
   * **Data de expiração**: por padrão, a data de validade é de um ano após a data de criação.
   * **Enviar um Alerta quando**:

      * Qualquer métria aciona
Adicione o tipo de chamada/s do servidor como uma métrica e especifique o limite de alerta selecionando o modificador e o limite:
         * é igual ou maior que
         * é igual ou menor que
      * Com
Especifique o limite e a condição (está acima ou é igual a, ou está abaixo ou é igual a) para o Período de uso gasto.

1. Clique em **[!UICONTROL Save]**.

## Gerenciar alertas de uso de chamadas do servidor {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

Para gerenciar alertas:

1. Marque a caixa de seleção próxima a um ou mais alertas. As ações de gerenciamento de alerta são exibidas na parte superior.
1. Conclua uma ou mais das seguintes ações:

   | Ação | Definição |
   |--- |--- |
   | + Adicionar | Access the [Alert Builder](/help/admin/c-server-call-usage/scu-alerts.md) by clicking  [!UICONTROL + Add]. |
   | Adicionar tag | Adicione tags a alertas para organizá-los e facilitar seu uso. |
   | Excluir | É possível excluir todos os alertas, exceto os padrões. |
   | Renomear | É possível renomear todos os alertas, exceto os padrões. |
   | Aprovar | Aprove alertas para “oficializá-los”. |
   | Habilitar/Desabilitar | É possível habilitar ou desabilitar todos os alertas, incluindo os padrões. |
   | Renovar | Quando um ou mais alertas são selecionados, eles podem ser renovados. This extends their expiration dates to be 1 year from the day [!UICONTROL Renew] was clicked, regardless of their original expiration date. |
   | Exportar para CSV | Consulte [Baixar relatório de uso](/help/admin/c-server-call-usage/report-suite-usage.md) |

