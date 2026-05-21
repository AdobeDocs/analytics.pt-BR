---
description: Adicionar ou gerenciar todos os alertas de uso do servidor. Ao definir um alerta, ele é aplicado a todos os conjuntos de relatórios em todas as empresas de logon de uma empresa de Faturamento.
title: Alertas de uso de chamadas do servidor
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
TQID: https://experienceleague.adobe.com/aF3SxS36Y1xQN-saS6NTRJoN6H5XwgCx2iRmWPvUPm0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 517
ht-degree: 44%

---

# Alertas de uso de chamadas do servidor

Ao definir um alerta, ele é aplicado a todos os conjuntos de relatórios em todas as empresas de logon de uma empresa de Faturamento.

Os Alertas de Uso de Chamadas do Servidor fazem parte da interface do usuário [Alertas](/help/components/alerts/alert-manager.md).

Ela é pré-preenchida com **1 alerta padrão** que é exibido em qualquer empresa de logon que tem acesso ao recurso de Uso de chamadas do servidor. Esses alertas acionarão uma notificação direcionada a todos os administradores caso um dos seguintes critérios seja atendido:

* 100% de uso de chamada de servidor &quot;Qualquer&quot; que &quot;esteja acima ou seja igual&quot; para qualquer tipo de chamada de servidor ao qual você tenha direito, OU
* 90% de uso de chamada de servidor &quot;Qualquer&quot; que &quot;esteja acima ou seja igual&quot; para qualquer tipo de chamada de servidor ao qual você tenha direito, OU
* &quot;Qualquer&quot; uso de chamada de servidor que &quot;está acima ou é igual a&quot; 75% para qualquer tipo de chamada de servidor ao qual você tenha direito, E &quot;Período de uso gasto&quot; &quot;está abaixo ou é igual a&quot; 75% do período de uso.

![](/help/admin/tools/server-call-usage/assets/alerts.png)

Você pode acessar alertas de uso de chamadas do servidor de duas maneiras:

* Clique em **[!UICONTROL Gerenciar alertas]** no canto superior direito da guia Uso atual ou na guia de uso do Conjunto de relatórios, ou
* Navegue até **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** no Adobe Analytics.

## Criar alertas de uso de chamadas do servidor {#create}

Para criar alertas adicionais,

1. Clique em **[!UICONTROL + Adicionar]** e selecione **[!UICONTROL Alerta de uso de chamadas do servidor]**.

   ![](/help/admin/tools/server-call-usage/assets/server_call_alert.png)

1. Defina o alerta.

   ![](/help/admin/tools/server-call-usage/assets/sc_alert.png)

   * **Título**: especifique um nome descritivo. Não é possível salvar o alerta sem um nome.
   * **Granularidade de tempo**: refere-se à frequência com a qual o alerta será verificado. *Oferecemos suporte somente à granularidade semanal no momento.* Isso significa que o alerta será verificado semanalmente e analisará os dados do período de uso atual.
   * **Destinatários**: especifique qualquer pessoa da empresa que deverá receber um email quando o alerta acionar o limite especificado.
   * **Data de expiração**: por padrão, a data de validade é de um ano após a data de criação.
   * **Enviar um Alerta quando**:

      * Qualquer uma dessas métricas é acionada
Adicione o tipo de chamada/s do servidor como uma métrica e especifique o limite de alerta selecionando o modificador e o limite:
         * é maior que ou igual a
         * é menor que ou igual a
      * Com
Especifique o limite e a condição (está acima ou é igual a, ou está abaixo ou é igual a) para o Período de uso gasto.

1. Clique em **[!UICONTROL Salvar]**.

## Gerenciar alertas de uso de chamadas do servidor {#manage}

![](/help/admin/tools/server-call-usage/assets/alert_mgmt.png)

Para gerenciar alertas:

1. Marque a caixa de seleção ao lado de um ou mais alertas. As ações de gerenciamento de alertas são exibidas na parte superior.
1. Conclua uma ou mais destas ações:

   | Ação | Definição |
   |--- |--- |
   | + Adicionar | Acesse o [Criador de alertas](/help/admin/tools/server-call-usage/scu-alerts.md), clicando em [!UICONTROL + Adicionar]. |
   | Tag | Marque alertas para organizá-los para facilitar o uso. |
   | Excluir | Você pode excluir todos os alertas, exceto os alertas padrão. |
   | Renomear | Você pode renomear todos os alertas, exceto os alertas padrão. |
   | Aprovar | Aprove alertas para torná-los &quot;oficiais&quot;. |
   | Ativar/desativar | Você pode ativar ou desativar todos os alertas, até mesmo os padrão. |
   | Renovar | Quando um ou mais alertas são selecionados, eles podem ser renovados. Essa ação estende as datas de expiração em 1 ano a partir do dia [!UICONTROL Renovar], independentemente da data de expiração original. |
   | Exportar para CSV | Consulte [Baixar relatório de uso](/help/admin/tools/server-call-usage/report-suite-usage.md) |

   {style="table-layout:auto"}
