---
title: Criar uma camada de dados
description: Saiba como uma camada de dados suporta a implementação do Analytics, por que a Adobe recomenda a Camada de dados do cliente Adobe e como ler valores da camada de dados com cada método de implementação.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 7%
---
# Criar uma camada de dados

Uma camada de dados é uma estrutura do JavaScript no site que expõe os dados coletados pela implementação do Analytics, como nomes de página, detalhes do produto e IDs do pedido. O código do site grava na camada de dados e a implementação lê a partir dela para definir variáveis do Analytics. Como sua implementação não depende do HTML da página, você pode reprojetar seu site sem interromper a coleta de dados.

## Pré-requisitos

[Criar um documento de design de solução](solution-design.md): é importante que sua organização se alinhe aos requisitos de rastreamento. Esteja preparado com um documento de design de solução antes de entrar em contato com as equipes de desenvolvimento em sua organização. Os dados exigidos pelo design da solução determinam o que a camada de dados contém.

## Escolha uma especificação de camada de dados {#specifications}

A Adobe recomenda a [Adobe Client Data Layer](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/acdl/overview) (ACDL) para implementações novas ou reestruturadas. ACDL é uma biblioteca JavaScript de código aberto que fornece ao seu site uma maneira padrão de enviar dados e eventos para uma matriz global `adobeDataLayer`. Tags, o Web SDK e o AppMeasurement podem ler a partir delas, e os Componentes principais do Adobe Experience Manager podem preenchê-las automaticamente.

