---
title: listar
description: Variáveis personalizadas que contêm vários valores na mesma ocorrência.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 63%

---

# listar

As variáveis de lista são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas funcionam de forma semelhante às eVars, mas podem conter vários valores na mesma ocorrência. As variáveis de lista não têm limite de caracteres.

Certifique-se de registrar a forma como você usa cada variável de lista e a lógica delas em [documento de design da solução](../../prepare/solution-design.md).

>[!NOTE]
>
>As variáveis de lista armazenam os 250 valores mais recentes por visitante. Se houver mais de 250 valores únicos para um determinado visitante, os valores mais antigos não serão atribuídos a métricas.

## Configurar variáveis de lista nas configurações do conjunto de relatórios

Certifique-se de configurar cada variável de lista nas configurações do conjunto de relatórios antes de usá-las na implementação. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/list-var-admin.md) no Guia de administração. Esta etapa se aplica a todos os métodos de implementação.

## Listar variáveis usando o SDK da Web

As variáveis de lista são [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) nos campos XDM `_experience.analytics.customDimensions.lists.list1.list[]` para `_experience.analytics.customDimensions.lists.list3.list[]`. Cada elemento de matriz contém um `"value"` objeto que contém cada string. Não há necessidade de fornecer um delimitador; é incluída automaticamente usando o valor especificado em [Configurações do conjunto de relatórios](/help/admin/admin/conversion-var-admin/list-var-admin.md). Por exemplo, se uma vírgula (&#39;`,`&#39;) estiver configurado como delimitador para a variável de lista 1, o seguinte objeto XDM preencherá a variável `list1` com `"Example value 1,Example value 2,Example value 3"`.

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
>O esquema Adobe XDM contém `key` além de `value` objetos em cada `list[]` matriz. O Adobe não os usa `key` ao enviar dados para o Adobe Analytics.

## Listar variáveis usando a extensão Adobe Analytics

Não há um campo dedicado na extensão Adobe Analytics para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.list1 - s.list3 no AppMeasurement e no editor de código personalizado da extensão do Analytics

Cada variável de lista é uma string que contém valores personalizados específicos para sua organização. Elas não têm uma contagem máxima de bytes; no entanto, cada valor individual tem no máximo 255 bytes. O delimitador usado é determinado ao configurar a variável no [Configurações do conjunto de relatórios](/help/admin/admin/conversion-var-admin/list-var-admin.md). Não use espaços ao delimitar vários itens.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Se você definir valores duplicados na mesma ocorrência, a Adobe desduplica todas as instâncias desses valores. Por exemplo, se você definir `s.list1 = "Brick,Brick";`, uma instância será contada nos relatórios.

## Comparar props de lista a vars de lista

Propriedades de lista e vars de lista podem conter vários valores na mesma ocorrência. No entanto, existem várias diferenças entre esses dois tipos de variáveis.

* Qualquer prop pode se tornar uma prop de lista. Você pode ter até 75 propriedades de lista se cada prop for uma prop de lista. Há apenas três vars de lista disponíveis.
* Propriedades de lista têm um limite de 100 bytes para a variável inteira. As variáveis de lista têm um limite de 255 bytes por valor e nenhum limite total de bytes.
* Propriedades de lista não persistem além da ocorrência definida. As variáveis de lista assumem a configuração de expiração que você desejar. Entretanto, usando o [processamento de tempo do relatório](/help/components/vrs/vrs-report-time-processing.md), é possível aplicar uma atribuição personalizada a propriedades de lista e variáveis de lista.
