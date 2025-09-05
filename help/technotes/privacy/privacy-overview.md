---
description: Visão geral de quais dados o Adobe Analytics coleta e outras considerações de privacidade.
keywords: privacidade
title: Visão geral de privacidade
feature: Data Governance
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 98%

---

# Visão geral de privacidade

A Adobe deseja capacitar sua organização a cumprir com as leis e regulamentos aplicáveis. Consulte [Privacidade do Adobe Experience Cloud](https://www.adobe.com/br/privacy/experience-cloud.html){target=_blank} para obter mais informações. Entre o Adobe Analytics e sua organização, a Adobe atua como um “processador de dados”, no qual você é o(a) “controlador(a) de dados” (ou equivalente, conforme as leis de privacidade e proteção de dados aplicáveis). Cabe à organização divulgar como você usa os produtos e serviços da Adobe, pois a organização controla com exclusividade a implementação das soluções da Adobe. Ao usar o Adobe Analytics, a organização é responsável por seguir a própria política de privacidade, o contrato de serviço com a Adobe e todas as leis aplicáveis.

A Adobe recomenda aderir aos seguintes conceitos abrangentes:

* **Ao coletar dados pessoais, certifique-se de cumprir as leis e regulamentos de privacidade.** As variáveis personalizadas permitem coletar praticamente tudo o que se pode acessar. No entanto, você também deve considerar a política de privacidade da organização e as leis aplicáveis.
* **Forneça a clientes informações de privacidade fáceis de encontrar e entender sobre a organização.** Informações úteis incluem links para opção de não participação, como os dados de navegação são usados e como você usa ou planeja usar os serviços da Adobe.
* **Esteja ciente das leis locais e internacionais que se aplicam a você.** Se sua organização opera em uma escala global, algumas leis internacionais podem entrar em vigor.

## Detalhamento da coleta de dados

A Adobe oferece várias bibliotecas de coleta de dados para auxiliar no envio de dados à Adobe. Exemplos notáveis incluem:

* **AppMeasurement**: uma biblioteca projetada para enviar dados diretamente para o Adobe Analytics.
* **SDK da web**: uma biblioteca projetada para enviar dados para a rede de borda da Adobe Experience Platform, que então encaminha esses dados para o Adobe Analytics.
* **Tags**: uma interface baseada na web que permite configurar sua implementação sem exigir acesso a um site ou código-fonte de aplicativo além da implementação inicial da tag. Há extensões disponíveis para o AppMeasurement e o SDK da web.

O Adobe Analytics pode coletar os seguintes tipos de dados:

| Tipo de dados: | Detalhes | Exemplos de variáveis que contêm esses dados |
| --- | --- | --- |
| Nomes de páginas ou URLs de páginas da web no site | Esses dados são necessários para que o Adobe Analytics funcione. Um URL ou nome de página é necessário para cada ocorrência. | [Página](/help/components/dimensions/page.md), [URL da página](/help/components/dimensions/page-url.md) |
| Dados baseados em tempo | Esses dados são necessários para que o Adobe Analytics funcione. Um carimbo de data/hora é necessário para a coleta de dados e os dados baseados em tempo são derivados do carimbo de data/hora. | [Tempo gasto na página](/help/components/dimensions/time-spent-on-page.md), [Hora do dia](/help/components/dimensions/hour-of-day.md), [AM/PM](/help/components/dimensions/am-pm.md), [Dia da semana/Fim de semana](/help/components/dimensions/weekday-weekend.md), [Dia da semana](/help/components/dimensions/day-of-week.md), [Mês do ano](/help/components/dimensions/month-of-year.md) |
| Dados do referenciador | As bibliotecas de coleção de dados coletam o URL referenciador por padrão quando um(a) visitante chega no site. É possível personalizar a implementação para coletar dados da string de consulta de um referenciador. Essa prática é comum para campanhas e rastreamento de desempenho de publicidade. | [Referenciador](/help/components/dimensions/referrer.md), [Domínio referenciador](/help/components/dimensions/referring-domain.md) |
| IDs de visitante anônimas | As bibliotecas de coleção de dados geram e fazem referência a uma ID de visitante para cada navegador que visita o site. Essa ID é armazenada em um cookie. Se uma biblioteca de coleção de dados não puder definir um identificador de cookies, ela usará um método substituto para identificação de visitante anônimo. Esse método envolve vincular ocorrências relacionadas à mesma visita usando o endereço IP do(a) visitante e a string de agente de usuário. Se sua organização habilitar a ofuscação de IP, essa configuração será respeitada. Consulte [Adobe Analytics e cookies de navegador](../cookies/cookies.md) para obter mais informações. | [Visitantes únicos](/help/components/metrics/unique-visitors.md) |
| IDs de visitante identificáveis | A Adobe não coleta IDs de visitante personalizadas automaticamente. No entanto, é possível personalizar a implementação para coletar esses dados. | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| Termos de pesquisa externos | Os dados de pesquisa externa incluem palavras-chave que se originam de mecanismos de pesquisa. As bibliotecas de coleção de dados procuram esses dados com base no URL referenciador. No entanto, muitos mecanismos de pesquisa modernos não incluem mais essas informações. | [Palavra-chave de pesquisa](/help/components/dimensions/search-keyword.md) |
| Termos de pesquisa interna | Os dados de pesquisa interna incluem palavras-chave originárias do site ou dos recursos de pesquisa do aplicativo. A Adobe não coleta dados de pesquisa interna automaticamente. No entanto, é possível personalizar a implementação para coletar esses dados. Essa prática é comum em organizações que usam o Adobe Analytics. | [eVar](/help/components/dimensions/evar.md) |
| Especificações do computador e do navegador | As bibliotecas de coleção de dados coletam automaticamente dicas de baixa entropia do navegador, como o tipo do navegador, o tipo do sistema operacional e se o dispositivo é desktop ou móvel. Uma configuração personalizada é necessária para coletar dicas de alta entropia, como a versão/build específica do navegador, o modelo do dispositivo ou a versão do sistema operacional. Consulte [Visão geral das dicas do cliente](../client-hints.md) para obter mais informações. | [Navegador](/help/components/dimensions/browser.md), [Sistema operacional](/help/components/dimensions/operating-systems.md), [Dimensões móveis](/help/components/dimensions/mobile-dimensions.md), [Resolução do monitor](/help/components/dimensions/monitor-resolution.md) |
| Informações de geolocalização | A Adobe oferece a capacidade de impedir a coleta da geolocalização detalhada definindo o último octeto de um endereço IP como 0. Isso torna as informações geográficas menos precisas e pode ser definido nas [configurações do conjunto de relatórios](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). | [Cidades](/help/components/dimensions/cities.md), [Regiões](/help/components/dimensions/regions.md), [Países](/help/components/dimensions/countries.md) |
| Endereço IP | A Adobe oferece a capacidade de ofuscar (hash) ou remover totalmente o endereço IP do(a) visitante ao armazenar esses dados. Clientes da EMEA geralmente têm a configuração de endereço IP ofuscada por padrão. Independentemente da configuração de ofuscação, o endereço IP não é disponibilizado como uma dimensão no Analysis Workspace, sendo incluído apenas nos [feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md). Consulte [Configurações gerais da conta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) no Guia de administração para obter detalhes sobre as configurações de ofuscação disponíveis. | Nenhum |
| Informações de formulário fornecidas no site | Todos os tipos de implementação exigem configuração para coletar esses dados. É possível incluir esses dados em variáveis personalizadas. | [eVar](/help/components/dimensions/evar.md) |
| Anúncios ou links clicados no site | Coletado se [`trackExternalLinks`](/help/implement/vars/config-vars/trackexternallinks.md) ou [`trackDownloadLinks`](/help/implement/vars/config-vars/trackdownloadlinks.md) estiver habilitado. Informações adicionais, como a localização dos cliques, são disponibilizadas ao habilitar o Activity Map. | [Activity Map](/help/analyze/activity-map/overview.md), [Link de saída](/help/components/dimensions/exit-link.md), [Link de download](/help/components/dimensions/download-link.md) |
| Produtos comprados no site | Todos os tipos de implementação exigem configuração para coletar esses dados. A Adobe oferece diversas variáveis padrão para coletar essas informações. | [Produto](/help/components/dimensions/product.md), [Pedidos](/help/components/metrics/orders.md), [Receita](/help/components/metrics/revenue.md) |

{style="table-layout:auto"}

Consulte o menu de navegação em [Visão geral das dimensões](/help/components/dimensions/overview.md) e [Visão geral das métricas](/help/components/metrics/overview.md) para encontrar mais variáveis que a Adobe pode utilizar para coletar dados.

## Locais de processamento de dados

A Adobe mantém três locais de processamento de dados para o Adobe Analytics. Esses sites recebem dados brutos e os processam em um conjunto de relatórios que é otimizado para armazenamento de dados e recuperação de relatórios. Esses locais de processamento de dados são atualmente localizados nos Estados Unidos (Oregon), Reino Unido (Londres) e Cingapura. Consulte [visão geral de segurança do Adobe Analytics](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} para obter mais informações.
