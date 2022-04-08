---
title: Pesquisas
description: O número de vezes que uma ocorrência correspondeu aos critérios de pesquisa externa.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '117'
ht-degree: 100%

---

# Pesquisas

A métrica &quot;Pesquisas&quot; mostra o número de ocorrências que correspondem à detecção de pesquisa externa da Adobe. Essa métrica é útil quando você quer observar itens de dimensão que não sejam de pesquisa e ver como eles contribuíram para o tráfego do mecanismo de pesquisa.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências que correspondem à detecção de pesquisa externa da Adobe. Ela deve corresponder ao seguinte:

* O valor do referenciador da ocorrência é um domínio de pesquisa reconhecido pela Adobe
* O URL do referenciador da ocorrência contém um parâmetro de sequência de consulta de palavra-chave. Devido às práticas modernas de privacidade, esse valor da sequência de consulta geralmente fica em branco. A Adobe reconhece sequências de consulta em branco como parte da detecção de pesquisa.
