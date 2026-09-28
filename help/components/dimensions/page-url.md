---
title: URL da página
description: O URL da página.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: 'https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 52%
---
# URL da página

A [dimensão](overview.md) da &#39;URL da página&#39; lista as URLs do site.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse. Se quiser usar uma dimensão de URL em outras soluções do Analytics, considere copiar o valor em uma [eVar](evar.md) em cada hit.

## Preencher esta dimensão com dados

O AppMeasurement coleta automaticamente a URL da página em cada [chamada de exibição de página (`t()`)](/help/implement/vars/functions/t-method.md). Você pode substituir o valor coletado usando a variável [`pageURL`](/help/implement/vars/page-vars/pageurl.md). Se uma URL tiver mais de 255 bytes, o estouro será armazenado no parâmetro da cadeia de caracteres de consulta `-g`. As strings de protocolo e de consulta no URL são incluídas. [As chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md) sempre removem essa dimensão, mesmo se o valor da URL existir.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`pageURL`](/help/implement/vars/page-vars/pageurl.md) |
| **Web SDK / campo XDM** | [`web.webPageDetails.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parâmetro de consulta** | [`g`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<pageUrl>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 255 bytes (sem limite fixo com estouro) |
| **Persistência** | Hit |

## Preencher uma eVar com URL

A Adobe recomenda configurar uma eVar para a sequência de caracteres associada `window.location.hostname + window.location.pathname`. Normalmente, essa sequência de caracteres funciona melhor do que `window.location.href` porque ela omite protocolos, sequências de consulta e tags de âncora.

Para a eVar corresponder exatamente à dimensão “URL da página&#39;” no Data Warehouse, é possível utilizar [variáveis dinâmicas](/help/implement/vars/page-vars/dynamic-variables.md) e definir a eVar como `D=g` em cada hit.

## Itens de dimensão

Os itens de dimensão incluem os URLs das páginas no site.
