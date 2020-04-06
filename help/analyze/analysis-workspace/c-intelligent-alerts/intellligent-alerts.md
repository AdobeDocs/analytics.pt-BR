---
description: O novo sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Visão geral de Alertas inteligentes
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral de Alertas inteligentes

Os Alertas inteligentes permitem um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.

[Alertas inteligentes no YouTube](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## Visão geral

O novo Criador de alertas e Gerenciador de alertas no Analysis Workspace substitui a funcionalidade de alertas existente nos Reports &amp; Analytics. Os Alertas inteligentes permitem:

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo)
* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta

Há quatro maneiras de acessar o Criador de alertas:

* Ir diretamente para o Criador de alertas:  **[!UICONTROL Components]** > **[!UICONTROL Alerts]**
* Usar o atalho de teclado do Workspace: `Ctrl + Shift + A` (Windows) ou `Cmd + Shift + A` (Mac)
* Selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. Essa ação abre o Criador de alertas e preenche as métricas e os filtros automaticamente com os dados selecionados da tabela. Você pode editar o alerta, se necessário.

   ![Criar alerta a partir da seleção](assets/create-alert-from-selection.png)

* Em um relatório de Relatórios e análises, vá até **[!UICONTROL More]** > **[!UICONTROL Add Alert]** . Essa ação abre o criador de alertas e preenche as métricas e os filtros automaticamente com os dados selecionados do relatório. Você pode editar o alerta, se necessário.

   ![Adicionar alerta](assets/add-alert.png)

Os limites de porcentagem são desvios padrão. Por exemplo, 95% = 2 desvios padrão e 99% = 3 desvios padrão. Dependendo da granularidade de tempo escolhida,   serão usados [modelos diferentes](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) para calcular a distância (a quantidade de desvios padrão) de cada dado em relação à norma. Se você definir um limite mais baixo (como 90%), receberá mais anomalias do que se definir um limite mais alto (99,75%).

>[!IMPORTANT]Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas disparem incorretamente. A Adobe recomenda o uso de dados sem carimbo de data e hora para criar Alertas inteligentes.

## Pesquisa de anomalias para alertas

Se um alerta usar a detecção de anomalias, o período de treinamento varia de acordo com a granularidade selecionada para o alerta.

* Granularidade mensal: 15 meses + mesmo intervalo do ano passado
* Granularidade semanal: 15 semanas + mesmo intervalo do ano passado
* Granularidade diária: 35 dias + mesmo intervalo do ano passado
* Granularidade por hora: 336 horas

Consulte [Técnicas estatísticas usadas na Detecção de anomalias](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) para obter mais informações.
