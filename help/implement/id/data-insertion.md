---
title: Identificação do visitante usando a API de inserção de dados
description: Identifique visitantes para a coleta de dados direta do Adobe Analytics e do lado do servidor com a API de inserção de dados.
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%
---
# Identificação do visitante usando a API de inserção de dados

A [API de Inserção de Dados](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) envia ocorrências para os servidores de coleção da Adobe Analytics sem uma biblioteca do lado do cliente, como o AppMeasurement ou o Web SDK. Como nenhuma biblioteca está presente para gerenciar a identidade para você, defina o identificador do visitante sozinho — no navegador para solicitações diretas de imagem ou no servidor para coleção do lado do servidor.

>[!NOTE]
>
>Esta página aborda a identidade do visitante. Para criar e enviar as próprias solicitações, consulte a [documentação da API de inserção de dados](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) no Adobe Developer.

O Adobe identifica um visitante usando a [ordem de operações](overview.md) padrão: o `vid`, depois o `aid`, `mid`, `fid` e, por fim, o endereço IP e o agente do usuário. Com a API de inserção de dados, você normalmente define um de três identificadores diretamente: ECID (`mid`), ID de visitante do Analytics (`aid`) ou ID de visitante personalizada (`vid`).

## Uso da ECID (recomendado)

A ECID (enviada como `mid`) é o identificador de visitante moderno entre soluções, compartilhado na Adobe Analytics, Adobe Target e Adobe Audience Manager. A Adobe recomenda usá-lo sempre que possível.

Obtenha a ECID com o [Serviço de ID de Visitante](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home) (`VisitorAPI.js`). Em um navegador, inicialize o serviço com sua ID de organização IMS usando [`getInstance`](https://experienceleague.adobe.com/pt-br/docs/id-service/using/id-service-api/methods/getinstance) e, em seguida, leia a ECID com [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/pt-br/docs/id-service/using/id-service-api/methods/getmcvid):

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

Envie esse valor em cada ocorrência como o parâmetro de consulta `mid`, juntamente com a ID da organização IMS como o parâmetro `mcorgid`, para que a ECID seja resolvida corretamente. Se seus dados forem encaminhados para o Audience Manager, envie também a região de [`getLocationHint`](https://experienceleague.adobe.com/pt-br/docs/id-service/using/id-service-api/methods/getlocationhint) como o parâmetro `aamlh`. Para associar seus próprios identificadores de clientes ao visitante, use [`setCustomerIDs`](https://experienceleague.adobe.com/pt-br/docs/id-service/using/id-service-api/methods/setcustomerids).

Para coleção do lado do servidor, obtenha a ECID no cliente e encaminhe-a para o servidor para enviar em cada ocorrência. Para gerar uma ECID totalmente no lado do servidor, sem um cliente, use a [integração direta](https://experienceleague.adobe.com/pt-br/docs/id-service/using/implementation/direct-integration) do Serviço de ID.

## Uso da ID de visitante do Analytics

A ID de visitante do Analytics (`aid`) está armazenada no cookie [`s_vi`](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/cookies/analytics). Quando uma ocorrência chega sem um identificador, o servidor de coleção atribui um `aid` e tenta definir um cookie contendo esse identificador. Alguns [tipos de resposta](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) também incluem esse identificador no corpo da resposta.

* **Lado do cliente (solicitações de imagem direta).** O navegador armazena o cookie `s_vi` que o servidor retorna e o envia em cada solicitação posterior para o mesmo domínio de coleção. O visitante é então reconhecido automaticamente, sem nenhum `aid` para definir a si mesmo. Como esse modelo depende de cookies, ele tem os mesmos limites de durabilidade que qualquer identidade baseada em cookies. Consulte [Identificação do visitante usando AppMeasurement](appmeasurement.md) para comportamento do cookie próprio ou de terceiros e a [ordem das operações](overview.md) para saber como a Adobe escolhe qual identificador usar. A Adobe recomenda usar uma ECID para identidade durável.

  >[!NOTE]
  >
  >Se você ler a ID de visitante diretamente do cookie `s_vi`, o cookie a envolve em dados adicionais (por exemplo, `[CS]v1|<id>[CE]`) — extrai somente a parte `<id>`. Ler a ID de uma resposta do visitante a retorna diretamente, sem análise.

* **Lado do servidor.** Um servidor não tem um jar de cookies, portanto, você mesmo armazena e reenvia o `aid`, digitado para o usuário:

  1. Procurar o `aid` armazenado para o usuário.
  1. Se você tiver um, envie-o como o parâmetro de consulta `aid`.
  1. Caso contrário, envie a ocorrência sem identificador, solicitando um tipo de resposta que retorne o `aid` atribuído, e depois armazene-a para a próxima vez.

  A primeira ocorrência sem identificador já foi atribuída ao `aid` retornado pelo servidor, portanto, você não perde dados ao enviá-la antes que tenha uma ID. Para os tipos de resposta que retornam a ID (`3` para JavaScript, `11` para XML, `10` para JSON) e o formato de solicitação, consulte [Tipo de resposta](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) na documentação da API de inserção de dados.

  Uma solicitação do lado do servidor não transporta cookies de visitante, e seu próprio endereço IP e agente do usuário pertencem ao remetente. Para atribuir as ocorrências corretamente, encaminhe também o endereço IP real do visitante (o cabeçalho `X-Forwarded-For`) e o agente do usuário (o cabeçalho `User-Agent`).

## Uso de uma ID de visitante personalizada

Se você já tiver um identificador durável que controla totalmente, poderá enviá-lo como [`visitorID`](/help/implement/vars/config-vars/visitorid.md) (`vid`) em cada ocorrência e na própria identidade de ponta a ponta. Isso se adapta a plataformas que não são de navegador e fornecem um identificador de dispositivo estável. Por exemplo, um aplicativo Unity pode enviar seu identificador de dispositivo como `vid`.

>[!IMPORTANT]
>
>Use `vid` somente quando puder garantir um valor estável em cada ocorrência:
>
>* **Os navegadores não se encaixam adequadamente.** Um navegador não tem um identificador durável que você possa preencher de forma confiável, portanto, um conjunto de navegadores `vid` tende a fragmentar ou colidir. Em vez disso, use o modelo do lado do cliente baseado em cookies.
>* **Tenha cuidado com os identificadores de autenticação.** Você não tem identificador antes que um usuário faça logon e, se o usuário fizer logoff, as ocorrências posteriores serão atribuídas a um visitante diferente. Essas ações dividem a atividade de uma pessoa em vários visitantes.

Consulte [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para obter o formato e as restrições de uma ID de visitante personalizada.
