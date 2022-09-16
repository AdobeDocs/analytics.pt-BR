---
title: Ordem de processamento dos dados no Adobe Analytics
description: Saiba a ordem dos componentes e serviços que processam dados no Adobe Analytics.
source-git-commit: 65ee7ae6d838f34149eb60547d976856e4da3b17
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# Ordem de processamento dos dados no Adobe Analytics

O Adobe oferece várias maneiras de alterar ou manipular dados antes de serem exibidos nos relatórios. Esta página mostra a ordem em que vários recursos do Adobe Analytics processam dados. Você pode usar esta lista para solucionar problemas de inconsistência de dados ou determinar o melhor recurso a ser usado quando os ajustes de dados forem necessários.

## Dados antes de serem enviados para o Adobe

Antes de os dados serem enviados para o Adobe, eles normalmente são compilados no lado do cliente usando um dos seguintes métodos:

* **AppMeasurement**: Um arquivo JavaScript hospedado em seu site e referenciado em cada página. Os dados são enviados diretamente para a Adobe Analytics.
* **Adobe Experience Platform Web SDK**: Um arquivo JavaScript hospedado em seu site e referenciado em cada página. Os dados são enviados para o Adobe Experience Edge.
* **Tags na coleta de dados do Adobe Experience Cloud**: Uma referência do JavaScript em cada página, contendo regras criadas na interface do usuário da coleta de dados. A extensão Adobe Analytics oferece uma maneira mais fácil de implementar o AppMeasurement. A extensão Web SDK oferece uma maneira mais fácil de implementar o SDK da Web.

Se você enviar dados para o Adobe Experience Edge, poderá configurá-los para encaminhá-los para o Adobe Analytics (bem como para muitas outras soluções da Adobe Experience Cloud). Independentemente do método de implementação, uma solicitação de imagem com as variáveis desejadas é enviada para os servidores de coleta de dados do Adobe.

## Dados à medida que chegam aos servidores de coleta de dados da Adobe Analytics

Quando os dados chegam ao Adobe Analytics, os seguintes recursos ajustam os dados conforme necessário:

1. **Tabelas de pesquisa**: Dimension que dependem de tabelas de pesquisa internas do Adobe (por exemplo, a variável [Navegador](/help/components/dimensions/browser.md) ) corresponde ao valor correspondente.
2. [**Variáveis dinâmicas**](/help/implement/vars/page-vars/dynamic-variables.md): Se uma variável dinâmica for vista em qualquer parte de uma solicitação de imagem, o valor será copiado e tratado como um valor independente, seguindo em frente.
3. [**Regras de bot**](/help/admin/admin/bot-removal/bot-rules.md): Aplique a filtragem de bot padrão ou personalizada para excluir esses dados dos relatórios.
4. [**Regras de processamento**](/help/admin/admin/c-processing-rules/processing-rules.md): Regras personalizadas aplicadas aos seus dados pela sua organização. Inclui o mapeamento de [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) à respectiva variável.
5. **Regras VISTA**: Regras flexíveis personalizadas aplicadas aos seus dados por um consultor do Adobe. As regras VISTA podem ser executadas antes ou depois das regras de processamento, dependendo das necessidades da organização. A maioria das regras VISTA geralmente é executada após as regras de processamento, mas cada organização é configurada de forma diferente. Entre em contato com o Gerente de conta do Adobe para obter mais informações sobre as regras VISTA existentes.
6. [**Regras de processamento de canal de marketing**](/help/components/c-marketing-channels/c-rules.md): Você pode usar [Regras de processamento](/help/admin/admin/c-processing-rules/processing-rules.md) preparar dados para uso nas regras de processamento do Canal de marketing.
7. **Dados de geolocalização**: Dimension que dependem da pesquisa de endereço IP (por exemplo, a variável [Países](/help/components/dimensions/countries.md) ) são preenchidas.
8. [**Ofuscação de IP**](/help/admin/admin/general-acct-settings-admin.md): Se sua organização optou por ofuscar endereços IP em dados brutos, isso será feito após a conclusão de todas as outras funções de processamento.

Nesse ponto, a ocorrência individual é registrada nas tabelas de dados do conjunto de relatórios. Após o padrão [latência](latency.md) está disponível no relatório.

## Alteração de dados após o processamento

Os dados no Adobe Analytics são em sua maioria permanentes; no entanto, há alguns recursos que podem permitir o ajuste ou a remoção seletiva de dados:

* [**API de reparo de dados**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Edite determinadas colunas ou exclua as linhas de dados desejadas.
* [**Governança de dados**](/help/admin/c-data-governance/an-gdpr-workflow.md): Acomodar solicitações de privacidade para excluir dados permanentemente.
* [**Classificações**](/help/components/classifications/c-classifications.md): Crie dimensões com base em regras ou dados carregados que permitem organizar os dados de forma diferente. Os dados subjacentes do conjunto de relatórios não são alterados, portanto, é possível editar ou substituir livremente os dados de classificação.
* [**Conjuntos de relatórios virtuais**](/help/components/vrs/vrs-about.md): Crie uma visualização alternativa do conjunto de relatórios que possa alterar o tempo limite da visita ou permitir [Análise entre dispositivos](/help/components/cda/overview.md).
