---
title: Ordem de processamento dos dados no Adobe Analytics
description: Saiba a ordem dos componentes e serviços que processam dados no Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 35%

---

# Ordem de processamento dos dados no Adobe Analytics

A Adobe oferece várias maneiras de alterar ou manipular dados antes de serem exibidos nos relatórios. Esta página mostra a ordem em que vários recursos do Adobe Analytics processam dados. Você pode usar esta lista para solucionar problemas de inconsistência de dados ou determinar o melhor recurso a ser usado quando os ajustes de dados forem necessários.

![Processando imagem da ordem](assets/processing-order.png)

## Dados antes de serem enviados para a Adobe

Antes de os dados serem enviados para a Adobe, eles normalmente são compilados no lado do cliente usando um dos seguintes métodos:

* **AppMeasurement**: um arquivo JavaScript hospedado em seu site e referenciado em cada página. Os dados são enviados diretamente para o Adobe Analytics.
* **SDK da Web da Adobe Experience Platform**: um arquivo JavaScript hospedado em seu site e referenciado em cada página. Os dados são enviados para o Adobe Experience Platform Edge Network.
* **Marcas na Coleção de Dados da Adobe Experience Platform**: um arquivo JavaScript referenciado em cada página, contendo regras criadas na interface da Coleção de Dados. A extensão do Adobe Analytics oferece uma maneira mais fácil de implementar o AppMeasurement. A extensão Web SDK oferece uma maneira mais fácil de implementar o SDK da Web.
* **API**: o AppMeasurement e o Edge Network oferecem métodos programáticos para enviar dados para o Adobe. A AppMeasurement oferece a [API de Inserção de Dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) e a [API de Inserção de Dados em Massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/); a Edge Network oferece a [API de coleção de dados](https://developer.adobe.com/data-collection-apis/docs/).

Se você enviar dados para a Edge Network, poderá configurá-los para encaminhá-los para a Adobe Analytics (bem como para muitas outras soluções da Adobe Experience Cloud). Independentemente do método de implementação, os dados de hit coletados chegam aos servidores de processamento da Adobe Analytics em um formato que pode ser analisado.

## Pré-processamento na coleção do Adobe Analytics

Quando os dados chegam ao Adobe Analytics, eles entram em uma fase de pré-processamento:

1. [**Variáveis dinâmicas**](/help/implement/vars/page-vars/dynamic-variables.md): se uma variável dinâmica for vista em qualquer parte de uma solicitação de imagem, o valor será copiado e tratado como um valor independente, seguindo em frente.
1. [**Ofuscação de IP (último octeto)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): se o conjunto de relatórios estiver configurado para ofuscar somente o último octeto, essa ofuscação se aplica aqui. Observe que a ofuscação de IP (remover IP) ocorre posteriormente no pipeline de processamento.
1. **Tabelas de pesquisa**: dimensões que dependem de tabelas de pesquisa internas da Adobe (por exemplo, a dimensão [Navegador](/help/components/dimensions/browser.md)) são combinadas ao seu valor correspondente.
1. [**Exclusão de IP**](/help/admin/tools/exclude-ip.md): todos os endereços IP que você exclui explicitamente dos relatórios são sinalizados durante esta etapa.
1. [**Regras de bot**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md): aplique a filtragem de bot padrão ou personalizada para excluir esses dados dos relatórios.
1. **Dados de geolocalização**: dimensões que dependem da pesquisa de endereço IP (por exemplo, a variável [Países](/help/components/dimensions/countries.md) ) são preenchidas.
1. [**Regras de processamento**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md): regras personalizadas aplicadas aos seus dados pela sua organização. Inclui o mapeamento de [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) às respectivas variáveis do Analytics.
1. [**Regras VISTA**](vista.md): regras flexíveis personalizadas aplicadas aos seus dados por um consultor do Adobe. As regras VISTA podem ser executadas antes ou depois das regras de processamento, dependendo das necessidades da organização. A maioria das regras VISTA geralmente é executada após as regras de processamento, mas cada organização é configurada de forma diferente. Entre em contato com a equipe de conta da Adobe para obter mais informações sobre as regras VISTA existentes.
1. **Conversão de moeda**: se a ocorrência contiver uma [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) diferente da moeda do conjunto de relatórios, todas as variáveis de moeda aplicáveis serão convertidas usando a taxa de câmbio do dia.
1. [**CEP**](/help/components/dimensions/zip-code.md): a dimensão &quot;CEP&quot; é preenchida com base nas configurações do conjunto de relatórios.

## Estágio de &quot;valor médio&quot; do pipeline de coleta de dados

Quando o pré-processamento é concluído, vários recursos usam essa forma de dados parcialmente processada, conhecida como &quot;valores médios&quot;. Antes que os dados sejam enviados para qualquer lugar, algum processamento específico de valor médio é aplicado:

1. [**Regras de processamento de canal de marketing no nível da ocorrência**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): essas regras de processamento são executadas especificamente para o Analytics Source Connector. Como ainda não há contexto de nível de visita ou visitante, essas regras de processamento presumem que uma ocorrência não é a primeira de uma visita. Os resultados da execução das regras de processamento para uma ocorrência estão disponíveis em `channel.typeAtSource` e `channel._id`.
1. [**Ofuscação de IP (remover IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): se o conjunto de relatórios estiver configurado para ofuscar completamente um endereço IP, essa ofuscação se aplica aqui (somente para valores médios).

Nesse ponto, dados de valor médio são enviados para o respectivo recurso:

* [**API Livestream**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/): conecte um aplicativo ao serviço livestream da Adobe para obter um fluxo de dados conforme são coletados.
* [**Conector Source do Analytics**](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/adobe-applications/analytics): assimilar dados do conjunto de relatórios do Adobe Analytics em um conjunto de dados do Adobe Experience Platform.
* [**Relatório em tempo real**](/help/components/c-real-time-reporting/realtime.md): fornece até três relatórios em tempo real configuráveis no Analysis Workspace.

## Processamento no nível da visita e do visitante

Até o momento, determinada ocorrência não tem conhecimento ou contexto de ocorrências que foram coletadas antes ou depois dela. Esse estágio do processamento preenche os campos de nível de visita e visitante.

1. [**Definição de visita + visitante**](/help/implement/id/overview.md): a ocorrência é identificada com base em suas variáveis de visitante contidas.
1. [**Número de visitas**](/help/components/dimensions/visit-number.md): com base em outras visitas do visitante identificado, o número de visitas é calculado.
1. **Eliminação de duplicação de eventos**: se a ocorrência contiver uma [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) ou [serialização de eventos](/help/implement/vars/page-vars/events/event-serialization.md) duplicadas, essas IDs serão verificadas e sinalizadas, respectivamente.
1. [**Regras de processamento de canal de marketing no nível da visita**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): cada ocorrência passa pelas regras de processamento de canal de marketing, e seus detalhes de canal + canal são determinados se a ocorrência corresponde a qualquer regra. Essas regras populam as dimensões [Canal de marketing](/help/components/dimensions/marketing-channel.md) e [Detalhes do canal de marketing](/help/components/dimensions/marketing-detail.md) disponíveis no Analysis Workspace.
1. **Persistência de variável**: para dimensões que têm persistência (como [eVars](/help/components/dimensions/evar.md)), esse valor é determinado nesta etapa. De modo geral, a maioria dos valores de `post` está definida aqui.
1. **ID da Transação**: se a ocorrência contiver um novo valor [`transactionID`](/help/implement/vars/page-vars/transactionid.md), um &quot;instantâneo&quot; de todos os valores com suporte será armazenado. Quando o upload de uma fonte de dados contém uma ID de transação correspondente, todos os valores com suporte desse instantâneo são incluídos nessa linha da fonte de dados.
1. [**Ofuscação de IP (remover IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): se o conjunto de relatórios estiver configurado para ofuscar completamente um endereço IP, essa ofuscação se aplica aqui após a conclusão de todo o processamento.

Nesse ponto, a ocorrência individual é registrada nas tabelas de dados do conjunto de relatórios. Após o intervalo de [latência](latency.md) padrão, está disponível no relatório.

## Alteração de dados após o processamento

Os dados no Adobe Analytics são em sua maioria permanentes; no entanto, há alguns recursos que podem permitir o ajuste ou a remoção seletiva de dados:

* [**API de reparo de dados**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): edite determinadas colunas ou exclua as linhas de dados desejadas.
* [**Governança de dados**](/help/technotes/privacy/privacy-overview.md): acomode solicitações de privacidade para excluir dados permanentemente.
* [**Classificações**](/help/components/classifications/classifications-overview.md): crie dimensões com base em regras ou dados carregados que permitem organizar os dados de forma diferente. Os dados subjacentes do conjunto de relatórios não são alterados, portanto, é possível editar ou substituir livremente os dados de classificação.
* [**Conjuntos de relatórios virtuais**](/help/components/vrs/vrs-about.md): crie uma exibição alternativa do conjunto de relatórios que possa alterar o tempo limite da visita.
