---
title: visitorID
description: Use uma ID de visitante personalizada.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
TQID: https://experienceleague.adobe.com/NVNZ5qIzAa3ztoH2JIHxpGGskQAATqA0EUOZbspauzY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 510
ht-degree: 20%

---

# visitorID

O Adobe usa vários métodos diferentes para [identificar visitantes](../../id/overview.md) no site. **A variável `visitorID` substitui todos os outros métodos de identificação de visitantes.**

>[!IMPORTANT]
>
>A Adobe recomenda não usar essa variável. Em vez disso, use o [Serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).

## Como o Analytics usa o `visitorID`

Essa variável é uma substituição da ID de visitante manual que substitui todas as outras formas de identificação do visitante. Para ser contado como um único visitante, cada ocorrência de uma pessoa deve usar o mesmo valor `visitorID`.

* As ocorrências que omitem `visitorID` retornam a outro método de identificação de visitante e são tratadas como um visitante separado.
* As ocorrências que usam mais de um valor `visitorID` são tratadas como visitantes separados.
* O Adobe não compila as ocorrências que usam IDs de visitante diferentes juntas.

Consulte [Identificação do visitante no Adobe Analytics](../../id/overview.md) para obter detalhes sobre a precedência de identificação e por que a combinação de identificadores pode aumentar as contagens de visitantes.

>[!WARNING]
>
>Defina `visitorID` somente se você puder garantir que ele seja definido em cada ocorrência para essa pessoa e que o valor nunca seja alterado. Configurá-lo em apenas algumas ocorrências, introduzi-lo parcialmente em uma visita (como na autenticação) ou alterá-lo entre ocorrências divide a atividade de um único visitante em vários visitantes.

>[!CAUTION]
>
>Valores inválidos de ID de visitante personalizada podem causar dados incorretos e relatórios com desempenho insatisfatório. Se essa variável contiver um valor padrão ou de espaço reservado (como `"0"` ou `"NULL"`), a Adobe tratará essas ocorrências como se elas fossem o mesmo visitante. Essa situação resulta em dados incorretos, com contagens artificialmente baixas de visitantes e em segmentos de nível de visitante que não funcionam como esperado. As IDs de visitante personalizadas implementadas incorretamente também podem apresentar grande carga nos servidores de processamento, aumentando a [latência](/help/technotes/latency.md) e diminuindo o desempenho do relatório.

## ID de visitante usando a extensão do Adobe Analytics

[!UICONTROL ID de visitante] é um campo da opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Selecione a propriedade de tag desejada.
3. Vá para a guia [!UICONTROL Extensões] e selecione o botão **[!UICONTROL Configurar]** no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela o campo [!UICONTROL ID de visitante].

Atribua esse campo ao elemento de dados que contém sua ID de visitante personalizada. **Não defina este campo como um valor estático único para todos os visitantes.** Use um elemento de dados que resolva por visitante e permaneça constante em todas as ocorrências.

## s.visitorID no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.visitorID` é uma string que contém um identificador exclusivo personalizado para o visitante. Valores válidos incluem caracteres alfanuméricos de até 100 bytes. Evite usar traços, espaços, sublinhados ou símbolos nessa variável.

```js
s.visitorID = "abc123";
```

## ID de visitante usando o Web SDK

O Adobe Experience Platform Edge Network permite fornecer vários identificadores usando o [Mapa de identidade](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap) do XDM. Cada identidade em um Mapa de identidade tem um namespace diferente. Você pode especificar qual namespace deve ser usado para a ID de visitante como parte da [configuração da sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics). Após configurar esse campo, ao enviar um evento com um valor especificado para esse namespace, ele será usado automaticamente como a ID de visitante no Analytics.
