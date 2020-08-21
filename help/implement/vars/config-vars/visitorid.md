---
title: visitorID
description: Use uma ID de visitante personalizada.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '257'
ht-degree: 100%

---


# visitorID

A Adobe usa vários métodos diferentes para identificar visitantes em seu site. A variável `visitorID` substitui todos os outros métodos de identificação de visitantes.

>[!IMPORTANT]
>
>A Adobe recomenda não usar essa variável. Em vez disso, use o [Serviço de identidade da Adobe Experience Cloud](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html).

## ID de visitante no Adobe Experience Platform Launch

[!UICONTROL ID de visitante] é um campo da opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela o campo [!UICONTROL ID de visitante].

Atribua esse campo ao elemento de dados que contém sua ID de visitante personalizada. Não defina esse campo como um valor estático.

## s.visitorID no AppMeasurement e no editor de código personalizado do Launch

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
