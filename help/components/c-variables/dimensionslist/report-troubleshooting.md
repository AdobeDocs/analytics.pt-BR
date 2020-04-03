---
description: O Adobe Analytics oferece uma interface de relatórios flexível que permite gerar diversos relatórios complexos. Enquanto a maioria dos relatórios são gerados muito rapidamente, você pode encontrar relatórios que expiram ou não são gerados com êxito. Para ajudar a evitar falhas na geração de relatórios, esta seção explica vários fatores que afetam a velocidade de geração de relatórios. Compreender essas informações pode ajudá-lo a estruturar os relatórios para que eles tenham maior probabilidade de serem gerados com êxito.
keywords: best practices;failure;timeout;troubleshooting;slow
title: Relatando práticas recomendadas e solucionando problemas
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: 025ac334f9191b6455eea0530a2a21c01199000a

---


# Relatando práticas recomendadas e solucionando problemas

O Adobe Analytics oferece uma interface de relatórios flexível que permite gerar diversos relatórios complexos. Enquanto a maioria dos relatórios são gerados muito rapidamente, você pode encontrar relatórios que expiram ou não são gerados com êxito. Para ajudar a evitar falhas na geração de relatórios, esta seção explica vários fatores que afetam a velocidade de geração de relatórios. Compreender essas informações pode ajudá-lo a estruturar os relatórios para que eles tenham maior probabilidade de serem gerados com êxito.

>[!Note]
>Essas recomendações se aplicam ao Reports &amp; Analytics, à Ad Hoc Analysis e ao Report Builder.
>Eles não se aplicam à Analysis Workspace, que tem seu próprio conjunto de [práticas recomendadas](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). Elas também não se aplicam às [práticas recomendadas](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html) do Data Warehouse. Um conjunto adicional de
>[práticas recomendadas](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) está disponível para a API de relatórios do Adobe Analytics.

## Relatar limites de tempo e relação de solicitações {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Tempo limite**

Um único relatório é dividido em várias solicitações (uma por análise) e cada solicitação está sujeita a um tempo limite individual. Os relatórios agendados recebem períodos de tempo limite mais longos e têm maior probabilidade de serem bem-sucedidos do que os relatórios gerados diretamente em uma interface do usuário.

**Fila de Report Suite**

Cada conjunto de relatórios mantém uma fila separada de solicitações. Se muitos relatórios forem solicitados simultaneamente, mesmo de usuários separados, um pequeno número de relatórios será gerado simultaneamente. Quando os relatórios são concluídos, os relatórios restantes são gerados na ordem em que foram recebidos. Como resultado, se um grande número de relatórios complexos já estiver na fila do conjunto de relatórios, um relatório que normalmente é gerado rapidamente pode expirar.

## Fatores que afetam a velocidade dos relatórios  {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

Os fatores a seguir contribuem para tempos mais longos de geração de relatórios. O aumento de um desses fatores pode não resultar em um tempo limite para esse relatório, mas pode atrasar outros relatórios na fila do conjunto de relatórios e fazer com que um relatório subsequente atinja o tempo limite.

**Intervalo de tempo do relatório**

O maior fator que afeta o tempo de geração de relatórios é o número de meses solicitados. A redução do número de meses de três para um diminui significativamente o tempo de geração, mas a redução do intervalo de tempo de um mês para uma semana não tem um grande impacto no tempo de geração do relatório.

**Número de métricas**

À medida que o número de métricas aumenta, o tempo de execução do relatório aumenta. A remoção de métricas frequentemente melhora o tempo de geração de relatórios.

**Número de detalhamentos**

Em um relatório, cada detalhamento representa uma solicitação separada. Embora as solicitações individuais possam ser concluídas rapidamente, a execução de milhares de detalhamentos em um único relatório pode retardar significativamente o tempo de geração do relatório e afetar a fila do conjunto de relatórios.

**Complexidade do segmento**

Segmentos que consideram várias dimensões ou têm muitas (mais de 24) regras aumentam o impacto do processamento e aumentam o tempo de geração do relatório.

**Número de valores únicos**

Relatórios que contêm centenas de milhares de valores únicos são gerados mais lentamente do que relatórios que contêm menos valores únicos, mesmo se o segmento ou filtro reduzir o número de valores que aparecem em um relatório. Por exemplo, um relatório que exibe termos de pesquisa normalmente gera mais lentamente que outros relatórios, mesmo se um filtro for aplicado para mostrar apenas termos de pesquisa que contenham um valor específico.

## Outras opções de relatório  {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

Além de reduzir o intervalo de tempo, a quantidade de métricas, e a quantidade de interrupções em um relatório, as instruções a seguir ajudam a aumentar a confiabilidade da entrega de relatório:

* Use o Data Warehouse para solicitar relatórios que contêm muitas análises ou métricas. O Data Warehouse foi projetado para gerar esses tipos de relatórios.
* Agende relatórios para serem executados durante horas que não sejam de pico. Isso aumenta a probabilidade de um relatório ser retornado porque a fila de solicitações de um conjunto de relatórios tem maior probabilidade de ficar vazia durante esses períodos.
* O Construtor de relatórios pode ser usado para dividir relatórios em intervalos de tempo menores e solicitações que contêm menos métricas. Você pode usar a funcionalidade nativa do Excel para unir dados de várias solicitações em um único relatório.

