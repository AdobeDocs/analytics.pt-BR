---
description: Descubra tudo o que você pode fazer com o Advertising Analytics, incluindo permissões necessárias e dimensões e métricas disponíveis.
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 70%

---

# Advertising Analytics

O Advertising Analytics permite que você veja todos os seus dados de pesquisa paga do Google Ads e do Microsoft Advertising lado a lado no Adobe Analytics. Anteriormente, todos os dados do Google Ads ou do Microsoft Advertising precisavam ser visualizados no Adobe Advertising Cloud (AMO) ou em cada interface de anúncio. Agora você pode obter dados de impressão, clique e custo diretamente de mecanismos de pesquisa, bem como Instâncias de ID AMO (Instâncias de clique).

Ao trazer esses dados desses mecanismos de pesquisa juntos para o Adobe Analytics, é possível analisar os mesmos dados usando a Analysis Workspace. Um novo modelo [Desempenho de pesquisa paga](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) no Workspace facilita essa análise.

![](assets/aa_aw.png)

Esta integração é destinada para os públicos-alvo a seguir:

* O **analista** que precisa coletar relatórios de desempenho para o profissional de marketing de pesquisa paga.
* O **profissional de marketing de pesquisa paga** que busca respostas para as perguntas: quanto tráfego estou enviando para nosso site e os clientes estão convertendo? Quais são minhas campanhas de publicidade mais rentáveis?


## Pré-requisitos {#prerequisites}

