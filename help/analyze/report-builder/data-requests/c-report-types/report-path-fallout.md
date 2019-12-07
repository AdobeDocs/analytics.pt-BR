---
description: Descreve como o construtor de relatórios suporta relatórios de definição de caminho e fallout e como a implementação difere do Relatórios e análises.
title: Relatórios de caminho e fallout de caminho no Report Builder
topic: Report builder
uuid: 9ca6cb97-8f31-46f6-977a-e81a89a176d1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Relatórios de caminho e fallout de caminho no Report Builder

Descreve como o construtor de relatórios suporta relatórios de definição de caminho e fallout e como a implementação difere do Relatórios e análises.

| Nome do relatório de caminho no Relatórios e análises (Caminhos &gt; dimensão &gt;) | Suportado no construtor de relatórios? |
|--- |--- |
| Próximo/Anterior  fluxo de dimensão | Não fornecido como um relatório independente. Pode ser reproduzido utilizando várias solicitações com Dimensão de caminho e um filtro. |
| Próximo/Anterior  dimension | Não fornecido como um relatório independente. É possível reproduzir com um relatório de caminho e utilizando um filtro. |
| Fallout | Suportado e fornecido como um relatório independente ( Caminhos &gt; dimensão &gt; fallout de dimensão). |
| Caminhos completos | Não suportado. |
| PathFinder | Não fornecido como um relatório independente. É possível reproduzir como um relatório de caminho utilizando um filtro. |
| Comprimento do caminho | Suportado somente para a dimensão Página. |
| Análise de página &gt;  resumo da Dimensão | Não fornecido como um relatório independente. Pode ser reproduzido utilizando várias solicitações com Dimensão de caminho e um filtro. |
| Análise de página &gt; Recarregamentos | Não fornecido como um relatório independente. Pode ser reproduzido com um relatório de dimensão utilizando a métrica Recarregamentos. |
| Análise de página &gt; profundidade da dimensão | Suportado somente para a dimensão Página. |
| Análise de página &gt; Tempo gasto na dimensão | Não suportado. |
| Entradas e saídas &gt; Páginas de entrada | Não fornecido como um relatório independente. Pode ser reproduzido como um Relatório de caminho com o filtro pré-definido Site inserido. |
| Entradas e saídas &gt; Páginas de entrada originais | Suportado somente para a dimensão Página. |
| Entradas e saídas &gt; Visitas de página única | Não fornecido como um relatório independente. Pode ser reproduzido como um Relatório de caminho com um filtro pré-definido. |
| Dimensão Entradas e saídas &gt; Saída | Não fornecido como um relatório independente. Pode ser reproduzido como um Relatório de caminho com o filtro pré-definido Saída de site. |
