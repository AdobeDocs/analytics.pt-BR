---
title: Mapear objetos de camada de dados para elementos de dados
description: Configure as tags para ler a partir da camada de dados.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 46%
---
# Mapear objetos de camada de dados para elementos de dados

Depois que sua organização tiver estabelecido e implementado uma camada de dados no site, você poderá mapear objetos de camada de dados para elementos de dados nas tags.

## Pré-requisitos

[Criar uma camada de dados](../prepare/data-layer.md): verifique se existe uma camada de dados no site. Embora você possa mapear qualquer objeto JavaScript ou extrair elementos CSS diretamente da página, a Adobe recomenda essa prática como último recurso. Se o layout do site mudar, os seletores de CSS usados nas tags deixarão de funcionar, causando perda de dados.

## Usar tags para criar elementos de dados

[Elementos de dados](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=pt-BR) são componentes na Coleção de dados da Adobe Experience Platform que você pode usar na ferramenta. Você pode atribuir valores variáveis na extensão do Adobe Analytics usando elementos de dados.

As etapas a seguir usam a [extensão da Camada de Dados do Cliente Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/client-data-layer/overview), que deve ser instalada na propriedade da marca.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Selecione a propriedade de tag desejada.
1. Selecione a guia **[!UICONTROL Elementos de Dados]** e selecione **[!UICONTROL Adicionar Elemento de Dados]**.

   ![criar elemento de dados](assets/createelement.png)

1. Insira um nome para o elemento de dados, como `Page name`.
1. Na lista suspensa **[!UICONTROL Extensão]**, selecione **[!UICONTROL Camada de dados de clientes Adobe]**.
1. Na lista suspensa **[!UICONTROL Tipo de Elemento de Dados]**, selecione **[!UICONTROL Estado computado da camada de dados]**.
1. Em **[!UICONTROL Valor de retorno]**, selecione **[!UICONTROL Caminho específico]** e insira o caminho para o valor na camada de dados, como `page.name`. Para validar um caminho, execute `adobeDataLayer.getState("page.name")` no console do navegador.
1. Selecione **[!UICONTROL Salvar]**.

Use esses elementos de dados em regras que o evento de push da camada de dados **[!UICONTROL da extensão aciona, para que a camada de dados tenha carregado e contenha os dados do push.]** Consulte [Tipos de elementos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state).

### Camadas de dados baseadas em objetos {#object-based}

Se sua camada de dados for um objeto JavaScript, como um objeto CEDDL `digitalData`, use o tipo de elemento de dados **[!UICONTROL Variável JavaScript]** da extensão **[!UICONTROL Core]**. Digite o caminho para o valor, como `digitalData.page.pageInfo.pageName`. Esse tipo de elemento de dados não pode ler a Camada de dados de clientes Adobe, que armazena seus dados em um estado calculado em vez de em propriedades de objeto.

## Próximas etapas

[Mapear elementos de dados para variáveis do Analytics](elements-to-variable.md): atribua elementos de dados às variáveis do Analytics para que você possa usá-los como dimensões no Analysis Workspace.
