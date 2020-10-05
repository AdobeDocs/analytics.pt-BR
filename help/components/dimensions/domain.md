---
title: Domínio
description: A organização ou ISP que o visitante usa para acessar a Internet.
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 41%

---


# Domínio

A dimensão &#39;Domínio&#39; relata os pontos de acesso que os visitantes usam para acessar a Internet.

## Preencher esta dimensão com dados

O Adobe é parceiro do Elemento [Digital](https://www.digitalelement.com/?lang=pt-br) para determinar o domínio do ponto de acesso. Vários métodos, incluindo pesquisa de DNS reverso, são usados para determinar o domínio do ponto de acesso. Ela não exige nenhuma configuração e não tem uma variável para preencher. Funciona imediatamente com todas as implementações do AppMeasurement.

## Itens de dimensão

Os itens de dimensão de exemplo incluem `comcast.net`, `rr.com`, `sbcglobal.net` e `amazonaws.com`. Observe que esses domínios são pontos de acesso e não necessariamente o domínio que representa um ISP ou uma organização.

Valores de Dimension `None` significam que o proprietário do endereço IP do ponto de acesso não forneceu um domínio.
