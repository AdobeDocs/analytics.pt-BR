---
title: trackInlineStats
description: Ativar ou desativar o Mapa de atividade na implementação.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

O Mapa de atividade é um recurso do Adobe Analytics que coleta dados sobre onde os visitantes clicam e em que clicam. É possível exibir esses dados nos relatórios do Analytics ou usando uma sobreposição de extensão do navegador. Ative essa variável se desejar usar os recursos do Mapa de atividade.

Quando ativado, o AppMeasurement coleta informações sobre o link e envia esses dados para a próxima solicitação de imagem. As informações de cada clique são armazenadas em um cookie rotulado `s_sq`.

## Ativar Clickmap no Adobe Experience Platform Launch

[!UICONTROL Ativar Clickmap] é uma caixa de seleção na opção [!UICONTROL Rastreamento] de link ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda a opção Rastreamento [!UICONTROL de] link, que revela a caixa de seleção [!UICONTROL Ativar Clickmap] .

Clique na caixa de seleção para ativar o rastreamento do Mapa de atividade.

## s.trackInlineStats no AppMeasurement e no editor de código personalizado Iniciar

O `s.trackInlineStats` é um booliano que ativa ou desativa o rastreamento do Mapa de atividade. Its default value is `false`. Defina esse valor como `true` se desejar ativar a coleta de dados do Mapa de atividade.

```js
s.trackInlineStats = true;
```
