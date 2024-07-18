---
title: dynamicVariablePrefix
description: Permite personalizar a cadeia de caracteres que identifica variáveis dinâmicas.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 70%

---

# dynamicVariablePrefix

As variáveis dinâmicas são um conceito abreviado que permite copiar valores de uma variável para outra. Eles são valiosos para valores de variável longos, pois ajudam a encurtar a duração do URL de uma solicitação de imagem. Consulte [Variáveis dinâmicas](../page-vars/dynamic-variables.md) para obter mais informações sobre esse conceito.

Por padrão, as variáveis dinâmicas usam o prefixo `D=`. A variável `dynamicVariablePrefix` permite personalizar a cadeia de caracteres que identifica variáveis dinâmicas. Diferencia maiúsculas e minúsculas.

## Prefixo da variável dinâmica usando o SDK da Web

O SDK da Web não usa formatação de variável dinâmica. Em vez disso, você pode usar o mapeamento da sequência de dados para preencher vários campos do Target usando um único campo do Source. Consulte [Variáveis dinâmicas usando o SDK da Web](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) para obter mais informações.

Se você enviar dados diretamente para a Adobe Analytics sem estar em conformidade com um esquema, ela usará a seguinte variável:

* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.dynamicVariablePrefix`

## Prefixo da variável dinâmica usando a extensão do Adobe Analytics

O Prefixo da variável dinâmica é um campo da opção [!UICONTROL Variáveis globais] ao configurar a extensão Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Variáveis globais], que revela o campo [!UICONTROL Prefixo da variável dinâmica].

Esse campo contém `D=` por padrão. É possível alterar o valor se quiser usar um prefixo de variável dinâmica diferente. Use qualquer valor desejado, desde que ele corresponda à codificação de caracteres do site.

## s.dynamicVariablePrefix no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.dynamicVariablePrefix` é uma cadeia de caracteres que pode conter qualquer cadeia de caracteres. Se essa variável não estiver definida, o AppMeasurement usará a cadeia de caracteres `D=` por padrão.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
