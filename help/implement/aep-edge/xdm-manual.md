---
title: Mapear dados XDM para o Analytics manualmente
description: 'Mapear manualmente dados XDM da Experience Platform para o Adobe Analytics '
translation-type: tm+mt
source-git-commit: 717c3e23eb2c3fb2477bd77ea92a1dce744f02df
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---


# Mapear dados XDM para o Analytics manualmente

O SDK da Web da Adobe Experience Platform (AEP) inclui recursos para ajudá-lo a mapear dados manualmente entre a Plataforma e o Analytics.

Para dados XDM que não são mapeados automaticamente para o Analytics, é possível adicionar dados [de](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) contexto para corresponder ao seu [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html). Em seguida, ele pode ser usado pelas regras [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) processamento do Analytics para preencher as variáveis do Analytics.

Além disso, você pode usar um conjunto padrão de ações e listas de produtos para enviar ou recuperar dados com o SDK da Web AEP. Para fazer isso, consulte [Produtos](https://docs.adobe.com/content/help/en/experience-platform/edge/implement/commerce.html).

## Dados de contexto

Para serem usados pelo Analytics, os dados XDM são nivelados usando a notação de pontos e disponibilizados como `contextData`. A lista de pares de valores a seguir mostra um exemplo de `context data`:

```javascript
{
          "bh": "900",
          "bw": "1680",
          "c": "24",
          "c.a.d.key.[0]": "value1",
          "c.a.d.key.[1]": "value2",
          "c.a.d.object.key1": "value1",
          "c.a.d.object.key2.[0]": "value2",
          "c.a.x.environment.browserdetails.javascriptenabled": "true",
          "c.a.x.environment.type": "browser",
          "cust_hit_time_gmt": "1579781427",
          "g": "http://example.com/home",
          "gn": "home",
          "j": "1.8.5",
          "k": "Y",
          "s": "1680x1050",
          "tnta": "218287:1:0|0,218287:1:0|2,218287:1:0|1,218287:1:0|32767,218287:1:0|1,218287:1:0|0,218287:1:0|1,218287:1:0|0,218287:1:0|1",
          "user_agent": "Mozilla/5.0 AppleWebKit/537.36 Safari/537.36",
          "v": "Y"
        }
```

## Regras de processamento

Todos os dados coletados pela rede de borda podem ser acessados pelas regras [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html)processamento. No Analytics, é possível usar regras de processamento para incorporar dados de contexto às variáveis do Analytics.

Por exemplo, na regra a seguir, o Analytics é definido para preencher os termos de Pesquisa **interna (eVar2)** com os dados associados a **a.x_atag.search.term(Dados de contexto)**.

![](assets/examplerule.png)


## Schema XDM

A plataforma Experience usa schemas para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, torna-se mais fácil manter o significado e, portanto, obter valor dos dados. Os dados de contexto do Analytics funcionam com a estrutura definida pelo schema.

O exemplo a seguir mostra como o [`event` comando](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html) pode ser usado com a `xdm` opção para enviar e recuperar dados com o AEP Web SDK. Neste exemplo, o `event` comando corresponde ao Schema [Detalhes de Comércio de](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md) ExperienceEvent para que productListItems `name` e `SKU` valores sejam rastreados:


```
alloy("event",{
  "xdm":{
    "commerce":{
      "productViews":{
        "value":1
      }
    },
    "productListItems":[
      {
        "SKU":"HT105",
        "name":"Large Field Hat",
      },
      {
        "SKU":"HT104",
        "name":"Small Field Hat",
      }
    ]
  }
});
```

Para obter mais informações sobre o rastreamento de eventos com o SDK da Web AEP, consulte [Rastreamento de eventos](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html).