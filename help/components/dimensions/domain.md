---
title: Domínio
description: A organização ou ISP que o visitante usa para acessar a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 64%

---

# Domínio

O &#39;Domínio&#39; [dimension](overview.md) relata os pontos de acesso que os visitantes usam para acessar a internet.

## Preencher esta dimensão com dados

A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/pt-pt/) para determinar o domínio do ponto de acesso. Vários métodos, incluindo a pesquisa de DNS reverso, são usados para determinar o domínio do ponto de acesso. Ela não exige nenhuma configuração e não tem uma variável para preencher.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do SDK da Web, habilite [!UICONTROL Pesquisa de rede] quando [configurar um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens de dimensão de exemplo incluem `comcast.net`, `rr.com`, `sbcglobal.net` e `amazonaws.com`. Esses domínios são pontos de acesso e não necessariamente o domínio que representa um ISP ou uma organização.

Os valores de dimensão de `None` significam que o proprietário do endereço IP do ponto de acesso não forneceu um domínio.
