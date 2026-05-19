---
description: A cada ID que você deseja pesquisar é atribuído um namespace, que é uma sequência personalizada que identifica essa ID em qualquer variável, onde ela é usada em todos os seus conjuntos de relatórios.
title: Namespaces
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
TQID: https://experienceleague.adobe.com/f9Pqs889VWpF4jyxX2GDBVdLyrDqWpHAkcHmDUizoGQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 942
ht-degree: 65%

---

# Namespaces

A cada ID que você deseja pesquisar é atribuído um namespace, que é uma sequência personalizada que identifica essa ID em qualquer variável, onde ela é usada em todos os seus conjuntos de relatórios.

A sequência de caracteres do namespace é usada para identificar os campos que você deseja pesquisar ao fornecer uma ID como parte de uma solicitação de Privacidade de dados. Quando uma solicitação de Privacidade de dados for enviada, ela incluirá uma seção JSON especificando as IDs dos titulares de dados que devem ser usadas. Várias IDs podem ser incluídas como parte de uma única solicitação de um titular de dados. O JSON inclui:

* Um campo &quot;namespace&quot; que contém a cadeia de caracteres do namespace.
* Um campo &quot;tipo&quot; que, para a maioria das solicitações do Adobe Analytics, contém o valor &quot;analytics&quot;.
* Um campo &quot;valor&quot; contendo a ID que o Analytics deve pesquisar nas variáveis de namespace associadas de cada um dos conjuntos de relatórios.

Consulte a [Documentação da API da Privacidade de dados corporativos do CX](https://experienceleague.adobe.com/pt-br/docs/experience-platform/privacy/api/overview) para obter mais detalhes e uma [lista de namespaces de identidade padrão](https://experienceleague.adobe.com/pt-br/docs/experience-platform/privacy/api/appendix#standard-namespaces). Consulte [Criar um processo de acesso/exclusão](https://experienceleague.adobe.com/pt-br/docs/experience-platform/privacy/api/privacy-jobs#access-delete) para obter um exemplo de solicitação.

## ID de cookies

Cookie herdado de rastreamento do Analytics, também conhecido como a Adobe Analytics ID (AAID):

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

O valor deve ser especificado como dois números hexadecimais separados por um traço. Todos os dígitos hexadecimais que são caracteres alfabéticos devem ser especificados usando letras maiúsculas. Os valores hexadecimais não devem ter zeros à esquerda (observe a diferença do mesmo valor especificado no formulário obsoleto, em que os zeros à esquerda são obrigatórios).

Também é aceitável usar `"namespaceId": 10` em vez de ou além de `"namespace": "AAID"`, e você pode ver outros produtos da Adobe usarem esse formulário.

## Cookie herdado de rastreamento do Analytics: forma obsoleta

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

O valor deve ser especificado como dois números hexadecimais de 16 dígitos ou como dois números decimais de 19 dígitos. Os números devem ser separados por traço, sublinhado ou dois-pontos. Zeros à esquerda devem ser adicionados se um dos dois números não tiver dígitos suficientes.

## Cookie do serviço de identidade

```json
{
   "namespace": "ECID",
   "type": "standard",
   "value": "00497781304058976192356650736267671594"
}
```

O valor deve ser especificado como um número decimal de 38 dígitos. Se você estiver extraindo esse número das duas colunas mcvisid\_high/low ou post\_msvisid\_high/low de um feed de dados ou do relatório Data Warehouse, você deve zerar cada um dos números até atingir 19 dígitos e concatená-los com o primeiro valor alto.

Também é aceitável usar `"namespaceId": 4` em vez de ou além de `"namespace": "ECID"`, e você pode ver outros produtos da Adobe usarem esse formulário.

>[!NOTE]
>
>A Experience Cloud ID (ECID) era conhecida anteriormente como Marketing Cloud ID (MCID) e ainda é referida por esse nome em algumas documentações existentes.
>
>Essas IDs são as únicas IDs compatíveis com o Analytics que usam um valor “type” em vez de “analytics”.

Se o formato da porção do valor de qualquer uma dessas IDs de cookie não seguir o formato descrito para essa ID, ocorrerá uma falha na solicitação de Privacidade de dados, com um erro de “Valor não formatado corretamente”.

Você normalmente coletará essas IDs de cookies com o novo [JavaScript de privacidade](https://developer.adobe.com/experience-platform-apis/references/privacy-service/), que fornecerá automaticamente todos os pares de chave/valor relevantes para essas IDs JSON.

Esse código JavaScript preenche o JSON com outros pares de chave/valor além dos listados acima (namespace, tipo, valor), mas os campos listados são os mais importantes para o processamento da Privacidade de dados do Analytics e os únicos que você precisa fornecer se coletar IDs de alguma outra maneira.

## ID de visitante personalizada

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

O namespace também é predefinido para a ID de visitante personalizada.

## IDs em variáveis personalizadas

```json
{
"namespace":"Email Address",
"type": "analytics", 
"value": "john@xyz.com" 
}, 
{
    "namespace": "CRM ID", 
    "type": "analytics",
    "value": "123456-ABCD" 
}
```

Para IDs em variáveis de conversão ou de tráfego personalizadas (props ou eVars), identifique a variável com um rótulo ID-DEVICE ou ID-PERSON, depois atribua seu próprio nome de namespace a esse tipo de ID. Consulte [Fornecer um namespace ao rotular uma variável como ID-DEVICE ou ID-PERSON.](/help/admin/tools/privacy-labeling/labels.md)

Você também pode ver os namespaces definidos anteriormente para outras variáveis ou conjuntos de relatórios e reutilizar um deles, para que o mesmo namespace possa ser usado facilmente para todos os seus conjuntos de relatórios que armazenam esse tipo de ID. Também é possível atribuir o mesmo namespace a várias variáveis em um conjunto de relatórios. Por exemplo, alguns clientes armazenam uma ID do CRM em uma variável de tráfego e uma variável de conversão (dependendo da página, às vezes ela está em uma ou outra, ou ambas) e podem atribuir o namespace &quot;ID do CRM&quot; a ambas as variáveis.

>[!TIP]
>
>Evite usar o nome amigável de uma variável (o nome exibido na interface do usuário dos relatórios) ou o número da variável (como eVar12) ao especificar o namespace para a API de Privacidade de dados, a menos que também seja o namespace especificado ao aplicar o rótulo de ID-DEVICE ou ID-PERSON a essa variável. Usar um namespace, em vez de um nome amigável, permite que o mesmo bloco de identidade do usuário especifique a variável correta para vários conjuntos de relatórios. Por exemplo, se a ID estiver em diferentes eVars em alguns conjuntos de relatórios ou se os nomes amigáveis não corresponderem (como quando o nome amigável foi localizado para um conjunto de relatórios específico).

>[!CAUTION]
>
>Os namespaces `visitorId` e `customVisitorId` são reservados para identificar o cookie de rastreamento herdado do Analytics e a ID de visitante do cliente do Analytics. Não use esses namespaces para tráfego personalizado ou variáveis de conversão.

Para obter mais informações, consulte [Fornecer um namespace ao rotular uma variável como ID-DEVICE ou ID-PERSON.](/help/admin/tools/privacy-labeling/labels.md)
