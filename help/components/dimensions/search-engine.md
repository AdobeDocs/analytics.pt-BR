---
title: Mecanismo de pesquisa
description: O mecanismo de pesquisa que o visitante utilizou para acessar seu site.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 93%

---

# Mecanismo de pesquisa

A [dimensão](overview.md) do &quot;Mecanismo de pesquisa&quot; informa os mecanismos de pesquisa que os visitantes utilizam para acessar seu site. Um referenciador deve atender às duas condições a seguir para ser classificado como um mecanismo de pesquisa:

* O domínio referenciador é reconhecido pela Adobe como um mecanismo de pesquisa válido;
* Existe um parâmetro de sequência de consulta de palavra-chave no URL de referência. O parâmetro da sequência de consulta pode estar em branco (como ocorre com vários mecanismos de pesquisa devido a práticas de privacidade).

Se você quiser distinguir a pesquisa paga da pesquisa natural, a [Detecção de pesquisa paga](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) é necessária. Várias dimensões estão disponíveis para mecanismos de pesquisa:

* **Mecanismo de pesquisa**: o mecanismo de pesquisa utilizado para acessar seu site, independentemente de ser pago ou natural.
* **Mecanismo de pesquisa - pago**: o mecanismo de pesquisa utilizado para acessar seu site que correspondeu à detecção de pesquisa paga.
* **Mecanismo de pesquisa - natural**: o mecanismo de pesquisa utilizado para acessar o site que não correspondeu à detecção de pesquisa paga.

## Preencher esta dimensão com dados

Essa dimensão faz referência a várias tabelas de pesquisa internas da Adobe. Cada valor se baseia no [referenciador](referrer.md) da ocorrência, que depende dos [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Verifique se a dimensão do referenciador e os filtros de URL internos estão configurados corretamente.

## Itens de dimensão

Os itens de dimensão incluem mecanismos de pesquisa utilizados para acessar seu site. Os valores de exemplo incluem `"Google"`, `"Microsoft Bing"` e `"DuckDuckGo"`. O item de dimensão `"Unspecified"` é todo o tráfego que não é de pesquisa.
