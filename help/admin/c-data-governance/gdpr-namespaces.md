---
description: A cada ID para a qual você deseja poder pesquisar, é atribuído um namespace, que é uma sequência de caracteres personalizada que identifica essa ID em qualquer variável em que for usada em todos os conjuntos de relatórios.
seo-description: A cada ID para a qual você deseja poder pesquisar, é atribuído um namespace, que é uma sequência de caracteres personalizada que identifica essa ID em qualquer variável em que for usada em todos os conjuntos de relatórios.
seo-title: Namespaces
title: Namespaces
uuid: cab61844-3209-4980-b14c-6859de77606
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Namespaces

A cada ID para a qual você deseja poder pesquisar, é atribuído um namespace, que é uma sequência de caracteres personalizada que identifica essa ID em qualquer variável em que for usada em todos os conjuntos de relatórios.

A string de namespace é usada para identificar os campos que você deseja pesquisar ao fornecer uma ID como parte de uma solicitação de Privacidade de dados. Quando uma solicitação de privacidade de dados for enviada, a solicitação incluirá uma seção JSON especificando as IDs de pessoa de dados a serem usadas para a solicitação. Várias IDs podem ser incluídas como parte de uma única solicitação de um titular de dados. O JSON inclui:

* Um campo de “namespace” contendo a sequência de caracteres do namespace.
* Um campo de “type” que, para a maioria das solicitações do Adobe Analytics, contém o valor “analytics”.
* Um campo de “value” contendo a ID que o Analytics deve pesquisar nas variáveis de namespace associadas a cada um dos conjuntos de relatórios.

Refer to the [Experience Cloud Data Privacy API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details.

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

Também é aceitável usar `“namespaceId”: 10` `“namespace”: “AAID”` em vez de ou além de, e você pode ver outros produtos da Adobe usarem esse formulário.

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

## Cookie do Serviço de Identidade

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

O valor deve ser especificado como um número decimal de 38 dígitos. Se você estiver extraindo esse número das duas colunas mcvisid\_high/low ou post\_msvisid\_high/low de um feed de dados ou de um relatório do Data Warehouse, será necessário preencher zero cada um dos dois números para 19 dígitos e concatená-los primeiro com o valor alto.

Também é aceitável usar: `“namespaceId”: 4` em vez de ou além de `“namespace”: “ECID”` e você pode ver outros produtos da Adobe usarem esse formulário.

>[!NOTE]
>
>A Experience Cloud ID (ECID) era conhecida anteriormente como Marketing Cloud ID (MCID) e ainda é mencionada por esse nome em alguma documentação existente.
>
>Essas IDs são as únicas IDs suportadas pelo Analytics que usam um valor de "tipo" diferente de "análise".

Se o formato da parte de valor de qualquer uma dessas IDs de cookie não seguir o formato descrito para essa ID, a solicitação de Privacidade de dados falhará, com um erro de "Valor não formatado corretamente".

Você normalmente coletará essas IDs de cookies com o novo [JavaScript de privacidade](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm), que fornecerá automaticamente todos os pares de chave/valor relevantes para essas IDs JSON.

Esse código JavaScript preenche o JSON com outros pares de chave/valor além daqueles listados acima (namespace, tipo, valor), mas os campos listados acima são os mais importantes para o processamento da Privacidade de dados do Analytics e os únicos que você precisa fornecer se coletar as IDs de outra forma.

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

Para IDs em tráfego personalizado ou variáveis de conversão (props ou eVars), rotule a variável com um rótulo ID-DEVICE ou ID-PERSON e atribua seu próprio nome de namespace a esse tipo de ID. Consulte [Fornecer um namespace ao rotular uma variável como ID-DEVICE ou ID-PERSON.](gdpr-labels.md)

Também é possível ver os namespaces definidos anteriormente para outras variáveis ou conjuntos de relatórios e reutilizá-los, para que um mesmo namespace possa ser facilmente usado em todos os conjuntos de relatórios que armazenam esse tipo de ID. Também é possível atribuir o mesmo namespace a várias variáveis em um conjunto de relatórios. Por exemplo, alguns clientes armazenam uma ID do CRM em uma variável de tráfego e em uma variável de conversão (dependendo da página, às vezes, somente em uma delas ou em ambas) e podem atribuir o namespace “ID do CRM” às duas variáveis.

> [!TIP] Evite usar o nome amigável de uma variável (o nome exibido na interface do usuário do relatório) ou o número da variável (como eVar12) ao especificar o namespace para a API de privacidade de dados, a menos que seja o namespace especificado ao aplicar o rótulo ID-DEVICE ou ID-PESSOA. Usar um namespace em vez de um nome amigável permite que o mesmo bloco de identidade de usuário especifique a variável correta para vários conjuntos de relatórios. Por exemplo, se a ID estiver em eVars diferentes em alguns conjuntos de relatórios, ou se os nomes amigáveis não corresponderem (como quando o nome amigável foi localizado para um conjunto de relatórios específico).

> [!CAUTION] Os namespaces "visitorId" e "customVisitorId" são reservados para identificar o cookie de rastreamento herdado do Analytics e a ID de visitante do cliente do Analytics. Não use esses namespaces para tráfego personalizado ou variáveis de conversão.

Para obter mais informações, consulte [Fornecer um namespace ao rotular uma variável como ID-DEVICE ou ID-PERSON.](/help/admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)
