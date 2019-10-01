---
description: Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.
seo-description: Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.
seo-title: Antes de ativar esta integração
title: Antes de ativar esta integração
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Antes de ativar esta integração {#before-you-activate-this-integration}

Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.

Isso garantirá que as práticas recomendadas ou pré-requisitos apropriados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

## Adobe Analytics Requirements{#adobe-analytics-requirements}

Examine as seguintes informações sobre a integração dos conectores de dados, conforme ela se relaciona ao Adobe Analytics:

* **** Conjunto de relatórios específico: Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração e se o conjunto de relatórios contém dados.
* **** Variáveis disponíveis e configuradas do Analytics: Essa integração requer 10 eventos personalizados e 1 eVar personalizada. Consulte Variáveis [de integração do](appfigures-before-activation.md#analytics-integration-variables)Analytics.

* **** Conjunto de relatórios inicializado com dados ao vivo: Se você estiver criando um conjunto de relatórios totalmente novo para essa integração, ele precisará ter recebido alguns dados (pelo menos uma ocorrência) por meio dos requisitos de rastreamento ao vivo do appFigures. Se os dados ao vivo não tiverem sido registrados, o conjunto de relatórios não estará pronto para receber dados integrados da App Store.

* **** Integração existente com a App Store: Essa integração preenche os dados por 13 meses. Para evitar qualquer sobreposição com qualquer provedor de dados da App Store anterior que você tenha tido, entre em contato com o representante do appFigures. Informe-os sobre a última data em que você recebeu os dados. o appFigures ajustará o período de preenchimento retroativo de acordo.

## appFigures Requirements{#appfigures-requirements}

Examine as seguintes informações sobre a integração dos conectores de dados, conforme ela está relacionada ao appFigures:

* **** Cliente atual do appFigures: Essa integração exige que você seja um usuário do Adobe e do appFigures. Se você não for atualmente um usuário do AppFigures Enterprise Plan, não terá as informações necessárias para concluir o assistente de integração. Visite o appFigures na Web para obter mais informações.
* **** Chave de conta do appFigures: Uma Chave de conta appFigures é necessária para ativar o Conector de dados appFigures. Essa chave de conta pode ser gerada na seção "Suplementos". Consulte [Configurar a integração](../appfigures-overview/t-appfigures-integration.md) para obter mais informações.

* **Finalização** de dados: As informações de download, vendas e classificação são sincronizadas todos os dias nos 7 dias anteriores. Após 7 dias, os dados são considerados finais e não são mais atualizados.

## Preços{#pricing}

Essa integração dos conectores de dados inclui considerações sobre preços que você precisa conhecer.

As seguintes seções contêm mais informações:

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Atualmente, não há taxas para ativar essa integração. No entanto, você pode notar um ligeiro aumento na chamada do servidor devido à importação das fontes de dados.

### Considerações sobre preços do appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Atualmente, não há taxas associadas a essa integração. No momento, essa integração está disponível somente para clientes Enterprise. Entre em [contato com o appFigures](https://appfigures.com/support/contact) para obter mais informações.

## Analytics Integration Variables{#analytics-integration-variables}

A integração dos conectores de dados para o appFigures usa variáveis do Analytics para rastrear várias métricas do appFigures.

A tabela a seguir descreve as variáveis do Analytics ativadas automaticamente para a integração do appFigures.

### Variáveis obrigatórias {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>Essa integração usa variáveis dedicadas para os dados da app store, de modo que não é necessário atribuir variáveis e eventos de comércio personalizados.

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| eVar | ID do objeto da App Store | Importado do appFigures. | Configure essa eVar com expiração de Visita, alocação mais recente e sub-relações básicas. |
| event (numérico) | Downloads da App Store | Importado do appFigures. | O número de downloads de aplicativos para dispositivos móveis. |
| event (numérico) | Compras na App Store (no aplicativo) | Importado do appFigures. | O número de compras e assinaturas no aplicativo. |
| event (numérico) | Classificação na AppStore | Importado do appFigures. | Usado para definir a métrica calculada Média de appFigures. Não usado diretamente. |
| event (numérico) | Divisor de classificação da App Store | Importado do appFigures. | Usado para definir a métrica calculada Média de appFigures. Não usado diretamente. |
| event (numérico) | Classificação na App Store | Importado do appFigures. | Usado para definir a métrica calculada Média de appFigures. Não usado diretamente. |
| event (numérico) | Divisor de classificação da App Store | Importado do appFigures. | Usado para definir a métrica calculada Média de appFigures. Não usado diretamente. |
| event (moeda) | Receita da App Store (no aplicativo) | Importado do appFigures. | A quantidade de receita no aplicativo menos a taxa da loja. |
| event (moeda) | Receita da App Store (uma vez) | Importado do appFigures. | Receita total de compras de aplicativos menos a taxa da loja. |
| event (moeda) | Royalties da App Store (no aplicativo) | Importado do appFigures. | Não usado |
| event (moeda) | Royalties da App Store (uma vez) | Importado do appFigures. | Não usado |
