---
title: visitorID
description: Use uma ID de visitante personalizada.
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: 7adf39a7f4ae5515f629894f90f7e8edf4519893
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 71%

---

# visitorID

A Adobe usa vários métodos diferentes para identificar visitantes em seu site. A variável `visitorID` substitui todos os outros métodos de identificação de visitantes.

>[!IMPORTANT]
>
>A Adobe recomenda não usar essa variável. Em vez disso, use o [Serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).

## ID de visitante usando a extensão do Adobe Analytics

[!UICONTROL ID de visitante] é um campo da opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela o campo [!UICONTROL ID de visitante].

Atribua esse campo ao elemento de dados que contém sua ID de visitante personalizada. Não defina esse campo como um valor estático.

## s.visitorID no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.visitorID` é uma string que contém um identificador exclusivo personalizado para o visitante. Valores válidos incluem caracteres alfanuméricos de até 100 bytes. Evite usar traços, espaços, sublinhados ou símbolos nessa variável.

>[!WARNING]
>
>Se você definir a variável `visitorID` durante uma visita, os dados resultarão em dois visitantes únicos separados.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Uma implementação inválida de IDs de visitantes personalizadas pode gerar dados incorretos e relatórios com desempenho inadequado. Se essa variável tiver um valor padrão (como `"0"` ou `"NULL"`), a Adobe tratará essas ocorrências como se elas fossem o mesmo visitante. Essa situação resulta em dados incorretos, com contagens baixas de visitantes e em segmentos de nível de visitante que não funcionam como esperado. As IDs de visitante personalizadas implementadas incorretamente também apresentam grande carga nos servidores de processamento, aumentando a [latência](/help/technotes/latency.md) e diminuindo o desempenho do relatório.

## ID de visitante usando o SDK da Web e o Experience Edge

O Experience Edge permite fornecer vários identificadores usando XDMs [Mapa de identidade](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=en#using-identitymap). Cada identidade em um Mapa de identidade tem um namespace diferente. Você pode especificar qual namespace deve ser usado para a ID de visitante como parte de [configuração da sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR#analytics). Após a configuração, ao enviar um evento com um valor especificado para esse namespace, ele será usado automaticamente como a ID do visitante no Analytics.
