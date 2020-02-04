---
title: Estado
description: Preencha o "Relatório de estado do visitante" em Relatórios e análises.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# state

> [!IMPORTANT] Essa variável é removida e não é uma dimensão disponível na Analysis Workspace. Em vez disso, use a dimensão &quot;Estados dos EUA&quot;, que o AppMeasurement coleta automaticamente com base na localização do visitante.

Em versões anteriores do Adobe Analytics, a `state` variável era usada quando os visitantes preenchiam as informações de envio em sites de varejo. Funcionalmente é idêntico a uma prop, mas não está disponível na Analysis Workspace.

## Estado no Adobe Experience Platform Launch

Você pode definir o estado ao configurar a extensão do Analytics (variáveis globais) ou as regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Estado] .

Você pode definir estado como qualquer valor de string ou elemento de dados.

## s.state no AppMeasurement e Iniciar editor de código personalizado

A `s.state` variável é uma string que normalmente contém o estado ou província do visitante. Nomes de estado completos ou códigos de duas letras são válidos. Tem um valor máximo de 50 bytes; valores mais longos são truncados. Seu valor padrão é uma string vazia.

```js
s.state = "Utah";
```
