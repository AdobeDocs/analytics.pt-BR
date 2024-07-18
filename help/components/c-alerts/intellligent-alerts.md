---
description: O sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Alertas inteligentes
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 68%

---

# Alertas inteligentes

O sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.

Veja um vídeo com uma visão geral:

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## Visão geral {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Os Alertas inteligentes estão disponíveis somente para clientes do Adobe [!DNL Analytics] Prime e do Adobe [!DNL Analytics] Ultimate.

Os Alertas inteligentes permitem

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo).
* Visualizar a frequência de disparo de um alerta.
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente.
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta.

Os componentes do sistema de alertas incluem: o Criador de alertas, o Gerenciador de alertas, a Pré-visualização de alertas e acesso melhorado com contexto para criar alertas. A interface de usuário do sistema de alerta anterior não estará mais disponível, mas os alertas serão migrados. Alguns recursos legados de alerta [não estão mais disponíveis](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html?lang=pt-BR).

Há três maneiras de acessar o Criador de alertas:

* Usando o seguinte atalho no Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Acessando diretamente o Criador de alertas: **[!UICONTROL Espaço de trabalho]** > **[!UICONTROL Componentes]** > **[!UICONTROL Novo alerta]** .
* Selecionando um ou mais itens de linha da tabela de forma livre, clicando com o botão direito do mouse e selecionando **[!UICONTROL Criar alerta a partir da seleção]**. Isso abrirá o Criador de alertas e pré-preencherá o criador com as métricas e filtros apropriados aplicados a partir da tabela. Você pode editar o alerta, se necessário.

  ![](assets/create-alert-from-selection.png)


## Perguntas frequentes: como os alertas são calculados e acionados {#trigger}

Os limites % são desvios padrão. Por exemplo, 95% = 2 desvios padrão e 99% = 3 desvios padrão. Dependendo da granularidade de tempo escolhida, os [modelos diferentes](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) são usados para calcular a distância (a quantidade de desvios padrão) de cada ponto de dados em relação à norma. Se você definir um limite mais baixo (como 90%), receberá mais anomalias se definir um limite mais alto (99%), Os limites 99,75% e 99,99% foram criados especificamente para a granularidade horária, de forma que não tantas anomalias não sejam acionadas.

+++ Até que ponto a detecção de anomalias do alerta vai para determinar anomalias de dados?

O período de treinamento varia com base na granularidade selecionada. Consulte Técnicas estatísticas usadas na <a href="/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md">Detecção de anomalias</a> para obter mais detalhes. Aqui está um resumo:

* Mensalmente = 15 meses + mesmo intervalo do ano passado
* Semanalmente = 15 semanas + mesmo intervalo do ano passado
* Diariamente = 35 dias + mesmo intervalo do ano passado
* De hora em hora = 336 horas

+++

+++ Para ser alertado de apenas uma queda no comportamento ou um pico no comportamento, é possível usar o recurso de anomalia ou preciso usar um valor absoluto?

O uso do valor absoluto ainda acionaria alertas em declínios, bem como picos. Não é possível isolar alertas apenas para baixas ou aumentos.

+++

+++ Posso configurar alertas para serem acionados apenas durante certas horas do dia (como horário comercial vs. horário não comercial)?

Atualmente, não.

+++

+++ Posso obter uma tabela dos &quot;valores esperados&quot; que contém a linha pontilhada, ou algum tipo de saída do que são esses valores?

Não no Workspace, mas você pode no Report Builder. Assista a [este vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html?lang=pt-BR) sobre a Detecção de anomalias no Report Builder.

Lembre-se de que o Report Builder usa métodos de detecção de anomalias menos sofisticados. Ele usa um período fixo de treinamento de 30 dias, com intervalo fixo de 95%.

+++
