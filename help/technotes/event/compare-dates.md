---
title: Comparar datas afetadas por um evento a intervalos anteriores
description: Saiba mais sobre o impacto de um evento, como um problema de implementação ou interrupção, comparando-o às tendências anteriores.
exl-id: 5e4ac1db-2740-4ec1-9d6a-5aa2005fadfd
feature: Curate and Share
TQID: https://experienceleague.adobe.com/g9-IhtHCTJQ0C7wF-FxwHkYuH7QnOLtEvH20JwBz0lE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 627
ht-degree: 0%

---

# Comparar datas afetadas por um evento a intervalos anteriores

Se você tiver dados [afetados por um evento](overview.md), poderá observar as tendências históricas para medir seu impacto. Essa comparação é importante para entender o quanto um evento afeta seus dados, para que você possa decidir se exclui-los, adicionar uma observação aos relatórios ou ignorá-los.

## Criar um intervalo de datas que inclua o evento

Crie um intervalo de datas que inclua o evento para começar a explorar o impacto desse evento.

1. Navegue até **[!UICONTROL Componentes]** > **[!UICONTROL Intervalos de datas]**.
2. Clique em **[!UICONTROL Adicionar]**.
3. Selecione o intervalo de datas em que o evento ocorreu. Clique em **[!UICONTROL Salvar]**.

   ![Construtor de intervalo de datas](assets/date_range_builder.png)

## Exibir datas de evento e intervalos anteriores semelhantes lado a lado

É possível comparar qualquer métrica entre o intervalo de datas do evento e os intervalos de datas anteriores semelhantes usando uma visualização de tabela de forma livre.

1. Abra um projeto do Workspace e adicione a dimensão &quot;Dia&quot; à tabela de forma livre. Aplique o intervalo de datas criado recentemente e empilhado em uma métrica, como &quot;Ocorrências&quot;.

   ![Métrica de intervalo de datas](assets/date_range_metric.png)

2. Clique com o botão direito do mouse no intervalo de datas e clique em **[!UICONTROL Adicionar coluna de período]** > **[!UICONTROL Intervalo de datas personalizado para esse intervalo de datas]**.
   * Para uma comparação entre semanas, selecione o intervalo do evento menos 7 dias. Verifique se os dias da semana entre o evento e esse intervalo de datas estão alinhados.
   * Para uma comparação mês a mês, selecione o intervalo do evento no mês passado. Você também pode selecionar o intervalo do evento menos 28 dias se desejar alinhar os dias da semana.
   * Para uma comparação ano a ano, selecione o intervalo do evento no ano passado.
3. Ao selecionar o intervalo de datas desejado, eles são adicionados à tabela de forma livre. Você pode clicar com o botão direito do mouse e adicionar quantos intervalos de datas desejar comparar.

   ![Tendências alinhadas por data](assets/date_aligned_trends.png)

## Calcular diferenças percentuais entre o evento e intervalos anteriores semelhantes

Compare itens de dimensão entre o intervalo de datas de um evento e intervalos de datas anteriores semelhantes usando uma visualização de tabela de forma livre. Essas etapas ilustram um exemplo de semana a semana que você pode seguir.

1. Abra um projeto do Workspace e adicione uma **dimensão que não seja de tempo** à tabela de forma livre. Por exemplo, você pode usar a dimensão &quot;Tipo de dispositivo móvel&quot;. Aplique o intervalo de datas criado recentemente e empilhado em uma métrica, como &quot;Ocorrências&quot;:

   ![Tipo de dispositivo móvel por intervalo de datas afetado](assets/mobile_device_type.png)

2. Clique com o botão direito do mouse no intervalo de datas e clique em **[!UICONTROL Comparar períodos]** > **[!UICONTROL Intervalo de datas personalizado com este intervalo de datas]**. Selecione o intervalo do evento menos 7 dias. Verifique se os dias da semana entre o evento e esse intervalo de datas estão alinhados.

   ![Comparar menu de período](assets/compare_time_custom.png)

3. Renomeie a métrica &quot;Alteração percentual&quot; resultante para algo mais específico, como &quot;Intervalo afetado por WoW&quot;. Clique no ícone de informações e, em seguida, clique no lápis de edição para editar o nome da métrica.

   ![Semana a semana](assets/wow_affected_range.png)

4. Repita as etapas 3 e 4 para comparações mês a mês e ano a ano. Essa ação pode ser executada na mesma tabela ou em tabelas separadas.

## Analisar intervalos de datas de comparação lado a lado como linhas

Se você quiser analisar mais detalhadamente as alterações de porcentagem acima, poderá convertê-las em linhas.

1. Adicione uma visualização de tabela de forma livre e ative o construtor de tabela. Essa ação permite colocar as métricas de alteração de porcentagem na ordem desejada.
2. Segure o `Ctrl` (Windows) ou o `Cmd` (Mac) e arraste as métricas de alteração de 3% para as linhas da tabela, uma de cada vez.

   ![Construtor de tabela](assets/table_builder.png)

3. Adicione o segmento &quot;Todas as visitas&quot; à coluna da tabela e a qualquer outro segmento desejado.

   ![Segmentos do construtor de tabela](assets/table_builder_segments.png)

4. Clique em **[!UICONTROL Criar]**. Na tabela resultante, é possível visualizar os intervalos afetados em relação à semana, mês e ano anteriores em qualquer segmento desejado.

   ![Tabela concluída](assets/table_builder_finished.png)
