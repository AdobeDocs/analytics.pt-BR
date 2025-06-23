---
title: listar
description: Variáveis personalizadas que contêm vários valores na mesma ocorrência.
feature: Appmeasurement Implementation
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 74%

---

# listar

As variáveis de lista são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas funcionam de forma semelhante às eVars, mas podem conter vários valores na mesma ocorrência. As variáveis de lista não têm limite de caracteres.

Registre a maneira como você usa cada variável de lista e a sua lógica no [documento de design da solução](../../prepare/solution-design.md).

>[!NOTE]
>
>As variáveis de lista armazenam os valores mais recentes por visitante com base na configuração [!UICONTROL Valores máximos] em [Configurações do conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Até 250 valores são suportados. Se houver mais valores únicos do que o permitido pela configuração [!UICONTROL Valores máximos], os valores mais antigos não serão atribuídos a métricas.

## Configurar variáveis de lista nas configurações do conjunto de relatórios

Certifique-se de configurar cada variável de lista nas configurações do conjunto de relatórios antes de usá-las na implementação. Consulte [Variáveis de conversão](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md) no Guia de administração. Esta etapa se aplica a todos os métodos de implementação.

## Variáveis de lista usando o SDK da Web

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), as variáveis de lista usarão os campos XDM `xdm._experience.analytics.customDimensions.lists.list1.list[]` a `xdm._experience.analytics.customDimensions.lists.list3.list[]`. Cada elemento de matriz contém um objeto `"value"` que contém cada string. Não há necessidade de fornecer um delimitador; os servidores de coleta de dados da Adobe detectam e incluem automaticamente o delimitador correto definido nas [configurações do conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

```json
"xdm": {
  "_experience": {
    "analytics": {
      "customDimensions": {
        "lists": {
          "list1": {
            "list": [
              {
                "value": "Example value 1"
              },
              {
                "value": "Example value 2"
              },
              {
                "value": "Example value 3"
              }
            ]
          }
        }
      }
    }
  }
}
```

>[!NOTE]
>
>O esquema XDM da Adobe contém objetos `key` e `value` em cada matriz `list[]`. A Adobe não usa os objetos `key` ao enviar dados para o Adobe Analytics.

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), as variáveis de lista usarão `data.__adobe.analytics.list1` - `data.adobe.analytics.list3` após a sintaxe do AppMeasurement. Use o delimitador correto definido nas [configurações do conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

```json
"data": {
  "__adobe": {
    "analytics": {
      "list1": "Example value 1,Example value 2,Example value 3"
    }
  }
}
```

## Variáveis de lista que usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.list1 - s.list3 no AppMeasurement e no editor de código personalizado da extensão do Analytics

Cada variável de lista é uma string que contém valores personalizados específicos para sua organização. Essa variável não tem uma contagem máxima de bytes; no entanto, cada valor individual tem um limite máximo de 255 bytes. O delimitador usado é determinado ao configurar a variável nas [configurações do conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Não use espaços ao delimitar vários itens.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Se você definir valores duplicados na mesma ocorrência, a Adobe desduplica todas as instâncias desses valores. Por exemplo, se você definir `s.list1 = "Brick,Brick";`, uma instância será contada nos relatórios.

## Comparar props de lista a vars de lista

Propriedades de lista e vars de lista podem conter vários valores na mesma ocorrência. No entanto, existem várias diferenças entre esses dois tipos de variáveis.

* Qualquer prop pode se tornar uma prop de lista. Você pode ter até 75 propriedades de lista se cada prop for uma prop de lista. Há apenas três variáveis de lista disponíveis.
* Propriedades de lista têm um limite de 100 bytes para a variável inteira. As variáveis de lista têm um limite de 255 bytes por valor e nenhum limite total de bytes.
* Propriedades de lista não persistem além da ocorrência definida. As variáveis de lista assumem a configuração de expiração que você desejar. Entretanto, usando o [processamento de tempo do relatório](/help/components/vrs/vrs-report-time-processing.md), é possível aplicar uma atribuição personalizada a propriedades de lista e variáveis de lista.
