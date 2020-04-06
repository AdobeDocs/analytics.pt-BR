---
title: Estado
description: Preencha o "Relatório de estado do visitante" em Reports and Analytics.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# state

>[!IMPORTANT] Essa variável foi removida e não é uma dimensão disponível no Analysis Workspace. Em vez disso, use a dimensão &quot;Estados dos EUA&quot;, que o AppMeasurement coleta automaticamente com base na localização do visitante.

Em versões anteriores do Adobe Analytics, a variável `state` era usada quando os visitantes preenchiam as informações de envio em sites de varejo. É funcionalmente idêntica a uma prop, mas não está disponível no Analysis Workspace.

## Estado no Adobe Experience Platform Launch

Você pode definir o estado ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Locate the [!UICONTROL State] section.

Você pode definir o estado como qualquer valor do tipo string ou elemento de dados.

## s.state no AppMeasurement e no editor de código personalizado do Launch

A variável `s.state` é uma string que normalmente contém o estado ou província do visitante. Nomes completos de estados ou códigos de duas letras são válidos. A variável tem um valor máximo de 50 bytes; valores mais longos são truncados. Seu valor padrão é uma string vazia.

```js
s.state = "Utah";
```
