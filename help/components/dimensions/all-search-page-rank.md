---
title: Toda a classificação da página de pesquisa
description: Determine em qual página de um mecanismo de pesquisa um visitante clicou para acessar seu site.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 85%

---

# Toda a classificação da página de pesquisa

A [dimensão](overview.md) de &quot;Toda classificação da página de pesquisa&quot; fornece a insight em qual página de resultados de pesquisa um visitante clicou para acessar seu site. Por exemplo, se o site for exibido na segunda página dos resultados de pesquisa de um mecanismo de pesquisa, o item de dimensão para essa variável será “Página de pesquisa 2”.

## Preencher esta dimensão com dados

Para que essa dimensão funcione, é necessário que seu conjunto de relatórios tenha [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) configurados corretamente. O AppMeasurement preenche automaticamente essa dimensão sem qualquer alteração no código de implementação.

## Itens de dimensão

Se um visitante clica em seu site a partir de um mecanismo de pesquisa, o valor dessa dimensão é “Página de pesquisa” seguido pelo número da página em que ele clicou. Se uma ocorrência não se originar de um mecanismo de pesquisa, o valor dessa dimensão será “Não especificado”.
