---
description: A cada ID para a qual você deseja poder pesquisar, é atribuído um namespace, que é uma sequência de caracteres personalizada que identifica essa ID em qualquer variável em que for usada em todos os conjuntos de relatórios.
seo-description: A cada ID para a qual você deseja poder pesquisar, é atribuído um namespace, que é uma sequência de caracteres personalizada que identifica essa ID em qualquer variável em que for usada em todos os conjuntos de relatórios.
seo-title: Namespaces
title: Namespaces
uuid: cab 61844-3209-4980-b 14 c -6859 de 777606
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Namespaces

A cada ID para a qual você deseja poder pesquisar, é atribuído um namespace, que é uma sequência de caracteres personalizada que identifica essa ID em qualquer variável em que for usada em todos os conjuntos de relatórios.

A sequência de caracteres do namespace é usada para identificar os campos que você deseja pesquisar ao fornecer uma ID como parte de uma solicitação do GDPR. Quando uma solicitação do GDPR for enviada, ela incluirá uma seção JSON especificando as IDs do titular de dados que devem ser usadas. Várias IDs podem ser incluídas como parte de uma única solicitação de um titular de dados. O JSON inclui:

* Um campo de “namespace” contendo a sequência de caracteres do namespace.
* Um campo de “type” que, para a maioria das solicitações do Adobe Analytics, contém o valor “analytics”.
* Um campo de “value” contendo a ID que o Analytics deve pesquisar nas variáveis de namespace associadas a cada um dos conjuntos de relatórios.

Consulte a [documentação da API do GDPR da Experience Cloud](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) para obter mais detalhes.

<!-- Meike, I converted this table to headings and text to fix a validation error. -Bob -->

## ID de cookies

Cookie herdado de rastreamento do Analytics, também conhecido como a Adobe Analytics ID (AAID):

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

O valor deve ser especificado como dois números hexadecimais separados por um traço. Todos os dígitos hexadecimais que são caracteres alfabéticos devem ser especificados usando letras maiúsculas. Os valores hexadecimais não devem ter zeros à esquerda (observe a diferença em relação ao mesmo valor especificado na forma obsoleta, onde zeros à esquerda eram obrigatórios).

It is also acceptable to use `“namespaceId”: 10` instead of or in addition to `“namespace”: “AAID”` and you may see some other Adobe products use that form.

## Cookie herdado de rastreamento do Analytics: forma obsoleta

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Forma obsoleta:

O valor deve ser especificado como dois números hexadecimais de 16 dígitos ou dois números decimais de 19 dígitos. Os números devem ser separados por um traço (-), sublinhado (_) ou dois pontos (:). Zeros à esquerda devem ser adicionados se um dos dois números não tiver dígitos suficientes.

## Cookie de serviço de identidade

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

O valor deve ser especificado como um número decimal de 38 dígitos. Se você estiver puxando este número das duas colunas mcvisid\_ high/low ou post\_ msvisid\_ high/low a partir de um feed de dados ou relatório do Data Warehouse, você deve colocar um zero em 19 dígitos e concatená-los com o valor alto primeiro.

It is also acceptable to use: `“namespaceId”: 4` instead of or in addition to `“namespace”: “ECID”` and you may see some other Adobe products use that form.

>[!NOTE]
>
>A Experience Cloud ID (ECID) já foi conhecida como Marketing Cloud ID (MCID) e ainda é referida por esse nome em alguma documentação existente.
>
>Essas IDs são as únicas IDs suportadas pelo Analytics que usam um valor "type" diferente de "analytics".

Se o formato da porção do valor de qualquer uma dessas IDs de cookie não seguir o formato descrito referente à ID, ocorrerá uma falha na solicitação de GDPR, com um erro de “Valor não formatado corretamente”.

Você normalmente coletará essas IDs de cookies com o novo [JavaScript de privacidade](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm), que fornecerá automaticamente todos os pares de chave/valor relevantes para essas IDs JSON.

Esse código JavaScript preenche o JSON com outros pares de chave/valor além dos listados acima (namespace, tipo, valor), mas os campos listados são os mais importantes para o processamento do GDPR do Analytics e os únicos que você precisa fornecer se coletar IDs de alguma outra maneira.

## ID de visitante personalizada

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

O namespace também é predefinido para a ID de visitante personalizada.

## IDs nas variáveis personalizadas

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

Para IDs em variáveis de conversão ou de tráfego personalizadas (props ou eVars), é necessário rotular a variável com ID-DEVICE ou ID-PERSON e atribuir seu próprio nome de namespace a esse tipo de ID. Consulte [Fornecer um namespace ao rotular uma variável como ID-DEVICE ou ID-PERSON](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7).

Também é possível ver os namespaces definidos anteriormente para outras variáveis ou conjuntos de relatórios e reutilizá-los, para que um mesmo namespace possa ser facilmente usado em todos os conjuntos de relatórios que armazenam esse tipo de ID. Também é possível atribuir o mesmo namespace a várias variáveis em um conjunto de relatórios. Por exemplo, alguns clientes armazenam uma ID do CRM em uma variável de tráfego e em uma variável de conversão (dependendo da página, às vezes, somente em uma delas ou em ambas) e podem atribuir o namespace “ID do CRM” às duas variáveis.

>[!NOTE]
>
>Não é possível usar o nome amigável de uma variável (o nome exibido na interface do usuário do relatório) ou o número da variável (como evar 12) ao especificar o namespace para a API do RGPD, a menos que também seja o namespace especificado ao aplicar o rótulo ID-DEVICE ou ID-USER a essa variável. Nesses casos, usar um namespace, em vez de um nome amigável, permite que o mesmo bloco de identidade do usuário especifique a variável correta para vários conjuntos de relatórios:

* A ID está em diferentes eVars em alguns dos conjuntos de relatórios ou
* Os nomes amigáveis não têm correspondência (por exemplo, quando o nome amigável foi localizado para um conjunto de relatórios específico)

Para obter mais informações, consulte [Fornecer um namespace ao rotular uma variável como ID-DEVICE ou ID-PERSON](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7).
