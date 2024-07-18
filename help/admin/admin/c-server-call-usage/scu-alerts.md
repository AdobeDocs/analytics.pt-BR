---
description: Adicione ou gerencie todos os alertas de uso de chamadas do servidor. Ao definir um alerta, ele é aplicado a todos os conjuntos de relatórios em todas as empresas de logon de uma empresa de Faturamento.
title: Alertas de uso de chamadas do servidor
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 96%

---

# Alertas de uso de chamadas do servidor

Ao definir um alerta, ele é aplicado a todos os conjuntos de relatórios em todas as empresas de logon de uma empresa de Faturamento.

Os Alertas de Uso de Chamadas do Servidor fazem parte da interface do usuário [Alertas](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).

Ela é pré-preenchida com **1 alerta padrão** que é exibido em qualquer empresa de logon que tem acesso ao recurso de Uso de chamadas do servidor. Esses alertas acionarão uma notificação direcionada a todos os administradores caso um dos seguintes critérios seja atendido:

* “Qualquer” uso de chamada do servidor que “esteja acima ou seja igual” a 100% para qualquer tipo de chamada do servidor à qual você tem direito, OU
* “Qualquer” uso de chamada do servidor que “esteja acima ou seja igual” a 90% para qualquer tipo de chamada do servidor à qual você tem direito, OU
* “Qualquer” uso de chamada do servidor que “esteja acima ou seja igual” a 75% para qualquer tipo de chamada do servidor à qual você tem direito, E “Período de uso gasto” “está abaixo ou é igual” a 75% do período de Uso.

![](/help/admin/admin/c-server-call-usage/assets/alerts.png)

Você pode acessar alertas de uso de chamadas do servidor de duas maneiras:

* Clique em **[!UICONTROL Gerenciar alertas]** no canto superior direito da guia Uso atual ou na guia de uso do Conjunto de relatórios, ou
* Navegue até **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** no Adobe Analytics.

## Criar alertas de uso de chamadas do servidor {#create}

Para criar alertas adicionais,

1. Clique em **[!UICONTROL + Adicionar]** e selecione **[!UICONTROL Alerta de uso de chamadas do servidor]**.

   ![](/help/admin/admin/c-server-call-usage/assets/server_call_alert.png)

1. Defina o alerta.

   ![](/help/admin/admin/c-server-call-usage/assets/sc_alert.png)

   * **Título**: especifique um nome descritivo. Não é possível salvar o alerta sem um nome.
   * **Granularidade de tempo**: refere-se à frequência com a qual o alerta será verificado. *No momento, oferecemos suporte somente à granularidade Semanal.* Isso significa que o alerta será verificado semanalmente e vai considerar os dados do período de uso atual.
   * **Destinatários**: especifique qualquer pessoa da empresa que deverá receber um email quando o alerta acionar o limite especificado.
   * **Data de expiração**: por padrão, a data de validade é de um ano após a data de criação.
   * **Enviar um Alerta quando**:

      * Qualquer métrica aciona
Adicione o tipo de chamada/s do servidor como uma métrica e especifique o limite de alerta selecionando o modificador e o limite:
         * é igual ou maior que
         * é igual ou menor que
      * Com
Especifique o limite e a condição (está acima ou é igual a, ou está abaixo ou é igual a) para o Período de uso gasto.

1. Clique em **[!UICONTROL Salvar]**.

## Gerenciar alertas de uso de chamadas do servidor {#manage}

![](/help/admin/admin/c-server-call-usage/assets/alert_mgmt.png)

Para gerenciar alertas:

1. Marque a caixa de seleção próxima a um ou mais alertas. As ações de gerenciamento de alerta são exibidas na parte superior.
1. Conclua uma ou mais das seguintes ações:

   | Ação | Definição |
   |--- |--- |
   | + Adicionar | Acesse o [Criador de alertas](/help/admin/admin/c-server-call-usage/scu-alerts.md), clicando em [!UICONTROL + Adicionar]. |
   | Tag | Adicione tags a alertas para organizá-los e facilitar seu uso. |
   | Excluir | É possível excluir todos os alertas, exceto os padrões. |
   | Renomear | É possível renomear todos os alertas, exceto os padrões. |
   | Aprovar | Aprove alertas para “oficializá-los”. |
   | Habilitar/Desabilitar | É possível habilitar ou desabilitar todos os alertas, incluindo os padrões. |
   | Renovar | Quando um ou mais alertas são selecionados, eles podem ser renovados. Isso estende as datas de expiração em 1 ano a partir do dia da [!UICONTROL Renovação], independentemente da data de expiração original. |
   | Exportar para CSV | Consulte [Baixar relatório de uso](/help/admin/admin/c-server-call-usage/report-suite-usage.md) |

   {style="table-layout:auto"}
