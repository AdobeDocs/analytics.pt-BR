---
title: Relatório de práticas recomendadas e solução de problemas
description: Práticas recomendadas e dicas de solução de problemas ao gerar relatórios.
keywords: best practices;failure;timeout;troubleshooting;slow
translation-type: ht
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: ht
source-wordcount: '567'
ht-degree: 100%

---


# Relatório de práticas recomendadas e solução de problemas

*Esta página de ajuda se refere às práticas recomendadas do Reports &amp; Analytics. Para o Analysis Workspace, consulte [Otimizar o desempenho do Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md).  Para o Data Warehouse, consulte [Práticas recomendadas do Data Warehouse](/help/export/data-warehouse/data-warehouse-bp.md).*

O Adobe Analytics oferece uma interface de relatório flexível que permite gerar uma variedade de relatórios complexos. Enquanto a maioria dos relatórios são gerados muito rapidamente, é possível se deparar com relatórios que possuem um tempo limite curto ou que não são gerados com sucesso. Esta página explica os fatores que afetam a velocidade de geração do relatório. O entendimento dessa informação pode ajudar você a estruturar seus relatórios de maneira que eles sejam gerados com mais facilidade.

## Relatar limites de tempo e relação de solicitações

* **Limites de tempo**: um único relatório é dividido em várias solicitações (uma por divisão), e cada solicitação está sujeita a um limite de tempo individual. Relatórios agendados possuem períodos de limite de tempo mais longos e a probabilidade de terem sucesso é maior do que relatórios que são gerados diretamente em uma interface do usuário.
* **Relação de Conjunto de relatórios**: Cada conjunto de relatórios mantém uma relação de solicitações separada. Caso muitos relatórios sejam solicitados ao mesmo tempo, mesmo que de usuários diferentes, um número pequeno de relatórios é gerado simultaneamente. Com a conclusão dos relatórios, os relatórios restantes são gerados na ordem em que foram recebidos. Como resultado, se um grande número de relatórios complexos já estiver na relação de conjunto de relatórios, um relatório que normalmente seria gerado de maneira rápida pode ter seu limite de tempo esgotado.

## Fatores que afetam a velocidade do relatório

Os fatores a seguir contribuem para o aumento do tempo de geração dos relatórios. O aumento de um desses fatores normalmente não afeta o desempenho, mas pode atrasar outros relatórios na fila do conjunto de relatórios e fazer com que um relatório subsequente atinja o tempo limite.

* **Intervalo de tempo do relatório**: o fator mais importante que afeta o tempo de geração de relatório é o número de solicitações mensais. A redução do número de meses de três para um diminui bastante o tempo de geração, mas a redução do intervalo de tempo de um mês para uma semana não tem um grande impacto no tempo de geração do relatório.
* **Quantidade de métricas**: Quando a quantidade de métricas aumenta, o tempo de execução do relatório também aumenta. A remoção das métricas pode melhorar o tempo de geração de relatórios.
* **Quantidade de interrupções**: Dentro de um relatório, cada interrupção representa uma solicitação diferente. Enquanto solicitações individuais podem ser concluídas rapidamente, a execução de milhares de interrupções em um único relatório pode retardar o tempo de geração de um relatório e afetar a relação do conjunto de relatórios.
* **Complexidade do segmento**: Segmentos que consideram várias dimensões ou têm muitas (mais de 24) regras aumentam o impacto do processo e aumentam o tempo de geração de relatório.
* **Número de valores únicos**: relatórios que contêm centenas de milhares de valores únicos são gerados mais lentamente do que relatórios que contém poucos valores únicos, mesmo que o segmento ou filtro reduza o número de valores que aparecem em um relatório. Por exemplo, normalmente um relatório que exibe os termos é gerado mais lentamente do que outros relatórios, mesmo que se aplique um filtro para exibir somente os termos de pesquisa que contêm um valor específico.

## Outras opções de relatório

As diretrizes a seguir ajudam a aumentar a confiabilidade do delivery do relatório:

* Utilize o Data Warehouse para solicitar relatórios que contêm muitas interrupções ou métricas. O Data Warehouse é projetado para gerar esses tipos de relatórios.
* Agende relatórios para serem executados durante horas fora de pico. Isso aumenta a probabilidade do retorno de um relatório porque é mais provável que a relação de solicitações para um relatório esteja vazia durante esses períodos.
* O Report Builder pode ser usado para dividir relatórios em intervalos de tempo menores e solicitações que contêm menos métricas. Dessa forma, é possível usar uma funcionalidade nativa do Excel para combinar dados de vários relatórios em um único.
