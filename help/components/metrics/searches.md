---
title: Pesquisas
description: O número de vezes que uma ocorrência correspondeu aos critérios de pesquisa externa.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 1%

---


# Pesquisas

A métrica &quot;Pesquisas&quot; mostra o número de ocorrências que correspondem à detecção de pesquisa externa da Adobe. Essa métrica é útil quando você deseja observar itens de dimensão que não sejam de pesquisa e ver como eles contribuíram para o tráfego do mecanismo de pesquisa.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências que correspondem à detecção de pesquisa externa da Adobe. Deve corresponder a ambos os seguintes:

* O valor de quem indicou da ocorrência é um domínio de pesquisa reconhecido pela Adobe
* O URL de referência da ocorrência contém um parâmetro de string de query de palavra-chave. Devido às práticas modernas de privacidade, esse valor da sequência de caracteres de query geralmente fica em branco. A Adobe reconhece strings de query de palavra-chave em branco como parte da detecção de pesquisa.
