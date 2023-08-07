---
description: Visão geral de quais dados o Adobe Analytics coleta e outras considerações de privacidade.
keywords: privacidade
title: Visão geral de privacidade
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 12%

---

# Visão geral de privacidade

Os visitantes podem saber mais sobre como a Adobe geralmente usa as informações coletadas no [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy.html). Cabe à sua organização revelar como você usa os produtos e serviços da Adobe, pois sua organização controla exclusivamente como implementar os serviços da Adobe. Sua organização é responsável por seguir sua própria política de privacidade, seu contrato de serviço com a Adobe e todas as leis aplicáveis.

A Adobe recomenda seguir os seguintes conceitos abrangentes:

* **Evite coletar informações de identificação pessoal no Adobe Analytics.** As variáveis personalizadas permitem coletar praticamente tudo o que você pode acessar; no entanto, você também deve considerar a política de privacidade da sua organização e as leis aplicáveis.
* **Forneça aos visitantes informações fáceis de encontrar e entender sobre informações de recusa.** Permita que eles se excluam de qualquer coisa que não seja estritamente necessária. A maioria dos países da União Europeia não considera os cookies de análise necessários.

## Detalhamento da coleção de dados

A Adobe Analytics coleta automaticamente ou pode coletar os seguintes tipos de dados:

| Tipo de dados | Detalhes | Exemplo de variáveis contendo esses dados |
| --- | --- | --- |
| Nomes de páginas ou URLs de páginas da Web no seu site | Sempre coletado. O URL ou o nome da página é necessário para cada ocorrência. | [Página](../components/dimensions/page.md), [URL da página](../components/dimensions/page-url.md) |
| Dados com base no tempo | Sempre coletado. O carimbo de data e hora é necessário para a coleta de dados, e os dados baseados em tempo são derivados do carimbo de data e hora. | [Tempo gasto na página](../components/dimensions/time-spent-on-page.md), [Hora do dia](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Dia da semana/Fim de semana](../components/dimensions/weekday-weekend.md), [Dia da semana](../components/dimensions/day-of-week.md), [Mês do ano](../components/dimensions/month-of-year.md) |
| Dados de páginas da Web em outros sites | O Adobe não pode coletar dados em sites não afiliados nos quais você não pode alterar o código fonte do site. O AppMeasurement coleta automaticamente o URL de referência quando um visitante chega ao seu site. Você pode personalizar sua implementação para coletar dados em cadeias de caracteres de consulta após elas chegarem ao seu site. | [Referenciador](../components/dimensions/referrer.md), [Domínio referenciador](../components/dimensions/referring-domain.md) |
| IDs de visitante anônimas | O AppMeasurement gera e faz referência a uma ID de visitante automaticamente para cada navegador que visita seu site. Essa ID é armazenada em um cookie. Se os cookies não estiverem disponíveis para uma determinada implementação, o Adobe Analytics usará um método de fallback de identificação do visitante usando o endereço IP e a sequência do agente do usuário. Consulte [Cookies do Adobe Analytics e do navegador](cookies/cookies.md) para obter mais informações. | [Visitantes únicos](../components/metrics/unique-visitors.md) |
| IDs de visitante identificáveis | O Adobe não coleta automaticamente IDs de visitante personalizadas. No entanto, você pode personalizar sua implementação para coletar esses dados. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Termos de pesquisa externa | O AppMeasurement tenta coletar automaticamente esses dados com base no URL de referência. No entanto, muitos mecanismos de pesquisa modernos não incluem mais essas informações. | [Palavra-chave de pesquisa](../components/dimensions/search-keyword.md) |
| Termos de pesquisa interna | O Adobe não coleta automaticamente dados de pesquisa interna. No entanto, você pode personalizar sua implementação para coletar esses dados, o que é uma prática comum para organizações que usam o Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Especificações do computador e do navegador | O AppMeasurement coleta automaticamente dicas de baixa entropia do navegador, como tipo de navegador, tipo de sistema operacional e se o dispositivo é desktop ou móvel. A configuração é necessária para coletar dicas de alta entropia, como a versão/build específica do navegador, o modelo do dispositivo ou a versão do sistema operacional. Consulte [Visão geral das dicas do cliente](client-hints.md) para obter mais informações. | [Navegador](../components/dimensions/browser.md), [Sistema operacional](../components/dimensions/operating-systems.md), [Dimensões móveis](../components/dimensions/mobile-dimensions.md), [Resolução do monitor](../components/dimensions/monitor-resolution.md) |
| Informações de geolocalização | O Adobe oferece a capacidade de ativar ou desativar a coleta de dados de geolocalização para cada site ou aplicativo (em um nível de conjunto de relatórios). Muitos tipos de implementação, incluindo o AppMeasurement, coletam automaticamente esses dados. | [Cidades](../components/dimensions/cities.md), [Regiões](../components/dimensions/regions.md), [Países](../components/dimensions/countries.md) |
| Endereço IP | O Adobe oferece a capacidade de ocultar o último octeto ou ocultar completamente o endereço IP do visitante ao armazenar esses dados. Normalmente, os clientes do EMEA têm endereços IP completamente ocultos por padrão. O endereço IP não está disponível como dimensão no Adobe Analytics; ele é incluído somente em dados brutos ([Feeds de dados](../export/analytics-data-feed/data-feed-overview.md)). | Nenhum |
| Informações de formulário fornecidas no site | Todos os tipos de implementação exigem configuração para coletar esses dados. É possível incluir esses dados em variáveis personalizadas. | [eVar](../components/dimensions/evar.md) |
| Anúncios ou links clicados no site | Coletado automaticamente se estiver usando o AppMeasurement. Informações adicionais, como a localização dos cliques, estão disponíveis com o Activity Map habilitado. | [Activity Map](../analyze/activity-map/activity-map.md), [Link de saída](../components/dimensions/exit-link.md), [Link de download](../components/dimensions/download-link.md) |
| Produtos comprados em seu site | Todos os tipos de implementação exigem configuração para coletar esses dados. O Adobe oferece várias variáveis padrão para armazenar essas informações. | [Produto](../components/dimensions/product.md), [Pedidos](../components/metrics/orders.md), [Receita](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Consulte o menu de navegação em [visão geral do Dimension](../components/dimensions/overview.md) e [Visão geral das métricas](../components/metrics/overview.md) para obter mais variáveis, esse Adobe pode coletar dados em.
