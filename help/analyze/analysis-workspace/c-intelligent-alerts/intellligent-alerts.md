---
description: O novo sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Visão geral de Alertas inteligentes
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 84%

---

# Visão geral de Alertas inteligentes

Os Alertas inteligentes permitem um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.

Tutorial em vídeo sobre [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=pt-BR) (5:34)

## Visão geral

O novo Criador de alertas e Gerenciador de alertas no Analysis Workspace substitui a funcionalidade de alertas existente nos Reports &amp; Analytics. Os Alertas inteligentes permitem:

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo)
* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta

Há quatro maneiras de acessar o Criador de alertas:

| Método | Detalhes |
| --- | --- |
| Ir diretamente para o Criador de alertas | **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** |
| Usar o atalho de teclado do Workspace | `Ctrl + Shift + A` (Windows) ou `Cmd + Shift + A` (Mac) |
| Selecione um ou mais itens de linha da tabela de forma livre | Clique com o botão direito e selecione **[!UICONTROL Criar alerta a partir da seleção]**. Isso abre o [!UICONTROL Criador de alertas] O e o preenchem previamente as métricas e os filtros apropriados aplicados a partir da tabela. Você pode editar o alerta, se necessário. ![Criar alerta a partir da seleção](assets/create-alert-from-selection.png) |
| Em um relatório do Reports &amp; Analytics | Ir para  **[!UICONTROL Mais]** > **[!UICONTROL Adicionar alerta]** . Essa ação abre o criador de alertas e preenche as métricas e os filtros automaticamente com os dados selecionados do relatório. Você pode editar o alerta, se necessário. ![Adicionar alerta](assets/add-alert.png) |

Os limites de porcentagem são desvios padrão. Por exemplo, 95% = 2 desvios padrão e 99% = 3 desvios padrão. Dependendo da granularidade de tempo escolhida, serão usados [modelos diferentes](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) para calcular a distância (a quantidade de desvios padrão) de cada dado em relação à norma. Se você definir um limite mais baixo (como 90%), receberá mais anomalias do que se definir um limite mais alto (99,75%).

>[!IMPORTANT]
>
>Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas disparem incorretamente. A Adobe recomenda o uso de dados sem carimbo de data e hora para criar Alertas inteligentes.

## Pesquisa de anomalias para alertas

Se um alerta usar a detecção de anomalias, o período de treinamento varia de acordo com a granularidade selecionada para o alerta.

* Granularidade mensal: 15 meses + mesmo intervalo do ano passado
* Granularidade semanal: 15 semanas + mesmo intervalo do ano passado
* Granularidade diária: 35 dias + mesmo intervalo do ano passado
* Granularidade por hora: 336 horas

Consulte [Técnicas estatísticas usadas na Detecção de anomalias](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) para obter mais informações.
