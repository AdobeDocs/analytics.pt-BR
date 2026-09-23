---
title: Domínio de referência
description: O domínio global no qual um visitante estava antes de clicar para acessar o site.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 81%
---
# Domínio de referência

A [dimensão](overview.md) do &#39;Domínio de referência&#39; informa em quais domínios os visitantes clicam para acessar seu site. Essa dimensão é útil para entender quais sites de terceiros direcionam mais tráfego para o seu site. Um link deve existir no site externo e um visitante deve clicar nele para que o item de dimensão seja exibido.

>[!IMPORTANT]
>
>Você deve configurar os [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios para utilizar essa dimensão. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

O mesmo relatório pode mostrar resultados diferentes entre o Analysis Workspace e o Data Warehouse. O Analysis Workspace informa o domínio de referência para cada página individual, excluindo valores que correspondem a filtros internos de URL. O Data Warehouse informa somente o primeiro domínio de referência da visita e ignora filtros internos de URL.

## Preencher esta dimensão com dados

O Adobe deriva essa dimensão do [referenciador](referrer.md) de cada ocorrência, usando a parte de domínio da URL do referenciador. Não há variável a ser definida. Você deve configurar os [filtros internos de URL](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios. Se isso não for feito, poderá incluir domínios internos ou impedir que domínios externos apareçam.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do referenciador) |
| **Web SDK / campo XDM** | Nenhum (derivado do referenciador) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Visita |

A Adobe mantém o domínio referenciador para uma visita. Se um visitante sair e clicar em um link para acessar o site por um domínio diferente em uma única visita, o novo valor será atualizado e persistirá no restante da visita. Se desejar ver apenas o valor original, consulte [Domínio de Referência Original](original-referring-domain.md).

## Itens de dimensão

Os itens de dimensão incluem os domínios nos quais os visitantes clicam para acessar seu site. Se um hit não tiver dados de referenciador (definidos ou persistentes), ele será agrupado sob o item de dimensão `"Typed/Bookmarked"`. Esse item de dimensão significa que não havia valor de referenciador, como se o visitante tivesse digitado manualmente o endereço do navegador na barra de endereços ou clicado em um marcador. O item de dimensão `"Typed/Bookmarked"` também aparece para redirecionamentos que não são hospedados no Analytics. Consulte [Redirecionamentos e aliases](/help/technotes/redirects.md) no guia do usuário Technotes.

### Itens de dimensão que contenham `googleusercontent.com`

Os usuários podem ver itens de dimensão com o domínio `googleusercontent.com`.

* **Páginas em cache**: as aranhas do Google rastreiam constantemente a web e armazenam cópias de páginas caso elas estejam offline. Essas páginas em cache estão disponíveis ao lado da maioria dos resultados da pesquisa clicando no link “Em cache”. Quando um usuário clica nesse link e visualiza o conteúdo que o Google armazena em cache, `googleusercontent.com` é um item de dimensão.
* **Páginas traduzidas**: o Google oferece um serviço de tradução robusto e prático. Ao visualizar um site usando este serviço, ele é originário do `googleusercontent.com`. Esse item de dimensão será exibido se o usuário clicar em um link para retornar ao conteúdo original.
