---
description: Antes de ativar essa integração, analise os itens a seguir comparando com as implantações do Adobe Analytics® e do seu software de email.
title: Antes de ativar essa integração
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Antes de ativar essa integração {#before-you-activate-this-integration}

Antes de ativar essa integração, analise os itens a seguir comparando com as implantações do Adobe Analytics® e do seu software de email.

Isso garantirá que as práticas recomendadas ou os pré-requisitos adequados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

## Requisitos do Adobe Analytics {#adobe-analytics-requirements}

Consulte as seguintes informações sobre a integração de conectores de dados, pois ela se relaciona ao Adobe Analytics:

* **Específica do conjunto de relatórios:** observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração e se o conjunto de relatórios contém dados.
* **Variáveis disponíveis e configuradas do Analytics:** essa integração requer 10 eventos personalizados e 1 eVar personalizada. Consulte [Variáveis de integração do Analytics](appfigures-before-activation.md#analytics-integration-variables).

* **Conjunto de relatórios inicializado com dados em tempo real:** se estiver criando um novo conjunto de relatórios para essa integração, ele precisará ter recebido alguns dados (pelo menos uma ocorrência) por meio dos requisitos de rastreamento em tempo real do appFigures. Se os dados em tempo real não foram registrados, o conjunto de relatórios não estará pronto para receber dados integrados da App Store.

* **Integração existente com a App Store:** essa integração preenche os dados por 13 meses. Para evitar qualquer sobreposição com provedores de dados da App Store anterior que você teve, entre em contato com o representante do appFigures. Informe-o sobre a última data em que você recebeu os dados. O appFigures ajustará o período de preenchimento retroativo de acordo.

## Requisitos do appFigures {#appfigures-requirements}

Consulte as seguintes informações sobre a integração do Data Connectors, pois ela está relacionada ao appFigures:

* **Cliente atual do appFigures:** essa integração requer que você seja um usuário do Adobe e do appFigures. Se você não for um usuário do AppFigures Enterprise Plan, não terá as informações necessárias para concluir o assistente de integração. Visite o appFigures na Web para obter mais informações.
* **Chave de conta do appFigures:** é necessária uma Chave de conta appFigures para ativar o appFigures Data Connector. Essa chave de conta pode ser gerada na seção &quot;Complementos&quot;. Consulte [Configurar a integração](../appfigures-overview/t-appfigures-integration.md) para obter mais informações.

* **Finalização de dados:** as informações de download, vendas e classificação são sincronizadas todos os dias nos 7 dias anteriores. Após 7 dias, os dados são considerados finais e não são mais atualizados.

## Preços {#pricing}

Essa integração do Data Connectors inclui considerações sobre preços que você precisa saber.

As seguintes seções contêm mais informações:

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Atualmente, não há tarifas para ativar essa integração. No entanto, você pode notar um pequeno aumento na chamada do servidor devido à importação das fontes de dados.

### Considerações sobre preços do appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Atualmente, não há tarifas associadas a essa integração. No momento, essa integração está disponível somente para clientes Enterprise. [Entre em contato com o appFigures](https://appfigures.com/support/contact) para obter mais informações.

## Variáveis de integração do Analytics {#analytics-integration-variables}

A integração do Data Connectors do appFigures usa variáveis do Analytics para rastrear várias métricas do appFigures.

A tabela a seguir descreve as variáveis do Analytics ativadas automaticamente para a integração do appFigures.

### Variáveis obrigatórias {#section-3ca8dc46bab0436cba0c9ef827c8356a}

> [!NOTE] Essa integração usa variáveis dedicadas para os dados da loja de aplicativos, de modo que não é necessário atribuir variáveis e eventos de comércio personalizados.

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| eVar | ID do objeto da App Store | Importado do appFigures. | Configure essa eVar com expiração de visita, alocação mais recente e relações secundárias básicas. |
| evento (numérico) | Downloads da App Store | Importado do appFigures. | O número de downloads de aplicativos para dispositivos móveis. |
| evento (numérico) | Compras na App Store (no aplicativo) | Importado do appFigures. | A quantidade de compras e assinaturas no aplicativo. |
| evento (numérico) | Classificação na AppStore | Importado do appFigures. | Usado para definir a métrica calculada média do appFigures. Não usado diretamente. |
| evento (numérico) | Divisor de classificação da App Store | Importado do appFigures. | Usado para definir a métrica calculada média do appFigures. Não usado diretamente. |
| evento (numérico) | Classificação na App Store | Importado do appFigures. | Usado para definir a métrica calculada média do appFigures. Não usado diretamente. |
| evento (numérico) | Divisor de classificação da App Store | Importado do appFigures. | Usado para definir a métrica calculada média do appFigures. Não usado diretamente. |
| event (moeda) | Receita da App Store (no aplicativo) | Importado do appFigures. | A quantidade de receita no aplicativo menos a tarifa da loja. |
| event (moeda) | Receita da App Store (uma vez) | Importado do appFigures. | Receita total de compras de aplicativos menos a tarifa da loja. |
| event (moeda) | Royalties da App Store (no aplicativo) | Importado do appFigures. | Não usado. |
| event (moeda) | Royalties da App Store (uma vez) | Importado do appFigures. | Não usado. |
