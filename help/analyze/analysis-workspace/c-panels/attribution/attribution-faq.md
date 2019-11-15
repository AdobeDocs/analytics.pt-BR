---
title: Perguntas frequentes sobre atribuição
description: Obtenha respostas para perguntas frequentes sobre atribuição.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Perguntas frequentes sobre atribuição

**O que é o item de linha "Nenhum" ao usar atribuição?**

O item de linha 'Nenhum' é um catch-all que representa todas as conversões que ocorreram sem nenhum ponto de toque na janela de pesquisa. Tente incluir um intervalo de tempo maior na janela de relatórios.

**Por que às vezes vejo datas fora da minha janela de relatórios ao usar modelos de atribuição?**

Essas datas extras devem-se à janela de pesquisa de relatórios do visitante. Consulte [Dados que aparecem fora da janela](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) de relatórios na Base de conhecimento do Analytics para obter mais informações. A Adobe planeja filtrar essas linhas extras em uma versão futura.

**Posso usar uma janela de pesquisa personalizada com meus modelos de atribuição?**

Os modelos de atribuição dependem atualmente de uma janela de pesquisa de visitante ou de visita. Ambas as janelas de pesquisa podem ser ajustadas alterando o intervalo de datas do relatório (para pesquisa de visitante) ou usando uma definição de visita personalizada como parte dos conjuntos de relatórios virtuais. Consulte Processamento [de tempo do](../../../../components/vrs/vrs-report-time-processing.md) relatório para obter mais informações.

**Quando devo usar uma pesquisa de visita vs. atribuição de visitante?**

A escolha da pesquisa de atribuição depende do caso de uso. Se as conversões tipicamente levarem mais tempo do que uma única visita, uma pesquisa de visitante será recomendada. Criar um conjunto de relatórios virtual com uma definição de visita mais longa também é uma solução potencial.

**Como as props e eVars se comparam ao usar atribuição?**

A atribuição é recalculada no tempo de execução do relatório, de modo que não há diferença entre uma prop ou eVar (ou qualquer outra dimensão) para fins de modelagem de atribuição. As props podem persistir usando qualquer janela de pesquisa ou modelo de atribuição, e as configurações de alocação/expiração de eVar são ignoradas.

**Os modelos de atribuição estão disponíveis em outros recursos do Analytics, como Feeds de dados ou Data Warehouse?**

Não. Os modelos de atribuição usam o processamento de tempo do relatório, que só está disponível na Analysis Workspace. Consulte Processamento [de tempo do](../../../../components/vrs/vrs-report-time-processing.md) relatório para obter mais informações.

**Os modelos de atribuição só estarão disponíveis se eu estiver usando um conjunto de relatórios virtual com o processamento de tempo de relatório ativado?**

Os modelos de atribuição estão disponíveis fora dos conjuntos de relatórios virtuais. Enquanto usam o processamento de tempo do relatório no backend, os modelos de atribuição estão disponíveis para os conjuntos de relatórios padrão e os conjuntos de relatórios virtuais.

**Quais dimensões e métricas não são suportadas?**

O painel de atribuição suporta todas as dimensões. As métricas não suportadas incluem:

* Visitantes únicos
* Visitas
* Ocorrências
* Exibições de página
* Métricas do A4T
* Métricas de tempo gasto
* Devoluções
* Taxa de rejeição
* Entradas
* Saídas
* Páginas não encontradas
* Pesquisas
* Visitas únicas à página
* Único Acesso

**Como a atribuição na Analysis Workspace difere da atribuição na Análise de big data?**

A Análise de big data oferece gradualmente:

* A habilidade de atribuir entre mais fontes de dados no nível do visitante, como impressões de anúncios e ponto de venda.
* Modelagem algoritmica. A atribuição na Analysis Workspace inclui apenas modelos baseados em regras. Consulte Modelagem [de](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) melhor ajuste no guia do usuário da Análise de big data.
* Visualizações adicionais, como tabelas de latência. Consulte Tabelas [de](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) latência no guia do usuário da Análise de big data.

**A atribuição funciona com classificações?**

Sim, as classificações são totalmente suportadas.

**A atribuição funciona com fontes de dados?**

Sim, a maioria das fontes de dados é compatível. A atribuição não é possível com fontes de dados de nível de resumo porque elas não se vinculam a um identificador de visitante do Analytics. As fontes de dados da ID de transação também são suportadas, a menos que sejam usadas em um conjunto de relatórios virtual com processamento de tempo de relatório ativado.

**A atribuição funciona com a integração do Advertising Analytics?**

Dimensões de metadados, como tipo de correspondência e palavra-chave, funcionam com atribuição. No entanto, as métricas (incluindo impressões, custo, cliques, posição média e pontuação de qualidade média) usam fontes de dados de nível de resumo e, portanto, são incompatíveis.
