---
title: Domínio
description: A organização ou ISP que o visitante usa para acessar a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 100%

---

# Domínio

A dimensão &quot;Domínio&quot; relata os pontos de acesso que os visitantes usam para acessar a Internet.

## Preencher esta dimensão com dados

A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/pt-br) para determinar o domínio do ponto de acesso. Vários métodos, incluindo a pesquisa de DNS reverso, são usados para determinar o domínio do ponto de acesso. Ela não exige nenhuma configuração e não tem uma variável para preencher. Funciona imediatamente com todas as implementações do AppMeasurement.

## Itens de dimensão

Os itens de dimensão de exemplo incluem `comcast.net`, `rr.com`, `sbcglobal.net` e `amazonaws.com`. Observe que esses domínios são pontos de acesso e não necessariamente o domínio que representa um ISP ou uma organização.

Os valores de dimensão de `None` significam que o proprietário do endereço IP do ponto de acesso não forneceu um domínio.
