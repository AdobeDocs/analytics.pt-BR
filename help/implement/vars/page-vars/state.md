---
title: estado
description: Preencha o "Relatório de estado do visitante" em Reports and Analytics.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: ht
source-wordcount: '223'
ht-degree: 100%

---

# estado

>[!IMPORTANT]
>
>Essa variável foi removida e não é uma dimensão disponível no Analysis Workspace. Em vez disso, use a dimensão &quot;Estados dos EUA&quot;, que o AppMeasurement coleta automaticamente com base na localização do visitante.

Em versões anteriores do Adobe Analytics, a variável `state` era usada quando os visitantes preenchiam as informações de envio em sites de varejo. É funcionalmente idêntica a uma prop, mas não está disponível no Analysis Workspace.

## Estado usando a extensão do Adobe Analytics

Você pode definir o estado ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Estado].

Você pode definir o estado como qualquer valor do tipo string ou elemento de dados.

## s.state no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.state` é uma string que normalmente contém o estado ou província do visitante. Nomes completos de estados ou códigos de duas letras são válidos. A variável tem um valor máximo de 50 bytes; valores mais longos são truncados. Seu valor padrão é uma string vazia.

```js
s.state = "Utah";
```
