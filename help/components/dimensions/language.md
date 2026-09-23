---
title: Idioma
description: A configuração de idioma preferencial do navegador.
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 65%
---
# Idioma

A [dimensão](overview.md) de &quot;Idioma&quot; mostra os principais idiomas em que os visitantes preferem ver o conteúdo. Essa dimensão é importante quando você quer entender os idiomas preferenciais mais frequentes dos visitantes para auxiliar nas tarefas de localização.

>[!NOTE]
>
>Essa dimensão não coleta o idioma do site. Se você quiser coletar o idioma do site em uma dimensão, a Adobe recomenda usar uma variável personalizada, como uma [eVar](evar.md).

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `Accept-Language` nas solicitações de imagem. Funciona imediatamente em qualquer implementação do AppMeasurement ou da Web SDK (tags) — não há variável para definir.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (cabeçalho HTTP) |
| **Web SDK / campo XDM** | Nenhum (cabeçalho HTTP) |
| **Parâmetro de consulta** | Nenhum (usa o cabeçalho `Accept-Language`) |
| **Marca XML** | [`<language>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem nomes amigáveis nos idiomas de preferência dos visitantes. Os exemplos incluem `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` e `"Spanish (Spain)"`. Se uma solicitação de imagem não contiver um idioma válido no cabeçalho HTTP, o item de dimensão será `"None"`.
