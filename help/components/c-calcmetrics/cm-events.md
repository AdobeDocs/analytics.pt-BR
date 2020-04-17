---
title: Derivar dados afetados pelos eventos
description: Use métricas calculadas para corrigir dados de tendências afetados por um evento.
translation-type: tm+mt
source-git-commit: dfc2e036711ee2229160f52ab16fb4299f7722e5

---


# Derivar dados afetados pelos eventos

Se os dados forem [afetados por um evento](/help/technotes/event-impacted.md), você poderá usar métricas calculadas para derivar valores de tendência para a duração do evento. Por exemplo, se você tiver um evento que causou uma queda de 25% nos dados, poderá usá-lo como um multiplicador em uma métrica calculada.

>[!NOTE] Essas etapas funcionam melhor quando você entende o impacto de um evento, tanto da perspectiva de segmentação quanto da comparação de datas. Certifique-se de seguir [Comparar datas afetadas por um evento a intervalos](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) anteriores e [Excluir datas específicas na análise](../c-segmentation/use-cases/exclude-date-range.md) antes de seguir esta página.

1. Crie dois segmentos para &quot;Dias afetados&quot; e &quot;Excluir dias afetados&quot;, conforme descrito em [Excluir datas específicas na análise](../c-segmentation/use-cases/exclude-date-range.md).
2. Navegue até **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**.
3. Clique em **[!UICONTROL Add]**.
4. Arraste ambos os segmentos acima para a tela de definição. Altere o operador entre eles para `+` somá-los.
5. Adicione a métrica desejada em ambos os segmentos. Por exemplo, você pode usar a métrica &quot;Visitas&quot;.

   ![Construtor de segmentos](assets/event_segment_builder.png)

6. Clique **[!UICONTROL Add]** no canto superior direito do container &#39;Dias afetados&#39; e clique em **[!UICONTROL Static number]**. Defina o número estático para a porcentagem que você deseja deslocar seus dados, conforme descrito em [Comparar datas afetadas por um evento a intervalos](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md)anteriores. Neste exemplo, o deslocamento é 25% ou 1,25.

   ![Número estático](assets/event_static_number.png)

7. Aplique a métrica &quot;corrigida&quot; lado a lado em uma tabela de forma livre de tendência. Todos os dias fora do evento refletem sua contagem métrica normal, enquanto todos os dias afetados usam o deslocamento do multiplicador.

   ![Métrica corrigida](assets/event_corrected.png)

8. Visualização os dados em uma visualização de linha para ver o efeito da sua métrica corrigida.

   ![Linha corrigida](assets/event_line.png)
