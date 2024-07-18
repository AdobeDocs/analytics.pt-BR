---
description: Obtenha alertas quando os componentes do projeto atingirem determinados limites.
title: Criador de alertas (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: aae28c90-bfdf-49ff-bd38-c9ef63880bf4
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 39%

---

# Criar alertas

>[!NOTE]
>
>Os Alertas inteligentes estão disponíveis somente para clientes do Adobe Analytics Prime e do Adobe Analytics Ultimate.

Os Alertas inteligentes (ou apenas &quot;alertas&quot;) no Adobe Analytics permitem que você seja notificado imediatamente quando ocorrerem eventos anormais em seus dados. (Os alertas de uso de chamadas do servidor são um tipo diferente de alerta que está disponível somente para administradores do Analytics. Esses alertas notificam você sobre o risco ou a ocorrência de uma sobreposição no consumo de chamadas do servidor e nos dados de compromisso. Para obter mais informações, consulte [Alertas de uso de chamadas do servidor](/help/admin/admin/c-server-call-usage/scu-alerts.md).)

Para obter informações mais detalhadas sobre a visão geral dos Alertas inteligentes, consulte [Visão geral dos Alertas inteligentes](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md).

Para criar um Alerta Inteligente:

1. Comece a criar um alerta acessando o criador de alertas. Você pode acessar o criador de alertas de qualquer uma das seguintes maneiras:

   * Abra um projeto no Analysis Workspace e selecione **[!UICONTROL Componentes]** > **[!UICONTROL Criar alerta]**.
   * Abra um projeto no Analysis Workspace e use o seguinte atalho:

     `ctrl (or cmd) + shift + a`
   * Abra um projeto no Analysis Workspace, selecione um ou mais itens de linha em uma tabela de forma livre, clique com o botão direito do mouse e selecione **[!UICONTROL Criar alerta a partir da seleção]**.

     Essa ação preenche o criador de alertas automaticamente para criar um alerta com as métricas e filtros corretos.
   * Criar um alerta [no gerenciador de alertas](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md#create-alerts).

   O criador de alertas é exibido. Essa interface é semelhante àquela que cria segmentos ou métricas calculadas no Analytics:

   ![](assets/alert-builder.png)

1. Especifique as seguintes opções para configurar o alerta:

   | Opção | Descrição |
   |---------|----------|
   | [!UICONTROL **Título**] | Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite da métrica. |
   | [!UICONTROL **Descrição (opcional)**] | Especifique uma descrição para o alerta. |
   | [!UICONTROL **Granularidade de tempo**] | Selecione a frequência com que deseja verificar a métrica: diariamente, semanalmente ou mensalmente.<p><b>Observação:</b>Para exibições de dados com um calendário personalizado, não oferecemos suporte à granularidade mensal no Criador de alertas.<!--true?--></p> |
   | [!UICONTROL **Destinatários**] | Especifique para onde o alerta pode ser enviado. Um alerta pode ser enviado a um usuário do Analytics, a um grupo do Analytics, a um endereço de email bruto ou a um número de telefone.<p><b>Importante:</b>O número de telefone deve ser precedido por um &quot;+&quot; e um [código do país](https://countrycode.org/).</p><p>O email que um usuário receberia depois que um alerta é acionado é semelhante ao modelo abaixo:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Data de expiração**] | Defina a data e a hora em que deseja que o alerta expire. |
   | [!UICONTROL **Enviar um alerta quando**] | [!UICONTROL **Qualquer uma destas métricas aciona**]: arraste e solte métricas (incluindo métricas calculadas) aqui para criar acionadores para o alerta.<p>Uma mensagem **&quot;componentes incompatíveis&quot;** será exibida se nem todas as métricas, dimensões ou segmentos no alerta forem compatíveis com a exibição de dados selecionada no momento.</p><p>Determine o limite que a métrica deve exceder antes de definir um alarme. Você pode definir este valor para um limite e, em seguida, para uma das condições a seguir:</p><ul><li>a anomalia existe</li><li>a anomalia está acima do esperado</li><li>a anomalia está abaixo do esperado</li><li>é igual ou maior que</li><li>é igual ou menor que</li><li>alterações por</li><li>Você pode definir um limite de 90%, 95%, 99%, 99,75% e 99,9%.</li></ul><p>[!UICONTROL **Com todos esses filtros**]: arraste e solte segmentos ou dimensões para adicionar filtros. Por exemplo, adicionar um segmento &quot;Somente dispositivos móveis&quot; significaria que a regra seria acionada somente para dispositivos móveis. Você pode adicionar filtros extras usando uma instrução AND. Você pode adicionar regras AND ou OR, clicando no ícone de engrenagem.</p><p>Consulte [Alertas inteligentes - casos de uso](/help/analyze/analysis-workspace/c-intelligent-alerts/alerts-use-cases.md), por exemplo, casos de uso.</p> |
   | [!UICONTROL **Pré-visualizar**] | A visualização de alertas interativa mostra a frequência de disparo aproximada de um alerta com base na experiência passada.<p>Por exemplo, se você definir a granularidade de tempo para diário, a visualização pode informar se o alarme foi disparado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias.</p><p>Se achar que muitos alertas podem ter sido disparados, você pode ajustar o limite no [Gerenciador de alertas](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Selecione [!UICONTROL **Salvar**].