Sua organização pode usar outras especificações, como a [CEDDL (Camada de Dados Digitais da Experiência do Cliente](https://www.w3.org/2013/12/ceddl-201312.pdf)), que armazena dados em um objeto global `digitalData` ou em uma especificação personalizada. O mais importante é que sua organização se alinhe a uma especificação que atenda às suas necessidades.

A tabela a seguir compara o ACDL com camadas de dados baseadas em objetos, como o CEDDL:

| | Camada de Dados de Clientes Adobe (`adobeDataLayer`) | Camada de dados baseada em objetos, como CEDDL (`digitalData`) |
| --- | --- | --- |
| Como o código do site grava dados | Objetos de push: `adobeDataLayer.push({ page: { name: "Home" } })` | Define propriedades: `digitalData.page.pageInfo.pageName = "Home"` |
| Como a implementação lê um valor | `adobeDataLayer.getState("page.name")` ou um elemento de dados **estado calculado da camada de dados** da extensão de marca da Camada de Dados do Cliente Adobe | `digitalData.page.pageInfo.pageName` ou um elemento de dados da **Variável JavaScript** da extensão de tag principal |
| Como a implementação sabe que os dados estão prontos | O código do site envia um evento por push, como `{ event: "page view" }`, e sua implementação o escuta. Os ouvintes também são executados para eventos que foram enviados antes de serem adicionados. | Sua implementação deve ler o objeto depois que o código do site terminar de preenchê-lo, por exemplo, usando uma regra de Chamada direta. |

## Exemplo de camada de dados {#example}

A ACDL não requer uma estrutura de dados específica. Projete a estrutura em torno do documento de design da solução e documente-a para todos que gravem ou leem na camada de dados. Os exemplos neste guia usam a seguinte estrutura.

Quando uma página é carregada, o código do site envia os dados da página e um evento de exibição de página:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

Quando um visitante conclui uma compra, o código do site envia os detalhes do pedido e um evento de compra:

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

A ACDL mescla cada push em um único objeto chamado estado calculado, que é lido pela implementação. Os objetos de evento informam a implementação quando lê-la. Consulte [Dados e o estado calculado](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state) e [Eventos](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events).

## Fluxo de trabalho {#workflow}

A implementação do Adobe Analytics usando uma camada de dados geralmente segue estas etapas:

1. **Trabalhe com a equipe de desenvolvimento do site para implementar uma camada de dados**: a equipe de desenvolvimento do site é responsável principalmente por garantir que a camada de dados contenha valores corretos. Consulte esta página com a equipe de desenvolvimento do site para garantir que as expectativas estejam alinhadas entre as equipes. Consulte [Instalar a Camada de Dados de Clientes Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/acdl/install).
1. **Valide sua camada de dados usando um console do navegador**: abra o console de desenvolvedor do navegador, o que você pode fazer na maioria dos navegadores com a chave `F12`. Execute `adobeDataLayer.getState()` para ver o estado calculado, ou `adobeDataLayer.getState("page.name")` para ver um único valor. Consulte [Verificar a instalação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/acdl/install#verify).
1. **Conectar a camada de dados ao Adobe Analytics**: essa etapa varia de acordo com o método de implementação de sua organização. Consulte [Conectar a camada de dados ao Adobe Analytics](#connect).

## Conectar a camada de dados ao Adobe Analytics {#connect}

A tabela a seguir mostra como cada método de implementação lê a Camada de dados de clientes Adobe:

| Método de implementação | Como ler a camada de dados | Mais informações |
| --- | --- | --- |
| Extensão da tag do SDK da web | Acione regras com o evento **push de camada de dados** da extensão de Camada de Dados do Cliente Adobe. Mapeie os valores da camada de dados para campos XDM ou para o objeto `data` com a ação **Atualizar variável** do Web SDK e envie-os com a ação **Enviar evento**. | [Enviar dados da Camada de Dados de Clientes Adobe com a Web SDK](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/acdl/web-sdk), [mapeamento do campo de objeto XDM](../aep-edge/xdm-var-mapping.md) e [mapeamento do campo de objeto de dados](../aep-edge/data-var-mapping.md) |
| Biblioteca JavaScript do Web SDK | Analise eventos de camada de dados com `addEventListener()` e defina campos XDM ou `data` a partir da camada de dados ao chamar `sendEvent`. | [Enviar dados da Camada de Dados de Clientes Adobe com a Web SDK](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/acdl/web-sdk), [mapeamento do campo de objeto XDM](../aep-edge/xdm-var-mapping.md) e [mapeamento do campo de objeto de dados](../aep-edge/data-var-mapping.md) |
| Extensão do Analytics | Acione regras com o evento de **push de camada de dados** e crie elementos de dados de **estado computado da camada de dados** a partir da extensão de Camada de Dados de Clientes Adobe. Atribua os elementos de dados às variáveis do Analytics na ação **Definir variáveis** e envie os dados com a ação **Enviar sinal**. | [Mapear objetos de camada de dados para elementos de dados](../launch/layer-to-elements.md) e [Mapear elementos de dados para variáveis do Analytics](../launch/elements-to-variable.md) |
| AppMeasurement | Leia os valores com `getState()` depois que o ACDL for carregado e chame `s.t()`. | [Ler a camada de dados com o AppMeasurement](#appmeasurement) |

### Ler a camada de dados com o AppMeasurement {#appmeasurement}

A ACDL adiciona seu método `getState()` à matriz `adobeDataLayer` quando a biblioteca é carregada. Para verificar se a biblioteca foi carregada e se o estado calculado inclui os dados mais recentes, leia os valores dentro de um ouvinte de eventos:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

O ouvinte é executado uma vez para cada evento `page view`, incluindo eventos que foram enviados por push antes de o ouvinte ser adicionado. As páginas de variáveis neste guia, como [`pageName`](../vars/page-vars/pagename.md), mostram como ler valores individuais com `getState()`. Use esses exemplos dentro de um ouvinte como este ou no editor de código personalizado de uma regra de extensão do Analytics que um evento de **push de camada de dados** aciona.

Se sua implementação enviar mais de uma ocorrência por página, como em um aplicativo de página única, use [`clearVars()`](../vars/functions/clearvars.md) para que os valores de uma ocorrência não persistam para a próxima.

## Próximas etapas

* [Mapear objetos de camada de dados para elementos de dados](../launch/layer-to-elements.md): use a camada de dados do site nas marcas Adobe Experience Platform.
* [Documentação da Camada de Dados de Clientes Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/acdl/overview): saiba mais sobre cada método, evento e prática recomendada ACDL.
