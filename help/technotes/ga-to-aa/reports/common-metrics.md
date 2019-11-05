---
title: Métricas normalmente usadas em outras plataformas guia de conversão
description: Entenda como obter dados de métrica para muitos relatórios comuns usando a terminologia mais familiar aos usuários do Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Métricas normalmente usadas em outras plataformas guia de conversão

Em outras plataformas, como o Google Analytics, muitos relatórios compartilham um número comum de métricas. Use esta página para entender como recriar as métricas usadas em muitos relatórios.

Para adicionar várias métricas a uma tabela de forma livre do espaço de trabalho, arraste a métrica da área de componentes ao lado do cabeçalho da métrica no espaço de trabalho:

![Métrica adicional](/help/technotes/ga-to-aa/assets/new_metric.png)

## Métricas de aquisição

**Os usuários** são aproximadamente iguais aos Visitantes **** únicos no Workspace. Consulte a métrica Visitantes [](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) únicos no guia do usuário Componentes para obter mais detalhes.

**Os novos usuários** podem ser obtidos pelo seguinte:

1. Arraste a métrica Visitantes **** únicos para a área de trabalho.
2. Arraste o segmento Visitas **pela** primeira vez acima dos cabeçalhos de métricas de Visitantes únicos:

   ![Novas visitas](../assets/first_time_visits.png)

**As sessões** são aproximadamente iguais às **Visitas** na Analysis Workspace. Consulte a métrica [Visitas](/help/components/c-variables/c-metrics/metrics-visit.md) no guia do usuário Componentes para obter mais detalhes.

![Métricas de aquisição](../assets/acquisition_metrics.png)

## Métricas de comportamento

**A Taxa** de rejeição está prontamente disponível na Analysis Workspace como uma métrica. Consulte a métrica Taxa de [rejeição](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) no guia do usuário Componentes para obter mais informações.

**Páginas/Sessão** é uma métrica calculada. Pode ser obtido do seguinte modo:

1. Se você já tiver criado essa métrica calculada, localize-a em Métricas e arraste-a para a área de trabalho.
2. Se você ainda não criou essa métrica calculada, clique no ícone **+** próximo à lista de métricas para abrir o Criador de métricas calculadas.
3. Dê a ele um título de "Exibições de página por visita" e uma descrição, se desejar.
4. Defina o formato como Decimal e defina o número de casas decimais como 2.
5. Arraste a métrica de exibições **de página e a métrica** Visitas **** para a área de definição.
6. Organize a definição para que a fórmula seja Exibições de **página divididas por Visitas**.

   ![Exibições de página por visita](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Clique em Salvar para voltar ao seu espaço de trabalho.
8. Arraste a métrica calculada recém-definida para o espaço de trabalho.

   Saiba mais sobre Métricas [](/help/components/c-variables/c-metrics/calculated-metric.md) calculadas no guia do usuário Componentes.

**Média A Duração** da sessão é aproximadamente igual ao **Tempo gasto por visita (segundos)**. Saiba mais sobre as métricas de [Tempo gasto](/help/components/c-variables/c-metrics/metrics-time-spent.md) no guia do usuário Componentes.

## Métricas de conversões

**A taxa** de conversão de metas, as **conclusões** de metas e o valor **da** meta exigem implementação adicional em ambas as plataformas. Se sua implementação já acomoda a dimensão de produtos e o evento de compra, considere as seguintes etapas:

1. Arraste a métrica **Pedidos** , a métrica **Receita** e a métrica **Visitas** para o espaço de trabalho.
1. Crie uma métrica calculada de **Pedidos por visita**. Use ctrl+clique (Windows) ou cmd+clique (Mac) em ambos os cabeçalhos de métrica para realçá-los. Clique com o botão direito do mouse em um dos cabeçalhos, selecione **Criar métrica da seleção** e clique em **Dividir**. Essa nova métrica é semelhante a uma Taxa de conversão de meta.
1. Se forem necessárias casas decimais, edite a Métrica calculada. Clique no botão Informações no cabeçalho da métrica e no ícone de lápis. Adicione 1 ou 2 Casas decimais na janela Construtor de métricas calculadas e clique em Salvar.

   ![Pedidos por visita](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Se sua implementação ainda não acomodar os dados de produtos ou conversão, a Adobe recomenda trabalhar com um consultor de implementação para garantir a qualidade e integridade dos dados.
