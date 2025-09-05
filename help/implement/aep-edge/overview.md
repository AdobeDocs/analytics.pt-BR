---
title: Implementar o Adobe Analytics com a Adobe Experience Platform Edge
description: Visão geral do uso de dados XDM da Experience Platform no Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 16%

---

# Implementar o Adobe Analytics com a rede de borda da Adobe Experience Platform

A rede de borda da Adobe Experience Platform permite enviar dados destinados a vários produtos a um local centralizado. A rede de borda encaminha as informações apropriadas para os produtos desejados. Esse conceito permite consolidar os esforços de implementação, especialmente abrangendo várias soluções de dados. O Adobe Analytics é um dos produtos para os quais você pode enviar dados usando a Edge Network.

## Como o Adobe Analytics lida com os dados da rede de borda

Como os dados enviados para a Edge Network e o AppMeasurement operam de forma diferente, a carga do Edge Network determina como o Adobe Analytics lida com a ocorrência. Consulte [Tipos de evento do Edge Network no Adobe Analytics](hit-types.md) para obter mais informações.

Os dados enviados para o Adobe Experience Platform Edge Network podem seguir três formatos: **Objeto XDM**, **Objeto de dados** e **Dados de contexto**. Quando um fluxo de dados encaminha dados para o Adobe Analytics, eles são traduzidos em um formato que o Adobe Analytics pode manipular.

## objeto `xdm`

Siga os esquemas que você cria com base no [XDM](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home) (Experience Data Model). O XDM oferece flexibilidade sobre quais campos são definidos como parte dos eventos. Se quiser usar um esquema predefinido específico do Adobe Analytics, você pode adicionar o [grupo de campos do esquema do Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) ao seu esquema. Depois de adicionado, é possível preencher esse esquema usando o objeto `xdm` no Web SDK para enviar dados a um conjunto de relatórios. Quando os dados chegam à Edge Network, eles traduzem o objeto XDM em um formato que a Adobe Analytics entende.

Consulte [Mapeamento de variável de objeto XDM para o Adobe Analytics](xdm-var-mapping.md) para obter uma referência completa de campos XDM e como eles são mapeados para variáveis do Analytics.

>[!TIP]
>
>Se você planeja mudar para o [Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-landing) no futuro, a Adobe recomenda não usar o grupo de campos de esquema do Adobe Analytics. Em vez disso, a Adobe recomenda [criar seu próprio esquema](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) e usar o mapeamento de sequência de dados para preencher as variáveis do Analytics desejadas. Essa estratégia não bloqueia você em um esquema de props e eVars quando estiver pronto para migrar para o Customer Journey Analytics.

## objeto `data`

Como alternativa ao uso do objeto `xdm`, você pode usar o objeto `data`. O objeto de dados é direcionado para implementações que atualmente usam o AppMeasurement, tornando a atualização para o Web SDK muito mais fácil. O Edge Network detecta a presença de campos específicos do Adobe Analytics sem a necessidade de estar em conformidade com um esquema.

Consulte [Mapeamento de variáveis de objetos de dados para o Adobe Analytics](data-var-mapping.md) para obter uma referência completa dos campos de objetos de dados e como eles são mapeados para variáveis do Analytics.

## Variáveis de dados de contexto

Envie dados para a Edge Network em qualquer formato desejado. Todos os campos que não são mapeados automaticamente para `xdm` ou `data` campos de objeto são incluídos como [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) quando encaminhados para o Adobe Analytics. Em seguida, você deve usar [Regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) para mapear os campos desejados para as respectivas variáveis do Analytics.

Por exemplo, se você tivesse um esquema XDM personalizado com aparência semelhante ao seguinte:

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

Em seguida, esses campos seriam as chaves de dados de contexto disponíveis na interface Regras de processamento:

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```