* O Advertising Analytics está disponível apenas para os SKUs [Select](https://www.adobe.com/br/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/br/data-analytics-cloud/analytics/prime.html) e [Ultimate](https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html) do Adobe Analytics.
* Esta funcionalidade está disponível para aqueles que não são clientes da Advertising Cloud e AMO.
* Você deve ser um Administrador do Adobe Analytics para ter acesso ao Advertising Analytics ou pertencer a um perfil de produto com [acesso](/help/integrate/c-advertising-analytics/overview.md#permissions) concedido ao Advertising Analytics.
* Para qualquer conjunto de relatórios em que você quiser exibir os dados de pesquisa do Google Ads ou do Microsoft Advertising, você deve [habilitar esses conjuntos de relatórios para o Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Configuração do Advertising Analytics]**).
* Você precisa de credenciais de logon para um usuário com permissões de edição das contas de pesquisa que deseja integrar com o Adobe Analytics, como ID e senha da conta do Google.
* No caso do Microsoft Advertising, você também precisa da [[!UICONTROL ID da Conta] e da [!UICONTROL ID da Conta do Gerente]](c-adanalytics-workflow/aa-locate-account-id.md).

## Permissões do Advertising Analytics {#permissions}

O Analytics tem duas permissões que são concedidas automaticamente a administradores do Analytics. Dessa forma, os administradores podem escolher conceder essas permissões para não administradores.

| Permissão | Definição | Conceder permissões se você estiver conectado à Adobe Experience Cloud |
| --- | --- | --- |
| Gerenciamento do Advertising Analytics | Permite que os usuários configurem/editem/exibam contas de pesquisa publicitárias. | Faça logon em [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Produtos] > [!UICONTROL Adobe Analytics] > [!UICONTROL Perfil de Produto] > [!UICONTROL guia Permissões] > [!UICONTROL Ferramentas do Analytics] > [!UICONTROL Gerenciamento do Advertising Analytics] |
| Configuração do Advertising Analytics | Permite que os usuários configurem conjuntos de relatórios que serão provisionados para o Advertising Analytics. | Faça logon em [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Produtos] > [!UICONTROL Adobe Analytics] > [!UICONTROL Perfil do Produto] > [!UICONTROL guia Permissões] > [!UICONTROL Ferramentas do Analytics] > [!UICONTROL Configuração do Advertising Analytics] |

## Dimensões e métricas do Advertising Analytics {#dimensions-metrics}

O Advertising Analytics adiciona as seguintes dimensões e métricas ao Analysis Workspace, Report Builder e à API de relatórios do Analytics.

### Dimensões

>[!IMPORTANT]
>
>Esta integração cria um novo conjunto de dimensões por meio de classificações da variável da ID do AMO. Essas novas dimensões não afetam ou modificam seus canais de marketing existentes ou as dimensões da variável de rastreamento de campanhas. A ID do AMO está conectada a um perfil de visitante quando um visitante chega no site a partir de uma publicidade de pesquisa paga. Sendo assim, as dimensões do AMO podem ser usadas para detalhar ambas as métricas do AMO fornecidas por esta integração, assim como qualquer downstream de dados capturados pelo visitante (visitas, visitantes, exibições de página, taxa de rejeição, pedidos, receita, eventos personalizados, etc.). Elas também podem ser detalhadas por outras dimensões ao fazer os relatórios de outras métricas no local.
>
>As classificações dessas métricas são atualizadas diariamente. Dessa forma, se fizer alterações ao metadados em um mecanismo de pesquisa, você pode não ver essas alterações refletidas até o dia seguinte, quando as classificações são atualizadas.

| Nome da classificação (dimensão) | Definição |
| --- | --- |
| **[!UICONTROL MatchType de Palavra-chave (AMO ID)]** | O tipo de correspondência da palavra-chave. Os valores geralmente são amplos, frases, exatos ou sem valor, caso o tipo de publicidade não tenha um tipo de correspondência. |
| **[!UICONTROL Plataforma de publicidade (AMO ID)]** | O nome do mecanismo de pesquisa. Os valores podem incluir &quot;Google AdWords&quot; ou &quot;Microsoft Bing Ads&quot;. |
| **[!UICONTROL Conta (ID AMO)]** | O nome da conta de mecanismo de pesquisa está sendo rastreado. |
| **[!UICONTROL Campanha (AMO ID)]** | O nome a campanha em sua conta de mecanismo de pesquisa. |
| **[!UICONTROL Grupo de Anúncios (ID do AMO)]** | O nome do grupo de publicidade em suas campanhas do mecanismo de pesquisa. |
| **[!UICONTROL Anúncio (ID AMO)]** | O Título do anúncio + Descrição do anúncio usado em seu anúncio. |
| **[!UICONTROL Palavra-chave (ID AMO)]** | O valor Palavra-chave da conta do mecanismo de pesquisa. |
| **[!UICONTROL Tipo de Correspondência (ID AMO)]** | O tipo de correspondência da palavra-chave atribuído à sua palavra-chave. Os valores geralmente são amplos, frases, exatos ou sem valor, caso o tipo de publicidade não tenha um tipo de correspondência. |
| **[!UICONTROL Tipo de anúncio (ID AMO)]** | O tipo de anúncio sendo fornecido, que tipicamente é “Anúncio de texto”. |
| **[!UICONTROL Título do anúncio (ID AMO)]** | O objeto de Título usado em seu Anúncio. |
| **[!UICONTROL Descrição do anúncio (ID AMO)]** | O objeto de Descrição do anúncio usado em seu Anúncio. |
| **[!UICONTROL Adicionar URL de Exibição (ID do AMO)]** | O objeto de URL de exibição do anúncio usado em seu Anúncio. |
| **[!UICONTROL URL de Destino do Anúncio (ID do AMO)]** | O URL da página de aterrissagem ou URL final atribuído a seu Anúncio. |
| **[!UICONTROL Rede (ID AMO)]** | A rede na qual a publicidade é exibida. No Advertising Analytics, esse valor sempre é “Pesquisa”. |
| **[!UICONTROL Posicionamento (ID AMO)]** | O site de posição gerenciada (para redes de conteúdo). Somente posições gerenciadas usam essa dimensão. |
| **[!UICONTROL Destino do produto (AMO ID)]** | O nome de direcionamento do produto usado em anúncios PLA (não o produto comprado). |
| **[!UICONTROL Otimização (AMO ID)]** | Não é usado pelo Advertising Analytics. É usado somente por clientes da Advertising Cloud. |
| **[!UICONTROL Dispositivo (ID AMO)]** | Não usado no momento. Espaço reservado para um possível aprimoramento de produto futuro no tipo de dispositivo de destino indicado (por exemplo, móvel, desktop) do anúncio (não do dispositivo do visitante). |

### Métricas

>[!IMPORTANT]
>
>As métricas fornecidas pelo Advertising Analytics (listadas abaixo) são dados a nível de resumo dos mecanismos de pesquisa. Elas não estão conectadas aos perfis de visitante do Analytics. Elas são conectadas apenas à variável de ID do AMO e suas dimensões de classificação associadas. Sendo assim, elas não devem ser relatadas por outras dimensões/segmentos além daqueles baseados nas dimensões de ID do AMO. Isso fará com que o Analytics exiba zeros para os dados. É possível incluí-las nas métricas calculadas com outras métricas, mas essa métrica calculada também deve ser detalhada apenas pela dimensão de ID do AMO.
>
>Essas métricas são ligadas à fonte de dados diariamente, de forma que não terão dados para o dia atual. Além disso, elas não devem ser relatadas em uma granularidade menor que diariamente.
>
>Há uma métrica de Instâncias de ID do AMO que é e definida quando a ID do AMO é configurada em uma página de aterrissagem (ou seja, um Clickthrough). Essa métrica é capturada em tempo real com a ocorrência da página de aterrissagem e está disponível para detalhamentos com outras dimensões também configuradas na página de aterrissagem.

| Nome da métrica | Definição |
| --- | --- |
| **[!UICONTROL Impressões AMO]** | O número de impressões de publicidade relatadas pelo mecanismo de pesquisa. |
| **[!UICONTROL Cliques AMO]** | O número de cliques em publicidades relatados pelo mecanismo de pesquisa. |
| **[!UICONTROL Custo AMO]** | O custo pago para cada palavra-chave/publicidade conforme relatado pelo mecanismo de pesquisa. |
