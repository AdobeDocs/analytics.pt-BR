---
description: Use alertas no Analysis Workspace.
title: Visão geral do Construtor de alertas
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 966bd9a05e6c344a62ce3f0b12df8a99ff3d7ece
workflow-type: ht
source-wordcount: '695'
ht-degree: 100%

---

# Criar alertas {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularidade de tempo"
>abstract="A granularidade de tempo se refere à frequência com a qual o alerta será verificado e ao que será incluído"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>O uso de alertas com detecção de anomalias (também conhecidos como _Alertas inteligentes_) está disponível somente para organizações com um pacote do Adobe Analytics Prime ou Ultimate.

Os alertas no Adobe Analytics permitem que você receba uma notificação com base em porcentagens alteradas ou pontos de dados específicos. Dependendo do pacote do Adobe Analytics, também é possível usar alertas que são acionados com base em limites de anomalias. Os alertas de uso de chamadas do servidor são um tipo diferente de alerta disponível somente para admins do Analytics. Esses alertas notificam sobre o risco ou a ocorrência de um excesso nos dados de consumo de chamadas do servidor e de compromisso. Para obter mais informações, consulte [Alertas de uso de chamadas do servidor](/help/admin/admin/c-server-call-usage/scu-alerts.md).

Para obter informações mais detalhadas da visão geral sobre alertas, consulte [Visão geral dos alertas](/help/components/c-alerts/intellligent-alerts.md).

Para criar um alerta:

1. Comece a criar um alerta acessando o construtor de alertas. É possível acessar o construtor de alertas de qualquer uma das seguintes maneiras:

   * Abra um projeto no Analysis Workspace e selecione **[!UICONTROL Componentes]** > **[!UICONTROL Criar alerta]**.
   * Abra um projeto no Analysis Workspace e use o seguinte atalho: ***ctrl (ou cmd) + shift + a***.
   * Abra um projeto no Analysis Workspace, escolha um ou mais itens de linha em uma tabela de forma livre, clique com o botão direito do mouse e selecione **[!UICONTROL Criar alerta a partir da seleção]**. Essa ação pré-preenche instantaneamente o construtor de alertas para criar um alerta com as métricas e filtros corretos.
   * Criar um alerta [a partir do gerenciador de alertas](/help/components/c-alerts/alert-manager.md#create-alerts).

   O construtor de alertas é exibido. Essa interface é semelhante à interface para criar segmentos ou métricas calculadas no Analytics:

   ![](assets/alert-builder.png)

1. Especifique as seguintes opções para configurar o alerta:

   | Opção | Descrição |
   |---------|----------|
   | [!UICONTROL **Título**] | Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite da métrica. |
   | [!UICONTROL **Descrição (opcional)**] | Especifique uma descrição para o alerta. |
   | [!UICONTROL **Granularidade de tempo**] | Especifique com que frequência deseja que a métrica seja verificada: por hora, dia, semana ou mês.<p><b>Observação:</b> o Construtor de alertas não é compatível com a granularidade mensal ao lidar com conjuntos de relatórios com um calendário personalizado.<!--true?--></p> |
   | [!UICONTROL **Destinatários**] | Especifique para onde o alerta pode ser enviado. Um alerta pode ser enviado a um usuário do Analytics, a um grupo do Analytics, a um endereço de email bruto ou a um número de telefone.<p><b>Importante:</b> o número de telefone deve ser precedido por `+` e um [código de país](https://countrycode.org/).</p><p>O email que um usuário recebe quando um alerta é acionado é semelhante ao exemplo abaixo:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Data de expiração**] | Defina a data e a hora em que deseja que o alerta expire. |
   | [!UICONTROL **Enviar um alerta quando**]: | [!UICONTROL **Qualquer uma destas métricas for acionada**]: arraste e solte métricas (incluindo métricas calculadas) aqui para criar acionadores para o alerta.<p>Será exibida uma mensagem **“componentes incompatíveis”** se nem todas as métricas, dimensões ou segmentos no alerta forem compatíveis com a exibição de dados selecionada no momento.</p><p>Determine o limite que a métrica deve exceder antes de definir um alarme. Você pode definir este valor para um limite e, em seguida, para uma das condições a seguir:</p><ul><li>a anomalia existe</li><li>a anomalia está acima do esperado</li><li>a anomalia está abaixo do esperado</li><li>é igual ou maior que</li><li>é igual ou menor que</li><li>alterações por</li><li>Você pode definir um limite de 90%, 95%, 99%, 99,75% e 99,9%.</li></ul><p>[!UICONTROL **Com todos esses filtros**]: arraste e solte segmentos ou dimensões para adicionar filtros. Por exemplo, adicionar um segmento “Somente dispositivos móveis” significaria que a regra é acionada somente para dispositivos móveis. Você pode adicionar mais filtros usando uma instrução AND. Você pode adicionar regras AND ou OR clicando no ícone de engrenagem.</p><p>Consulte [Alertas: casos de uso](/help/components/c-alerts/alerts-use-cases.md) para ver exemplos.</p> |
   | [!UICONTROL **Pré-visualizar**] | A pré-visualização de alertas interativa mostra a frequência de acionamento aproximada de um alerta com base na experiência passada.<p>Por exemplo, se você definir a granularidade de tempo como diária, a visualização poderá informar que o alerta seria acionado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias. A janela de aproximação da pré-visualização é estabelecida pela configuração de frequência do alerta. Para frequências de alerta diárias, a janela de pré-visualização aproxima os 30 dias anteriores. Para frequências de alerta semanais, a janela de pré-visualização aproxima as últimas 12 semanas. Para frequências de alerta mensais, a janela de pré-visualização aproxima os 12 meses anteriores.</p><p>Se achar que muitos alertas serão acionados, ajuste o limite no [Gerenciador de alertas](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Selecione [!UICONTROL **Salvar**].
