---
title: Ordem de processamento dos dados no Adobe Analytics
description: Saiba a ordem dos componentes e serviços que processam dados no Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 91%

---

# Ordem de processamento dos dados no Adobe Analytics

A Adobe oferece várias maneiras de alterar ou manipular dados antes de serem exibidos nos relatórios. Esta página mostra a ordem em que vários recursos do Adobe Analytics processam dados. Você pode usar esta lista para solucionar problemas de inconsistência de dados ou determinar o melhor recurso a ser usado quando os ajustes de dados forem necessários.

![Processamento do pedido](assets/processing-order.png)

## Dados antes de serem enviados para a Adobe

Antes de os dados serem enviados para a Adobe, eles normalmente são compilados no lado do cliente usando um dos seguintes métodos:

* **AppMeasurement**: um arquivo JavaScript hospedado em seu site e referenciado em cada página. Os dados são enviados diretamente para o Adobe Analytics.
* **SDK da Web da Adobe Experience Platform**: um arquivo JavaScript hospedado em seu site e referenciado em cada página. Os dados são enviados para a Rede de borda da Adobe Experience Platform.
* **Tags na Coleçao de dados da Adobe Experience Cloud**: um arquivo JavaScript referenciado em cada página, contendo regras criadas na interface da Coleção de dados. A extensão do Adobe Analytics oferece uma maneira mais fácil de implementar o AppMeasurement. A extensão Web SDK oferece uma maneira mais fácil de implementar o SDK da Web.

Se você enviar dados para a Rede de borda, poderá configurá-los para encaminhá-los para a Adobe Analytics (bem como para muitas outras soluções da Adobe Experience Cloud). Independentemente do método de implementação, uma solicitação de imagem com as variáveis desejadas é enviada para os servidores da coleção de dados da Adobe.

## Situação dos dados à medida que chegam aos servidores de coleção de dados do Adobe Analytics

Quando os dados chegam ao Adobe Analytics, os seguintes recursos ajustam os dados conforme necessário:

1. **Tabelas de pesquisa**: dimensões que dependem de tabelas de pesquisa internas da Adobe (por exemplo, a dimensão [Navegador](/help/components/dimensions/browser.md)) são combinadas ao valor correspondente.
2. [**Variáveis dinâmicas**](/help/implement/vars/page-vars/dynamic-variables.md): se uma variável dinâmica for vista em qualquer parte de uma solicitação de imagem, o valor será copiado e tratado como um valor independente, seguindo em frente.
3. [**Regras de bot**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md): aplique a filtragem de bot padrão ou personalizada para excluir esses dados dos relatórios.
4. [**Regras de processamento**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md): regras personalizadas aplicadas aos seus dados pela sua organização. Inclui o mapeamento de [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) à respectiva variável.
5. **Regras VISTA**: regras flexíveis personalizadas aplicadas aos seus dados por um consultor do Adobe. As regras VISTA podem ser executadas antes ou depois das regras de processamento, dependendo das necessidades da organização. A maioria das regras VISTA geralmente é executada após as regras de processamento, mas cada organização é configurada de forma diferente. Entre em contato com a equipe de conta do Adobe para obter mais informações sobre as regras VISTA existentes.
6. [**Regras de processamento de canal de marketing**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md): você pode usar [Regras de processamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) para preparar dados para uso nas regras de processamento do Canal de marketing.
7. **Dados de geolocalização**: dimensões que dependem da pesquisa de endereço IP (por exemplo, a variável [Países](/help/components/dimensions/countries.md) ) são preenchidas.
8. [**Ofuscação de IP**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md): se sua organização optou por ofuscar endereços IP em dados brutos, isso será feito após a conclusão de todas as outras funções de processamento.

Nesse ponto, a ocorrência individual é registrada nas tabelas de dados do conjunto de relatórios. Após o intervalo de [latência](latency.md) padrão, está disponível no relatório.

## Alteração de dados após o processamento

Os dados no Adobe Analytics são em sua maioria permanentes; no entanto, há alguns recursos que podem permitir o ajuste ou a remoção seletiva de dados:

* [**API de reparo de dados**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): edite determinadas colunas ou exclua as linhas de dados desejadas.
* [**Governança de dados**](/help/admin/admin/c-data-governance/an-gdpr-workflow.md): acomode solicitações de privacidade para excluir dados permanentemente.
* [**Classificações**](/help/components/classifications/c-classifications.md): crie dimensões com base em regras ou dados carregados que permitem organizar os dados de forma diferente. Os dados subjacentes do conjunto de relatórios não são alterados, portanto, é possível editar ou substituir livremente os dados de classificação.
* [**Conjuntos de relatórios virtuais**](/help/components/vrs/vrs-about.md): crie uma visualização alternativa do conjunto de relatórios que possa alterar o tempo limite da visita ou permitir [Análise entre dispositivos](/help/components/cda/overview.md).
