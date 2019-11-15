---
description: O novo sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Visão geral de alertas inteligentes
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visão geral de alertas inteligentes

Alertas inteligentes permitem um controle mais detalhado sobre alertas e integram a detecção de anomalias ao sistema de alertas.

[Alertas inteligentes no YouTube](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## Visão geral

O novo Criador de alertas e Gerenciador de alertas na Analysis Workspace substitui a funcionalidade de alertas existente nos Reports &amp; Analytics. Os Alertas inteligentes permitem:

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo)
* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de uma só alerta

Há quatro maneiras de acesso o Criador de alertas:

* Ir diretamente para o Criador de alertas:  **[!UICONTROL Componentes]** &gt; **[!UICONTROL Alertas]**
* Uso do atalho de teclado no Workspace: `Ctrl + Shift + A` (Windows) ou `Cmd + Shift + A` (Mac)
* Selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. Isso abre o Criador de alertas e pré-preenche as métricas e filtros apropriados aplicados a partir da tabela. Você pode editar o alerta, se necessário.

   ![Criar alerta a partir da seleção](assets/create-alert-from-selection.png)

* From within a Reports &amp; Analytics report, by going to  **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]** . Isso abre o criador de alertas e pré-preenche as métricas e filtros apropriados aplicados a partir do relatório. Você pode editar o alerta, se necessário.

   ![Adicionar alerta](assets/add-alert.png)

Os limites de porcentagem são desvios padrão. Por exemplo, 95% = 2 desvios padrão e 99% = 3 desvios padrão. Dependendo da granularidade de tempo escolhida, [modelos diferentes](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) são usados para calcular o quão distante (quantos desvios padrão) cada ponto de dados está da norma. Se você definir um limite mais baixo (como 90%), obterá mais anomalias do que se você definir um limite mais alto (99,75%).

> [!IMPORTANT] O uso de dados com carimbo de data e hora para criar alertas pode fazer com que os alertas sejam disparados incorretamente. A Adobe recomenda usar dados sem carimbo de data e hora para Alertas inteligentes.

## Pesquisa de anomalias para alertas

Se um alerta usar a detecção de anomalias, o período de treinamento varia com base na granularidade selecionada para o alerta.

* Granularidade mensal: 15 meses + mesmo intervalo do ano passado
* Granularidade semanal: 15 semanas + mesmo intervalo do ano passado
* Granularidade diária: 35 dias + mesmo intervalo do ano passado
* Granularidade por hora: 336 horas

Consulte Técnicas [estatísticas usadas na Detecção](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) de anomalias para obter mais informações.
