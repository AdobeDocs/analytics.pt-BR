---
title: trackInlineStats
description: Ativar ou desativar o Activity Map na implementação.
translation-type: ht
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

O Activity Map é um recurso do Adobe Analytics que coleta dados sobre onde os visitantes clicam e no que clicam. É possível exibir esses dados nos relatórios do Analytics ou usando uma sobreposição de extensão do navegador. Ative essa variável se desejar usar os recursos do Activity Map.

Quando ativado, o AppMeasurement coleta informações sobre o link e envia esses dados na próxima solicitação de imagem. As informações de cada clique são armazenadas em um cookie rotulado como `s_sq`.

## Ativar Clickmap no Adobe Experience Platform Launch

[!UICONTROL Ativar Clickmap] é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Ativar Clickmap].

Clique na caixa de seleção para ativar o rastreamento do Activity Map.

## s.trackInlineStats no AppMeasurement e no editor de código personalizado do Launch

`s.trackInlineStats` é uma variável do tipo booleano que ativa ou desativa o rastreamento do Activity Map. O valor padrão é `false`. Defina esse valor como `true` se desejar ativar a coleta de dados do Activity Map.

```js
s.trackInlineStats = true;
```
