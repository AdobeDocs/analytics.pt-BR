---
description: O Adobe Analytics oferece uma interface de relatório flexível que permite gerar uma variedade de relatórios complexos. Enquanto a maioria dos relatórios são gerados muito rapidamente, é possível se deparar com relatórios que possuem um tempo limite curto ou que não são gerados com sucesso. Essa seção explica muitos fatores que influenciam na velocidade da geração de relatórios para ajudar a evitar essas falhas. O entendimento dessa informação pode ajudá-lo a estruturar seus relatórios de maneira que eles sejam gerados com mais facilidade.
keywords: práticas recomendadas;falha;tempo limite;solução de problemas;lento
seo-description: O Adobe Analytics oferece uma interface de relatório flexível que permite gerar uma variedade de relatórios complexos. Enquanto a maioria dos relatórios são gerados muito rapidamente, é possível se deparar com relatórios que possuem um tempo limite curto ou que não são gerados com sucesso. Essa seção explica muitos fatores que influenciam na velocidade da geração de relatórios para ajudar a evitar essas falhas. O entendimento dessa informação pode ajudá-lo a estruturar seus relatórios de maneira que eles sejam gerados com mais facilidade.
seo-title: Relatando práticas recomendadas e solucionando problemas
solution: Analytics
title: Relatando práticas recomendadas e solucionando problemas
topic: Relatórios
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Relatando práticas recomendadas e solucionando problemas

O Adobe Analytics oferece uma interface de relatório flexível que permite gerar uma variedade de relatórios complexos. Enquanto a maioria dos relatórios são gerados muito rapidamente, é possível se deparar com relatórios que possuem um tempo limite curto ou que não são gerados com sucesso. Essa seção explica muitos fatores que influenciam na velocidade da geração de relatórios para ajudar a evitar essas falhas. O entendimento dessa informação pode ajudá-lo a estruturar seus relatórios de maneira que eles sejam gerados com mais facilidade.

>[!Nnota]
>Essas recomendações se aplicam ao Relatórios e análises, Análise ad hoc e Construtor de relatórios.
>Eles não se aplicam à Analysis Workspace, que tem seu próprio conjunto de práticas [](/help/analyze/analysis-workspace/optimizing-performance.md)recomendadas. They also do not &gt;apply to Data Warehouse [best practices](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html). Um conjunto adicional de
>[as práticas](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) recomendadas estão disponíveis para a API de relatórios do Adobe Analytics.

## Relatar limites de tempo e relação de solicitações {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Tempos limite**

Um único relatório é dividido em várias solicitações (uma por divisão), e cada solicitação está sujeita a um limite de tempo individual. Relatórios agendados possuem períodos de limite de tempo mais longos e a probabilidade de terem sucesso é maior do que relatórios que são gerados diretamente em uma interface do usuário.

**Relação de Conjunto de relatórios**

Cada conjunto de relatórios mantém uma relação de solicitações separada. Caso muitos relatórios sejam solicitados ao mesmo tempo, mesmo que de usuários diferentes, um número pequeno de relatórios é gerado simultaneamente. Com a conclusão dos relatórios, os relatórios restantes são gerados na ordem em que foram recebidos. Como resultado, se um grande número de relatórios complexos já estiver na relação de conjunto de relatórios, um relatório que normalmente seria gerado de maneira rápida pode ter seu limite de tempo esgotado.

## Fatores que afetam a velocidade dos relatórios {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

Os fatores a seguir contribuem para o aumento do tempo para geração de relatórios. O aumento de um desses fatores não significa que o limite de tempo do se esgotará, mas poderá atrasar outros relatórios no relação do conjunto de relatórios e ocasionar o esgotamento do tempo limite de um relatório subsequente.

**Intervalo de tempo do relatório**

O fator mais importante que afeta o tempo de geração de relatório é o número de solicitações mensais. A redução do número de meses de três para um diminui bastante o tempo de geração, mas a redução do intervalo de tempo de um mês para uma semana não tem um grande impacto no tempo de geração do relatório.

**Quantidade de métricas**

Quando a quantidade de métricas aumenta, o tempo de execução do relatório também aumenta. A remoção das métricas pode melhorar o tempo de geração de relatórios.

**Quantidade de interrupções**

Dentro de um relatório, cada interrupção representa uma solicitação diferente. Enquanto solicitações individuais podem ser concluídas rapidamente, a execução de milhares de interrupções em um único relatório pode retardar o tempo de geração de um relatório e afetar a relação do conjunto de relatórios.

**Complexidade do segmento**

Segmentos que consideram várias dimensões ou têm muitas (mais de 24) regras aumentam o impacto do processo e aumentam o tempo de geração de relatório.

**Quantidade de valores únicos**

Relatórios que contém centenas de milhares de valores únicos são gerados mais lentamente do que relatórios que contém poucos valores únicos, mesmo que o segmento ou filtro reduza o número de valores que aparecem em um relatório. Por exemplo, normalmente um relatório que exibe os termos é gerado mais lentamente do que outros relatórios, mesmo que se aplique um filtro para exibir somente os termos de pesquisa que contêm um valor específico.

## Outras opções de relatório {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

Além de reduzir o intervalo de tempo, a quantidade de métricas, e a quantidade de interrupções em um relatório, as instruções a seguir ajudam a aumentar a confiabilidade da entrega de relatório:

* Utilize o Data Warehouse para solicitar relatórios que contêm muitas interrupções ou métricas. O Data Warehouse é projetado para gerar esses tipos de relatórios.
* Agende relatórios para serem executados durante horas fora de pico. Isso aumenta a probabilidade do retorno de um relatório porque é mais provável que a relação de solicitações para um relatório esteja vazia durante esses períodos.
* O Report Builder pode ser usado para dividir relatórios em intervalos de tempo menores e solicitações que contêm menos métricas. Dessa forma, é possível usar uma funcionalidade nativa do Excel para combinar dados de vários relatórios em um único.

