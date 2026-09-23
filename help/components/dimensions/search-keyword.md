---
title: Palavra-chave de pesquisa
description: A palavra-chave de pesquisa que o visitante utilizou para acessar seu site.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
TQID: https://experienceleague.adobe.com/4naavrC42ddsxGFJfkOJ0wzHLTa7tdMeI9nKDgVWrBY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 70%
---
# Palavra-chave de pesquisa

A [dimensão](overview.md) de &quot;Palavra-chave de pesquisa&quot; informa as palavras-chave de pesquisa que os visitantes utilizam para acessar seu site.

>[!IMPORTANT]
>
>A maioria dos mecanismos de pesquisa não passa mais a palavra-chave de pesquisa devido ao aumento das práticas de privacidade. Hits em que a Adobe reconhece um mecanismo de pesquisa, mas falta um grupo de palavras-chave no item de dimensão `"Keyword unavailable"`.

Um referenciador deve atender aos dois itens a seguir para se classificar como uma palavra-chave de pesquisa:

* O domínio referenciador é reconhecido pela Adobe como um [mecanismo de pesquisa](search-engine.md) válido;
* Existe um parâmetro de sequência de consulta de palavra-chave no URL de referência. Se uma sequência de consulta por palavras-chave existir mas não tiver um valor, ela se agrupará sob o item de dimensão `"Keyword unavailable"`.

Se você quiser distinguir a pesquisa paga da pesquisa natural, a [Detecção de pesquisa paga](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) é necessária. Várias dimensões estão disponíveis para palavras-chave de pesquisa:

* **Palavra-chave de pesquisa**: a palavra-chave de pesquisa utilizada para acessar seu site, independentemente de ser paga ou comum.
* **Palavra-chave de pesquisa - paga**: a palavra-chave de pesquisa usada para acessar seu site que corresponde à detecção de pesquisa paga.
* **Palavra-chave de pesquisa - comum**: a palavra-chave de pesquisa utilizada para acessar seu site que não corresponde à detecção de pesquisa paga.

## Preencher esta dimensão com dados

O Adobe deriva essa dimensão do mecanismo de pesquisa [referenciador](referrer.md) de cada ocorrência, extraindo a palavra-chave da sequência de consulta do referenciador. Não há variável a ser definida. Como cada valor depende do referenciador, verifique se a dimensão do referenciador e os [filtros internos de URL](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) estão configurados corretamente.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do referenciador do mecanismo de pesquisa) |
| **Web SDK / campo XDM** | Nenhum (derivado do referenciador do mecanismo de pesquisa) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem palavras-chave de pesquisa utilizadas para acessar seu site. O item de dimensão `"Unspecified"` é todo o tráfego que não é de pesquisa.
