---
description: Saiba como criar alertas no Analysis Workspace.
title: Criar alertas
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 100%

---

# Criar alertas {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularidade de tempo"
>abstract="A granularidade de tempo refere-se à frequência com a qual o alerta é verificado."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>O uso de alertas com detecção de anomalias (também conhecidos como _Alertas inteligentes_) está disponível somente para organizações com um pacote do Adobe Analytics Prime ou Ultimate.

Os alertas no Adobe Analytics permitem que você receba uma notificação com base em porcentagens alteradas ou pontos de dados específicos. Dependendo do pacote do Adobe Analytics, também é possível usar alertas que são acionados com base em limites de anomalias. Os alertas de uso de chamadas do servidor são um tipo diferente de alerta disponível somente para admins do Analytics. Esses alertas notificam sobre o risco ou a ocorrência de um excesso nos dados de consumo de chamadas do servidor e de compromisso. Para obter mais informações, consulte [Alertas de uso de chamadas do servidor](/help/admin/tools/server-call-usage/scu-alerts.md).

Para informações mais detalhadas sobre os alertas, consulte [Visão geral dos alertas](alerts-overview.md).

Para criar um alerta:

1. Use qualquer um dos seguintes métodos para criar um alerta:

   * Abra um projeto no Analysis Workspace e selecione **[!UICONTROL Componentes]** > **[!UICONTROL Criar alerta]**.
   * Abra um projeto no Analysis Workspace e use o seguinte atalho: ***cmd + shift + a*** (macOS) ou ***ctrl + shift + a*** (Windows).
   * Abra um projeto no Analysis Workspace, escolha um ou mais itens de linha em uma tabela de forma livre, clique com o botão direito do mouse e selecione **[!UICONTROL Criar alerta a partir da seleção]**. Essa ação preenche instantaneamente o [Construtor de alertas](alert-builder.md) para criar um alerta com as métricas e filtros corretos.
   * Criar um alerta [a partir do gerenciador de alertas](/help/components/alerts/alert-manager.md#create-alerts).

   O construtor de alertas é exibido. Esta interface é semelhante à interface de construção de segmentos ou métricas calculadas no Analytics.



## Construtor de alertas

A interface do construtor de alertas é semelhante à interface usada para construir segmentos ou métricas calculadas no Customer Journey Analytics:

![Interface do construtor de alertas](assets/alert-builder.png)

Especifique os seguintes detalhes no Construtor de alertas para um alerta:

| Elemento | Descrição |
|---------|----------|
| **[!UICONTROL Título]** | Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite da métrica. |
| **[!UICONTROL Descrição (opcional)]** | Especifique uma descrição para o alerta. |
| **[!UICONTROL Granularidade de tempo]** | Selecione a frequência com que deseja verificar a métrica: por dia, hora ou mês.<p> |
| **[!UICONTROL Destinatários]** | Especifique para onde o alerta pode ser enviado. Um alerta pode ser enviado a um usuário do Analytics, a um grupo do Analytics, a um endereço de email bruto ou a um número de telefone.<p><b>Importante:</b> o número de telefone deve ser precedido por um `+` e o [código do país](https://countrycode.org/).</p><p>Um exemplo do email que o usuário recebe:</p><p>![Email de alerta](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Data de expiração]** | Defina a data e a hora em que deseja que o alerta expire. |
| **[!UICONTROL Atraso]** | O tempo necessário antes que os dados sejam concluídos e estejam disponíveis para serem relatados no Customer Journey Analytics muda de acordo com a organização, normalmente com uma variação de 3 a 9 horas após o horário do evento de dados. Para que os alertas sejam precisos, os dados de evento para um determinado intervalo de evento devem ser concluídos, o que significa que a Adobe não está mais recebendo dados de evento para o intervalo de evento especificado.<p>Para levar em conta esse atraso no tempo de ingestão, os alertas têm um atraso padrão de 9 horas antes de serem enviados.</p><p>É possível ajustar o atraso padrão de 9 horas para qualquer valor entre 0 e 24 horas. No entanto, diminuir o atraso para menos de 9 horas pode significar que você está relatando dados incompletos, o que resulta em informações de alerta imprecisas.</p><p>Leve em consideração o seguinte ao diminuir o tempo de atraso:</p><ul><li>**Entenda a diferença entre disponibilidade e integridade dos dados**: os dados em lote são assimilados por um conjunto de dados da Experience Platform somente após um período de três a nove horas. Para que os alertas sejam precisos, a ingestão de dados deve ser concluída, com todos os dados em lote disponíveis no conjunto de dados.</li><li>**Determine quanto tempo leva para que seus dados sejam concluídos e estejam disponíveis no conjunto de dados**: os tempos de ingestão de dados diferem de acordo com a organização. Certifique-se de que o tempo de atraso escolhido para a entrega de alertas é o mesmo ou menos frequente do que o tempo que leva para que os dados em lote fiquem disponíveis no conjunto de dados da Platform<!--add link? -->.</li><p>**Dica:** a maneira mais precisa de saber o tempo necessário para que todos os dados em lote sejam concluídos e assimilados no conjunto de dados da Platform é consultar os engenheiros de dados em sua organização.</p><p>Como alternativa, você pode ter uma ideia geral de quanto tempo demora para que a entrega em lote na sua organização fique disponível no conjunto de dados da Experience Platform. Criação da seguinte tabela de forma livre no Analysis Workspace:</p><ol><li>Em uma tabela de forma livre no Analysis Workspace, adicione uma métrica [!UICONTROL **Eventos**] e uma dimensão [!UICONTROL **Dia**].</li><li>Detalhe a dimensão [!UICONTROL **Dia**] usando uma dimensão [!UICONTROL **Horas**].<p>Horas que não possuem nenhum dado são mostradas como 0.</p></li></ol><li>**Leve em conta os erros de cálculo**: se você diminuir o tempo de atraso padrão, configure o atraso para pelo menos uma hora além do tempo que a organização demora para concluir a ingestão de dados. Por exemplo, se houver um atraso de 3 horas antes da conclusão da ingestão de dados, você deve definir um atraso de 4 horas.</li> |
| **[!UICONTROL Enviar um alerta quando]**: | [!UICONTROL **Qualquer uma destas métricas aciona**]: arraste e solte métricas (incluindo métricas calculadas) aqui para criar acionadores para o alerta.<p>Será exibida uma mensagem **“componentes incompatíveis”** se nem todas as métricas, dimensões ou segmentos no alerta forem compatíveis com a visualização de dados selecionada atualmente.</p><p>Determine o limite que a métrica deve exceder antes de definir um alarme. Você pode definir este valor para um limite e, em seguida, para uma das condições a seguir:</p><ul><li>a anomalia existe</li><li>a anomalia está acima do esperado</li><li>a anomalia está abaixo do esperado</li><li>é igual ou maior que</li><li>é igual ou menor que</li><li>alterações por</li><li>Você pode definir um limite de 90%, 95%, 99%, 99,75% e 99,9%.</li></ul><p>[!UICONTROL **Com todos estes filtros**]: arraste e solte segmentos ou dimensões para adicionar filtros ao alerta. Por exemplo, adicionar um segmento *Somente dispositivos móveis* significa que a regra será acionada apenas para dispositivos móveis. É possível adicionar filtros extras usando uma instrução AND. Você pode adicionar regras AND ou OR, clicando no ícone de engrenagem.</p><p>Consulte [Alertas - casos de uso](alerts-use-cases.md) para exemplos de casos de uso.</p> |
| **[!UICONTROL Pré-visualizar]** | A visualização interativa de alertas mostra a frequência de acionamento aproximada de um alerta com base em experiências passadas.<p>Por exemplo, se você definir a granularidade de tempo para diário, a visualização pode informar se o alerta foi acionado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias.</p><p>Se você constatar o acionamento de uma quantidade excessiva de alertas, ajuste o limite em [Gerenciar alertas](alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |

<!--

   ![](assets/alert-builder.png)

1. Specify the following options to configure the alert:

   | Option | Description | 
   |---------|----------|
   | [!UICONTROL **Title**]  | Specify a name for the alert. The alert name might contain the name of the report or the metrics threshold. | 
   | [!UICONTROL **Description (optional)**] | Specify a description for the alert. | 
   | [!UICONTROL **Time granularity**] | Select how often you want the metric to be checked: Hourly, Daily, Weekly, or Monthly.<p><b>Note:</b> For report suites with a custom calendar, monthly granularity in the Alert Builder is not supported.<!--true?--</p | 
   | [!UICONTROL **Recipients**] | Specify where the alert can be sent. An alert can be sent to an Analytics user, an Analytics group, a raw email address, or to a phone number.<p><b>Important:</b> The phone number must be preceded by `+` and a [country code](https://countrycode.org/).</p><p>The e-mail that a user would receive once an alert has been triggered looks similar to:</p><p>![](assets/alerts-email.PNG)</p> | 
   | [!UICONTROL **Expiration date**] | Set the date and time when you want the alert to expire. | 
   | [!UICONTROL **Send an alert when**] | [!UICONTROL **Any of these metrics trigger**]: Drag and drop metrics (including calculated metrics) here to create triggers for the alert.<p>An **"incompatible components"** message appears if not all the metrics, dimensions, or segments in the alert are compatible with the currently selected data view.</p><p>Determine the threshold that the metric must exceed before an alert is set. You can set this value to a threshold and then to one of the following conditions:</p><ul><li>anomaly exists</li><li>anomaly is above expected</li><li>anomaly is below expected</li><li>is above or equals</li><li>is below or equals</li><li>changes by</li><li>You can set a threshold of 90%, 95%, 99%, 99.75%, and 99.9%.</li></ul><p>[!UICONTROL **With all of these filters**]: Drag and drop segments or dimensions to add filters. For example, adding a *Mobile Devices Only* segment would mean that the rule triggers only for mobile devices. You can add additional filters by using an AND statement. You can add AND or OR rules by clicking the gear icon.</p><p>See [Alerts - use cases](/help/components/alerts/alerts-use-cases.md) for example.</p> | 
   | [!UICONTROL **Preview**] | The interactive alert preview shows you how often, approximately, an alert will fire based on past experience.<p>For example, if you set the time granularity to daily, the preview can tell you that the alert would have been triggered for a certain metric x times during the last 30 or 31 days. The preview approximation window is established by the alert frequency setting. For daily alert frequencies, the preview window approximates the previous 30 days. For weekly alert frequencies, the preview window approximates the last 12 weeks. For monthly alert frequencies, the preview window approximates the previous 12 months.</p><p>If you find that too many alerts will be triggered, you can adjust the threshold in the [Alert Manager](/help/components/alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Select [!UICONTROL **Save**].

-->