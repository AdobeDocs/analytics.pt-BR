---
title: Perguntas frequentes sobre Atribuição
description: Obtenha respostas para perguntas frequentes sobre atribuição.
translation-type: tm+mt
source-git-commit: b5418e6321b09ddbab36e0052f75f36067086e3e

---


# Perguntas frequentes sobre Atribuição

**O que é o item de linha “Nenhum” na atribuição?**

O item de linha “Nenhum” é um item “catch-all” (global) que representa todas as conversões que ocorreram sem nenhum ponto de contato na janela de retrospectiva. Tente incluir um intervalo de tempo maior na janela de relatórios.

**Por que às vezes vejo datas fora da minha janela de relatórios ao usar modelos de atribuição?**

Essas datas extras aparecem devido à janela de retrospectiva do visitante. Consulte [Dados que aparecem fora da janela de relatórios](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) na base de conhecimento (KB) do Analytics para obter mais informações. O Adobe excluirá essas linhas adicionais nas próximas versões.

**Posso usar uma janela de retrospectiva personalizada com meus modelos de atribuição?**

Os modelos de atribuição dependem atualmente de uma janela de retrospectiva de visitante ou de visita. Ambas as janelas de retrospectiva podem ser ajustadas alterando-se o intervalo de datas do relatório (para retrospectiva de visitante) ou usando uma definição de visita personalizada como parte dos conjuntos de relatórios virtuais. Consulte [Processamento de tempo do relatório](../../../../components/vrs/vrs-report-time-processing.md) para obter mais informações.

**Quando devo usar retrospectiva de atribuição de visita e quando devo usar retrospectiva de atribuição de visitante?**

A escolha da retrospectiva de atribuição depende do seu caso de uso. Se as conversões normalmente levam mais tempo do que uma visita única, recomenda-se a retrospectiva de visitante. Criar um conjunto de relatórios virtual com uma definição de visita mais longa também é uma solução possível.

**Como funciona a comparação de props e eVars na atribuição?**

A atribuição é recalculada no tempo de execução do relatório, portanto, não há diferença entre prop e eVar (ou qualquer outra dimensão) para fins de modelagem de atribuição. As props podem persistir usando qualquer janela de retrospectiva ou modelo de atribuição, e as configurações de alocação/expiração de eVar são ignoradas.

**Os modelos de atribuição estão disponíveis em outros recursos do Analytics, como Feeds de dados ou Data Warehouse?**

Não. Os modelos de atribuição usam o processamento de tempo do relatório, que só está disponível no Analysis Workspace. Consulte [Processamento de tempo do relatório](../../../../components/vrs/vrs-report-time-processing.md) para obter mais informações.

**Os modelos de atribuição estão disponíveis somente se uso um conjunto de relatórios virtual com o processamento de tempo ativado?**

Os modelos de atribuição estão disponíveis fora dos conjuntos de relatórios virtuais. Estes usam o processamento de tempo do relatório no backend, enquanto os modelos de atribuição estão disponíveis tanto para os conjuntos de relatórios padrão como para os conjuntos de relatórios virtuais.

**Que dimensões e métricas são incompatíveis?**

O painel de atribuição é compatível com todas as dimensões. As métricas não compatíveis incluem as seguintes:

* Visitantes únicos
* Visitas
* Ocorrências
* Exibições de página
* Métricas do A4T
* Métricas de tempo gasto
* Rejeições
* Taxa de rejeição
* Entradas
* Saídas
* Páginas não encontradas
* Pesquisas
* Visitas únicas à página
* Acesso único

**Posso usar uma janela de retrospectiva personalizada com meus modelos de atribuição?**

Sim, usando a opção da janela de pesquisa personalizada, as janelas de pesquisa podem ser configuradas para qualquer intervalo de datas até 90 dias antes da janela de relatório. Consulte [Processamento de tempo do relatório](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-report-time-processing.html) para obter mais informações.

**A atribuição funciona com classificações?**

Sim, as classificações são totalmente compatíveis.

**A atribuição funciona com fontes de dados?**

Sim, a maioria das fontes de dados é compatível. A atribuição não é possível com fontes de dados de nível de resumo porque elas não se vinculam a um identificador de visitante do Analytics. Fontes de dados de ID de transação também são compatíveis, a menos que sejam usadas em um conjunto de relatórios virtual com o processamento de tempo de relatório ativado.

**A atribuição funciona com a integração do Advertising Analytics?**

As dimensões de metadados, como tipo de correspondência e palavra-chave, funcionam com atribuição. No entanto, as métricas (incluindo impressões, custo, cliques, posição média e pontuação de qualidade média) usam fontes de dados de nível de resumo e, portanto, são incompatíveis.
