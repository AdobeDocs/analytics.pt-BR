---
title: Perguntas frequentes sobre Atribuição
description: Obtenha respostas para perguntas frequentes sobre atribuição.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Perguntas frequentes sobre Atribuição

**O que é o item de linha “Nenhum” na atribuição?**

O item de linha “Nenhum” é um item “catch-all” (global) que representa todas as conversões que ocorreram sem nenhum ponto de contato na janela de retrospectiva. Tente incluir um intervalo de tempo maior na janela de relatórios.

**Por que às vezes vejo datas fora da minha janela de relatórios ao usar modelos de atribuição?**

Essas datas extras aparecem devido à janela de retrospectiva do visitante. Consulte [Dados que aparecem fora da janela de relatórios](https://helpx.adobe.com/br/analytics/kb/data-appearing-outside-reporting-window.html) na base de conhecimento (KB) do Analytics para obter mais informações. O Adobe excluirá essas linhas adicionais nas próximas versões.

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

**Em que a atribuição no Analysis Workspace difere da atribuição no Data Workbench?**

O Data Workbench oferece de maneira crescente:

* A habilidade de atribuir em mais fontes de dados ao nível do visitante, como impressões de anúncios e pontos de venda.
* Modelagem algorítmica. A atribuição no Analysis Workspace inclui apenas modelos baseados em regras. Consulte [Modelagem de melhor ajuste](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) no guia do usuário do Data Workbench.
* Visualizações adicionais, como tabelas de latência. Consulte [Tabelas de latência](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) no guia do usuário do Data Workbench.

**A atribuição funciona com classificações?**

Sim, as classificações são totalmente compatíveis.

**A atribuição funciona com fontes de dados?**

Sim, a maioria das fontes de dados é compatível. A atribuição não é possível com fontes de dados de nível de resumo porque elas não se vinculam a um identificador de visitante do Analytics. Fontes de dados de ID de transação também são compatíveis, a menos que sejam usadas em um conjunto de relatórios virtual com o processamento de tempo de relatório ativado.

**A atribuição funciona com a integração do Advertising Analytics?**

As dimensões de metadados, como tipo de correspondência e palavra-chave, funcionam com atribuição. No entanto, as métricas (incluindo impressões, custo, cliques, posição média e pontuação de qualidade média) usam fontes de dados de nível de resumo e, portanto, são incompatíveis.
