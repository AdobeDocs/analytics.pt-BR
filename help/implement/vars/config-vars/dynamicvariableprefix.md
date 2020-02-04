---
title: dynamicVariablePrefix
description: Permite personalizar a string que identifica variáveis dinâmicas.
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

As variáveis dinâmicas são um conceito abreviado que permite copiar valores de uma variável para outra. Eles são valiosos para valores variáveis longos, pois ajudam a encurtar a duração do URL de uma solicitação de imagem. Consulte Variáveis [](../page-vars/dynamic-variables.md) dinâmicas para obter mais informações sobre esse conceito.

Por padrão, as variáveis dinâmicas usam o prefixo `D=`. A `dynamicVariablePrefix` variável permite personalizar a string que identifica variáveis dinâmicas. É sensível a maiúsculas e minúsculas.

## Prefixo de variável dinâmica no Adobe Experience Platform Launch

O Prefixo de variável dinâmica é um campo sob a opção Variáveis  globais ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda o acordeão Variáveis  globais, que revela o campo Prefixo [!UICONTROL da variável] dinâmica.

Esse campo contém `D=` por padrão. Você pode alterar o valor se quiser usar um prefixo de variável dinâmica diferente. Você pode usar qualquer valor desejado, desde que ele corresponda à codificação de caracteres do site.

## s.dynamicVariablePrefix no AppMeasurement e no editor de código personalizado Iniciar

A `s.dynamicVariablePrefix` variável é uma string que pode conter qualquer sequência de caracteres. Se essa variável não estiver definida, o AppMeasurement usará a string `D=` por padrão.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
