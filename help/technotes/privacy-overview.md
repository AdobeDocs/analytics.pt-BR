---
description: Visão geral de quais dados o Adobe Analytics coleta e outras considerações de privacidade.
keywords: privacidade
title: Visão geral de privacidade
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 9fd055fd747c7124d49e280af1b0acc24d79be8e
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 3%

---

# Visão geral de privacidade

A Adobe deseja habilitar sua organização para que você possa cumprir as leis e os regulamentos aplicáveis. Consulte [Privacidade do Adobe Experience Cloud](https://www.adobe.com/br/privacy/experience-cloud.html){target=_blank} para obter mais informações. Entre a Adobe Analytics e sua organização, o Adobe atua como um &quot;processador de dados&quot; e você é o &quot;controlador de dados&quot; (ou equivalente conforme as leis de privacidade e proteção de dados aplicáveis). Cabe à sua organização revelar como você usa os produtos e serviços da Adobe, pois sua organização controla exclusivamente como implementar as soluções da Adobe. Ao usar o Adobe Analytics, sua organização é responsável por seguir sua própria política de privacidade, seu contrato de serviço com o Adobe e todas as leis aplicáveis.

A Adobe recomenda seguir os seguintes conceitos abrangentes:

* **Se coletar dados pessoais, certifique-se de cumprir as leis e regulamentos de privacidade.** As variáveis personalizadas permitem coletar praticamente tudo o que você pode acessar; no entanto, você também deve considerar a política de privacidade da sua organização e as leis aplicáveis.
* **Forneça aos clientes informações de privacidade fáceis de encontrar e entender sobre a sua organização.** Informações úteis incluem links para opção de não participação, como os dados de navegação são usados e como você usa ou planeja usar os serviços de Adobe.
* **Esteja ciente das leis locais e internacionais aplicáveis a você.** Se sua organização operar em uma escala global, algumas leis internacionais poderão ser aplicadas.

## Detalhamento da coleção de dados

O Adobe oferece várias bibliotecas de coleção de dados para auxiliar no envio de dados para o Adobe. Exemplos notáveis incluem:

* **AppMeasurement**: uma biblioteca projetada para enviar dados diretamente para o Adobe Analytics.
* **SDK da Web**: uma biblioteca projetada para enviar dados para a rede de borda da Adobe Experience Platform, que então encaminha esses dados para a Adobe Analytics.
* **Tags**: uma interface do usuário baseada na Web que permite configurar sua implementação sem exigir acesso a um site ou código-fonte do aplicativo além da implementação inicial de tag. As extensões estão disponíveis para o AppMeasurement e o SDK da Web.

O Adobe Analytics pode coletar os seguintes tipos de dados:

| Tipo de dados | Detalhes | Exemplo de variáveis contendo esses dados |
| --- | --- | --- |
| Nomes de páginas ou URLs de páginas da Web no seu site | Esses dados são necessários para que o Adobe Analytics funcione. Um URL ou nome de página é necessário para cada ocorrência. | [Página](../components/dimensions/page.md), [URL da página](../components/dimensions/page-url.md) |
| Dados com base no tempo | Esses dados são necessários para que o Adobe Analytics funcione. Um carimbo de data e hora é necessário para a coleta de dados, e os dados baseados em tempo são derivados do carimbo de data e hora. | [Tempo gasto na página](../components/dimensions/time-spent-on-page.md), [Hora do dia](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Dia da semana/Fim de semana](../components/dimensions/weekday-weekend.md), [Dia da semana](../components/dimensions/day-of-week.md), [Mês do ano](../components/dimensions/month-of-year.md) |
| Dados do referenciador | As bibliotecas de coleção de dados coletam o URL de referência por padrão quando um visitante chega ao seu site. Você pode personalizar sua implementação para coletar dados dentro da sequência de consulta de um referenciador. Essa prática é comum para campanhas e rastreamento de desempenho de anúncios. | [Referenciador](../components/dimensions/referrer.md), [Domínio referenciador](../components/dimensions/referring-domain.md) |
| IDs de visitante anônimas | As bibliotecas de coleção de dados geram e fazem referência a uma ID de visitante para cada navegador que visita seu site. Essa ID é armazenada em um cookie. Se uma biblioteca de coleta de dados não puder definir um identificador de cookie, a biblioteca usará um método de fallback de identificação de visitante anônimo. Esse método envolve vincular ocorrências relacionadas à mesma visita usando o endereço IP do visitante e a sequência de agente do usuário. Se sua organização tiver a ofuscação de IP ativada, essa configuração será aplicada. Consulte [Cookies do Adobe Analytics e do navegador](cookies/cookies.md) para obter mais informações. | [Visitantes únicos](../components/metrics/unique-visitors.md) |
| IDs de visitante identificáveis | O Adobe não coleta IDs de visitante personalizadas automaticamente. No entanto, você pode personalizar sua implementação para coletar esses dados. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Termos de pesquisa externa | Os dados de pesquisa externa incluem palavras-chave que se originam de mecanismos de pesquisa. As bibliotecas de coleção de dados procuram esses dados com base no URL de referência. No entanto, muitos mecanismos de pesquisa modernos não incluem mais essas informações. | [Palavra-chave de pesquisa](../components/dimensions/search-keyword.md) |
| Termos de pesquisa interna | Os dados de pesquisa interna incluem palavras-chave originárias do site ou dos recursos de pesquisa do aplicativo. O Adobe não coleta automaticamente dados de pesquisa interna. No entanto, você pode personalizar sua implementação para coletar esses dados. Essa prática é comum para organizações que usam o Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Especificações do computador e do navegador | As bibliotecas de coleção de dados coletam automaticamente dicas de baixa entropia do navegador, como o tipo de navegador, o tipo de sistema operacional e se o dispositivo é desktop ou móvel. A configuração personalizada é necessária para coletar dicas de alta entropia, como a versão/build específica do navegador, o modelo do dispositivo ou a versão do sistema operacional. Consulte [Visão geral das dicas do cliente](client-hints.md) para obter mais informações. | [Navegador](../components/dimensions/browser.md), [Sistema operacional](../components/dimensions/operating-systems.md), [Dimensões móveis](../components/dimensions/mobile-dimensions.md), [Resolução do monitor](../components/dimensions/monitor-resolution.md) |
| Informações de geolocalização | O Adobe oferece a capacidade de ativar ou desativar a coleta de dados de geolocalização para cada site ou aplicativo (em um nível de conjunto de relatórios). A coleta de dados de geolocalização é ativada por padrão. | [Cidades](../components/dimensions/cities.md), [Regiões](../components/dimensions/regions.md), [Países](../components/dimensions/countries.md) |
| Endereço IP | O Adobe oferece a capacidade de ofuscar o último octeto ou ofuscar totalmente o endereço IP do visitante ao armazenar esses dados. Normalmente, os clientes do EMEA têm a configuração de endereço IP totalmente ofuscada por padrão. Independentemente da configuração de ofuscação, o endereço IP não está disponível como uma dimensão no Adobe Analytics; ele só é incluído em [Feeds de dados](../export/analytics-data-feed/data-feed-overview.md). | Nenhum |
| Informações de formulário fornecidas no site | Todos os tipos de implementação exigem configuração para coletar esses dados. É possível incluir esses dados em variáveis personalizadas. | [eVar](../components/dimensions/evar.md) |
| Anúncios ou links clicados em seu site | Coletado por padrão se estiver usando uma biblioteca de coleta de dados. Informações adicionais, como a localização dos cliques, estão disponíveis quando você habilita o Activity Map. | [Activity Map](../analyze/activity-map/activity-map.md), [Link de saída](../components/dimensions/exit-link.md), [Link de download](../components/dimensions/download-link.md) |
| Produtos comprados em seu site | Todos os tipos de implementação exigem configuração para coletar esses dados. O Adobe oferece várias variáveis padrão para coletar essas informações. | [Produto](../components/dimensions/product.md), [Pedidos](../components/metrics/orders.md), [Receita](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Consulte o menu de navegação em [visão geral do Dimension](../components/dimensions/overview.md) e [Visão geral das métricas](../components/metrics/overview.md) para obter mais variáveis, esse Adobe pode coletar dados em.

## Locais de processamento de dados

O Adobe mantém três locais de processamento de dados para o Adobe Analytics. Esses sites recebem dados brutos e os processam em um conjunto de relatórios, que é otimizado para armazenamento de dados e recuperação de relatórios. Esses locais de processamento de dados residem nos Estados Unidos (Oregon), Reino Unido (Londres) e Cingapura. Consulte [Visão geral de segurança do Adobe Analytics](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} para obter mais informações.
