---
title: dynamicVariablePrefix
description: Permite personalizar a cadeia de caracteres que identifica variáveis dinâmicas.
translation-type: ht
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

As variáveis dinâmicas são um conceito abreviado que permite copiar valores de uma variável para outra. Eles são valiosos para valores de variável longos, pois ajudam a encurtar a duração do URL de uma solicitação de imagem. Consulte [Variáveis dinâmicas](../page-vars/dynamic-variables.md) para obter mais informações sobre esse conceito.

Por padrão, as variáveis dinâmicas usam o prefixo `D=`. A variável `dynamicVariablePrefix` permite personalizar a cadeia de caracteres que identifica variáveis dinâmicas. Diferencia maiúsculas e minúsculas.

## Prefixo de variável dinâmica no Adobe Experience Platform Launch

O Prefixo da variável dinâmica é um campo da opção [!UICONTROL Variáveis globais] ao configurar a extensão Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Variáveis globais], que revela o campo [!UICONTROL Prefixo da variável dinâmica].

Esse campo contém `D=` por padrão. É possível alterar o valor se quiser usar um prefixo de variável dinâmica diferente. Use qualquer valor desejado, desde que ele corresponda à codificação de caracteres do site.

## s.dynamicVariablePrefix no AppMeasurement e no editor de código personalizado do Launch

A variável `s.dynamicVariablePrefix` é uma cadeia de caracteres que pode conter qualquer cadeia de caracteres. Se essa variável não estiver definida, o AppMeasurement usará a cadeia de caracteres `D=` por padrão.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
