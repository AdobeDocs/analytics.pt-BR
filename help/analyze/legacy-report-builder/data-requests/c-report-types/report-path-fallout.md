---
description: Descreve como o Report Builder oferece suporte a relatórios de definição de caminho e fallout, e como a implementação difere de Reports & Analytics.
title: Relatórios de caminho e fallout de caminho no Report Builder
feature: Report Builder
role: User, Admin
exl-id: 211b0e76-2895-401d-a5a5-73e459a486e2
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 81%

---

# Relatórios de caminho e fallout de caminho no Report Builder

{{legacy-arb}}

Descreve como o Report Builder suporta relatórios de definição de caminho e fallout, e como a implementação difere do Reports &amp; Analytics (agora encerrado).

| Nome do relatório de caminho em Reports &amp; Analytics (Caminhos > Dimensão >) | Suportado no Report Builder? |
|--- |--- |
| Fluxo de dimensão seguinte/anterior | Não fornecido como um relatório independente. Pode ser reproduzido utilizando várias solicitações com Dimensão de caminho e um filtro. |
| Dimensão seguinte/anterior | Não fornecido como um relatório independente. É possível reproduzir com um relatório de caminho e utilizando um filtro. |
| Fallout | Suportado e fornecido como um relatório independente ( Caminhos > dimensão > fallout de dimensão). |
| Caminhos completos | Não suportado. |
| PathFinder | Não fornecido como um relatório independente. É possível reproduzir como um relatório de caminho utilizando um filtro. |
| Comprimento do caminho | Suportado somente para a dimensão Página. |
| Análise de página > Resumo da dimensão | Não fornecido como um relatório independente. Pode ser reproduzido utilizando várias solicitações com Dimensão de caminho e um filtro. |
| Análise de página > Recarregamentos | Não fornecido como um relatório independente. Pode ser reproduzido com um relatório de dimensão utilizando a métrica Recarregamentos. |
| Análise de página > profundidade da dimensão | Suportado somente para a dimensão Página. |
| Análise de página > Tempo gasto na dimensão | Não suportado. |
| Entradas e saídas > Páginas de entrada | Não fornecido como um relatório independente. Pode ser reproduzido como um Relatório de caminho com o filtro pré-definido Site inserido. |
| Entradas e saídas > Páginas de entrada originais | Suportado somente para a dimensão Página. |
| Entradas e saídas > Visitas de página única | Não fornecido como um relatório independente. Pode ser reproduzido como um Relatório de caminho com um filtro pré-definido. |
| Entradas e saídas > Dimensão de saída | Não fornecido como um relatório independente. Pode ser reproduzido como um Relatório de caminho com o filtro pré-definido Saída de site. |
