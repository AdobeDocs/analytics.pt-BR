---
title: Referenciador
description: O URL no qual um visitante estava antes de clicar para acessar seu site.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 96%

---

# Referenciador

A [dimensão](overview.md) de &quot;Referenciador&quot; relata em quais URLs os visitantes estavam quando clicaram para acessar seu site. Essa dimensão é útil para entender quais URLs específicos direcionam mais tráfego para o site. Um link deve existir no URL externo e um visitante deve clicar nele para que o item de dimensão seja exibido.

>[!IMPORTANT]
>
>Você deve configurar os [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios para utilizar essa dimensão. Falhas ao configurar filtros de URL internos podem incluir URLs internos ou impedir que URLs externos apareçam.

O mesmo relatório pode mostrar resultados diferentes entre o Analysis Workspace e o Data Warehouse. O Analysis Workspace informa o referenciador de cada página individual, excluindo valores que correspondem a filtros internos de URL. O Data Warehouse informa somente o primeiro referenciador da visita e ignora filtros internos de URL.

## Preencher esta dimensão com dados

Essa dimensão precisa ser configurada na interface do Analytics e os dados em solicitações de imagem.

* Em sua implementação, essa dimensão recupera dados da [`r` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Você pode usar a substituição da variável [`referrer`](/help/implement/vars/page-vars/referrer.md) para configurá-la manualmente. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente. Se um método de coleta de dados diferente do AppMeasurement for utilizado (por meio da API), inclua o parâmetro da sequência de consulta `r` em solicitações de imagem.
* Na interface do Analytics, é necessário configurar os [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios. Falhas ao configurar filtros de URL internos podem incluir URLs internos ou impedir que URLs externos apareçam.

## Itens de dimensão

Os itens de dimensão incluem os URLs nos quais os visitantes clicam para acessar seu site. Se uma ocorrência não tiver dados de referenciador, ela será agrupada sob o item de dimensão `"Typed/Bookmarked"`. Esse item de dimensão significa que não havia valor de referenciador, como se o visitante tivesse digitado manualmente o endereço do navegador na barra de endereços ou clicado em um marcador. O item de dimensão `"Typed/Bookmarked"` também aparece para redirecionamentos que não são hospedados no Analytics. Consulte [Redirecionamentos e aliases](/help/technotes/redirects.md) no guia do usuário Technotes.

### Itens de dimensão que contenham `googleusercontent.com`

Os usuários podem ver itens de dimensão com o domínio `googleusercontent.com`.

* **Páginas em cache**: as aranhas do Google rastreiam constantemente a web e armazenam cópias de páginas caso elas estejam offline. Essas páginas em cache estão disponíveis ao lado da maioria dos resultados da pesquisa clicando no link “Em cache”. Quando um usuário clica nesse link e visualiza o conteúdo que o Google armazena em cache, `webcache.googleusercontent.com` é um item de dimensão típico.
* **Páginas traduzidas**: o Google oferece um serviço de tradução robusto e prático. Ao visualizar um site usando este serviço, ele é originário do `translate.googleusercontent.com`. Esse item de dimensão será exibido se o usuário clicar em um link para retornar ao conteúdo original.
