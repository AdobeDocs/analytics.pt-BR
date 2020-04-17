---
title: Comparar datas afetadas por um evento a intervalos anteriores
description: Saiba mais sobre o impacto de um evento, como um problema de implementação ou interrupção, comparando-o com as tendências anteriores.
translation-type: tm+mt
source-git-commit: b8741c1e48cf4d5602e5d7d49b1132d2743a10a0

---


# Comparar datas afetadas por um evento a intervalos anteriores

Se você tiver dados [impactados por um evento](/help/technotes/event-impacted.md), poderá observar tendências históricas para medir seu impacto. Essa comparação é importante para entender o quanto um evento afeta seus dados, para que você possa decidir se deseja excluir os dados, adicionar uma observação aos relatórios ou ignorá-los.

## Criar um intervalo de datas que inclua o evento

Crie um intervalo de datas que inclua o evento para começar a explorar o impacto desse evento.

1. Navegue até **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**.
2. Clique em **[!UICONTROL Add]**.
3. Selecione o intervalo de datas em que o evento ocorreu. Clique em **[!UICONTROL Save]**.

   ![Construtor de intervalo de datas](assets/date_range_builder.png)

## Datas do evento da Visualização e intervalos anteriores semelhantes lado a lado

É possível comparar qualquer métrica entre o intervalo de datas do evento e intervalos de datas anteriores semelhantes usando uma visualização de tabela de forma livre.

1. Abra um projeto do Workspace e adicione a dimensão &quot;Dia&quot; à tabela de forma livre. Aplique o intervalo de datas criado recentemente empilhado em uma métrica, como &quot;Ocorrências&quot;.

   ![Métrica de intervalo de datas](assets/date_range_metric.png)

2. Clique com o botão direito do mouse no intervalo de datas e clique em **[!UICONTROL Add time period column]** > **[!UICONTROL Custom date range to this date range]**.
   * Para uma comparação semana após semana, selecione o intervalo do evento menos 7 dias. Verifique se os dias da semana entre o evento e esse intervalo de datas estão alinhados.
   * Para uma comparação mês a mês, selecione o intervalo do evento no mês passado. Você também pode selecionar o intervalo do evento menos 28 dias se quiser alinhar os dias da semana.
   * Para uma comparação ano após ano, selecione o intervalo do evento no ano passado.
3. Quando você seleciona o intervalo de datas desejado, eles são adicionados à tabela de forma livre. Você pode clicar com o botão direito do mouse e adicionar quantos intervalos de datas desejar comparar.

   ![Tendências alinhadas à data](assets/date_aligned_trends.png)

## Calcular diferenças percentuais entre o evento e intervalos anteriores semelhantes

Compare os valores de dimensão entre um intervalo de datas do evento e intervalos de datas anteriores semelhantes usando uma visualização de tabela de forma livre. Essas etapas ilustram um exemplo de semana por semana que você pode seguir.

1. Abra um projeto do Workspace e adicione uma dimensão **** que não seja de tempo à tabela de forma livre. Por exemplo, você pode usar a dimensão &#39;Tipo de dispositivo móvel&#39;. Aplique o intervalo de datas criado recentemente empilhado em uma métrica, como &quot;Ocorrências&quot;:

   ![Tipo de dispositivo móvel por intervalo de datas afetado](assets/mobile_device_type.png)

2. Clique com o botão direito do mouse no intervalo de datas e clique em **[!UICONTROL Compare time periods]** > **[!UICONTROL Custom date range to this date range]**. Selecione o intervalo do evento menos 7 dias. Verifique se os dias da semana entre o evento e esse intervalo de datas estão alinhados.

   ![Comparar menu de período de tempo](assets/compare_time_custom.png)

3. Renomeie a métrica resultante &quot;Alteração na porcentagem&quot; para algo mais específico, como &quot;Intervalo afetado por WoW&quot;. Clique no ícone de informações e clique no lápis de edição para editar o nome da métrica.

   ![Semana após semana](assets/wow_affected_range.png)

4. Repita as etapas 3 e 4 para comparações mês a mês e ano a ano. É possível realizar essa ação na mesma tabela ou em tabelas separadas.

## Analisar os intervalos de datas de comparação lado a lado como linhas

Se você quiser analisar mais detalhadamente as alterações de porcentagem acima, converta-as em linhas.

1. Adicione uma visualização de tabela de forma livre e ative o criador de tabela. Essa ação permite colocar as métricas de alteração de porcentagem na ordem desejada.
2. Mantenha pressionada `Ctrl` (Windows) ou `Cmd` (Mac) e arraste as métricas de alteração de 3% para as linhas da tabela, uma de cada vez.

   ![Criador de tabela](assets/table_builder.png)

3. Adicione o segmento &quot;Todas as visitas&quot; à coluna da tabela e a quaisquer outros segmentos desejados.

   ![Segmentos do construtor de tabela](assets/table_builder_segments.png)

4. Clique em **[!UICONTROL Build]**. Na tabela resultante, é possível visualização os intervalos afetados em relação à semana, mês e ano anterior em qualquer segmento desejado.

   ![Tabela concluída](assets/table_builder_finished.png)
