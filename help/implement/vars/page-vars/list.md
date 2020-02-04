---
title: listar
description: Variáveis personalizadas que contêm vários valores na mesma ocorrência.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# listar

As variáveis de lista são variáveis personalizadas que podem ser usadas da maneira que você desejar. Eles funcionam de forma semelhante às eVars, exceto que podem conter vários valores na mesma ocorrência. As variáveis de lista não têm um limite de caracteres.

Certifique-se de registrar como você usa cada variável de lista e sua lógica no documento [de design da](../../prepare/solution-design.md)solução.

> [!NOTE] As variáveis de lista armazenam os 250 valores mais recentes por visitante. Se houver mais de 250 valores únicos para um determinado visitante, os valores mais antigos não serão atribuídos a métricas.

## Configurar variáveis de lista nas configurações do conjunto de relatórios

Certifique-se de configurar cada variável de lista nas configurações do conjunto de relatórios antes de usá-las na implementação. See [Conversion variables](/help/admin/admin/conversion-var-admin/list-var-admin.md) in the Admin guide.

## Listar variáveis no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.list1 - s.list3 no AppMeasurement e Iniciar editor de código personalizado

Cada variável de lista é uma string que contém valores personalizados específicos da sua organização. Não têm uma contagem máxima de bytes; no entanto, cada valor individual tem um máximo de 255 bytes. O delimitador usado é determinado ao configurar a variável nas configurações do conjunto de relatórios. Não use espaços ao delimitar vários itens.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

> [!TIP] Se você definir valores duplicados na mesma ocorrência, a Adobe eliminará a duplicação de todas as instâncias desses valores. Por exemplo, se você definir `s.list1 = "Example,Example";`, uma instância será contada nos relatórios.

## Comparar props de lista a vars de lista

Propriedades de lista e vars de lista podem conter vários valores na mesma ocorrência. No entanto, existem várias diferenças entre esses dois tipos de variáveis.

* Qualquer prop pode se tornar um list prop. Você pode ter até 75 propriedades de lista, se cada prop for uma prop de lista. Há apenas 3 vars de lista disponíveis.
* Propriedades de lista têm um limite de 100 bytes para a variável inteira. As variáveis de lista têm um limite de 255 bytes por valor e nenhum limite de bytes total.
* Propriedades de lista não persistem além da ocorrência definida. As variáveis de lista têm qualquer configuração de expiração desejada. Entretanto, com o processamento [de tempo do](/help/components/vrs/vrs-report-time-processing.md)relatório, é possível aplicar atribuição personalizada a propriedades de lista e variáveis de lista.
