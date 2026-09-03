---
title: dynamicVariablePrefix
description: Permite personalizar a cadeia de caracteres que identifica variáveis dinâmicas.
feature: Appmeasurement Implementation
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7Ayfh1-CNzZvurWPaQNTjWuWrgOG8t-NYwdbJLyzFP8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 71%

---

# dynamicVariablePrefix

As variáveis dinâmicas são um conceito abreviado que permite copiar valores de uma variável para outra. Eles são valiosos para valores de variável longos, pois ajudam a encurtar a duração do URL de uma solicitação de imagem. Consulte [Variáveis dinâmicas](../page-vars/dynamic-variables.md) para obter mais informações sobre esse conceito.

Por padrão, as variáveis dinâmicas usam o prefixo `D=`. A variável `dynamicVariablePrefix` permite personalizar a cadeia de caracteres que identifica variáveis dinâmicas. Diferencia maiúsculas e minúsculas.

## Prefixo da variável dinâmica usando o Web SDK

O Web SDK não usa formatação de variável dinâmica. Em vez disso, você pode usar o mapeamento da sequência de dados para preencher vários campos do Target usando um único campo do Source. Consulte [Variáveis dinâmicas usando o Web SDK](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) para obter mais informações.

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
