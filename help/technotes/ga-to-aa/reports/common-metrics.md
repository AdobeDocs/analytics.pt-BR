---
title: Guia de tradução de métricas normalmente usadas em outras plataformas
description: Entenda como obter dados de métrica para muitos relatórios comuns usando a terminologia mais familiar aos usuários do Google Analytics.
translation-type: ht
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Guia de tradução de métricas normalmente usadas em outras plataformas

Em outras plataformas, como o Google Analytics, muitos relatórios compartilham um número comum de métricas. Use esta página para entender como recriar as métricas usadas em muitos relatórios.

Para adicionar várias métricas a uma tabela de forma livre do espaço de trabalho, arraste a métrica da área de componentes ao lado do cabeçalho da métrica no espaço de trabalho:

![Métrica adicional](/help/technotes/ga-to-aa/assets/new_metric.png)

## Métricas de aquisição

**Usuários** é aproximadamente igual a **Visitantes únicos** no Workspace. Consulte a métrica [Visitantes únicos](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) no guia do usuário Componentes para obter mais detalhes.

**Novos usuários** pode ser obtida fazendo o seguinte:

1. Arraste a métrica **Visitantes únicos** para o espaço de trabalho.
2. Arraste o segmento **Novas Visitas** para acima dos cabeçalhos da métrica Visitantes únicos:

   ![Novas visitas](../assets/first_time_visits.png)

**Sessões** é aproximadamente igual a **Visitas** no Analysis Workspace. Consulte a métrica [Visitantes](/help/components/c-variables/c-metrics/metrics-visit.md) no guia do usuário Componentes para obter mais detalhes.

![Métricas de aquisição](../assets/acquisition_metrics.png)

## Métricas de comportamento

**Taxa de rejeição** está prontamente disponível no Analysis Workspace como uma métrica. Consulte a métrica [Taxa de rejeição](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) no guia do usuário Componentes para obter mais informações.

**Páginas/Sessão** é uma métrica calculada. Pode ser obtida do seguinte modo:

1. Se você já tiver criado essa métrica calculada, localize-a em Métricas e arraste-a para o espaço de trabalho.
2. Se você ainda não criou essa métrica calculada, clique no ícone **+** próximo à lista de métricas para abrir o Criador de métricas calculadas.
3. Dê a ele o título de &quot;Exibições de página por visita&quot; e, se desejar, uma descrição.
4. Defina o formato como Decimal e defina o número de casas decimais como 2.
5. Arraste as métricas **Exibições de página** e **Visitas** para a área de definição.
6. Organize a definição para que a fórmula seja **Exibições de página divididas por Visitas**.

   ![Exibições de página por visita](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Clique em Salvar para voltar ao seu espaço de trabalho.
8. Arraste a métrica calculada recém-definida para o espaço de trabalho.

   Saiba mais sobre [Métricas calculadas](/help/components/c-variables/c-metrics/calculated-metric.md) no guia do usuário Componentes.

**Duração média da sessão** é aproximadamente igual a **Tempo gasto por visita (segundos)**. Saiba mais sobre [Tempo gasto](/help/components/c-variables/c-metrics/metrics-time-spent.md) no guia do usuário Componentes.

## Métricas de conversões

**Taxa de conversão de meta**, **Realizações de metas** e **Valor da meta** exigem implementação adicional em ambas as plataformas. Se sua implementação já acomoda a dimensão de produtos e o evento de compra, considere fazer as seguintes etapas:

1. Arraste a métrica **Pedidos**, a métrica **Receita** e a métrica **Visitas** para o espaço de trabalho.
1. Crie uma métrica calculada de **Pedidos por visita**. Use ctrl + clique (Windows) ou cmd + clique (Mac) em ambos os cabeçalhos da métrica para destacá-los. Clique com o botão direito do mouse em um dos cabeçalhos, selecione **Criar métrica a partir da seleção** e clique em **Dividir**. Essa nova métrica é semelhante a uma Taxa de conversão de meta.
1. Se forem necessárias casas decimais, edite a Métrica calculada. Clique no botão Info no cabeçalho da métrica e, em seguida, no ícone de lápis. Adicione 1 ou 2 casas decimais na janela Construtor de métricas calculadas e clique em Salvar.

   ![Pedidos por visita](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Se sua implementação ainda não acomodar os dados de produtos ou de conversão, a Adobe recomenda trabalhar com um consultor de implementação para garantir a qualidade e a integridade dos dados.
