---
title: Verificação do conjunto de relatórios no assistente de atualização do Web SDK
description: Revise as variáveis do Analytics em seus conjuntos de relatórios e escolha quais serão transportadas para o mapeamento XDM.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%
---
# Verificação do conjunto de relatórios

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification"
>title="Verificação do conjunto de relatórios"
>abstract="Revise as variáveis do Analytics que a propriedade de tags envia para cada conjunto de relatórios. As variáveis selecionadas aqui são transportadas para o mapeamento XDM. Use as guias para verificar dados recentes, localizar variáveis duplicadas e comparar configurações em conjuntos de relatórios."

<!-- markdownlint-enable MD034 -->

O assistente de atualização identifica os conjuntos de relatórios para os quais a propriedade de tags envia dados e compara as variáveis do Analytics na implementação com a configuração de cada conjunto de relatórios e com os dados recentes. Use esta etapa para decidir quais variáveis são transportadas para o [mapeamento XDM](xdm-mapping.md).

O assistente de atualização usa seus conjuntos de relatórios para entender quais variáveis seus conjuntos de implementação e como eles são configurados. Os dados da atividade abrangem os últimos 90 dias.

## Atividade variável {#variable-activity}

A guia **[!UICONTROL Atividade de variável]** lista as variáveis do Analytics para o conjunto de relatórios que você escolheu mapear em [Análise de variáveis](#variable-analysis) e mostra se cada uma coletou dados nos últimos 90 dias.

As variáveis selecionadas são transportadas para o mapeamento XDM. Considere limpar as variáveis que não coletam mais dados ou que não são necessárias na implementação do Web SDK. Uma variável sem atividade recente ainda pode estar em uso, por exemplo, se for sazonal ou tiver tráfego baixo, portanto, confirme se você não precisa dela antes de limpá-la.

Para cada variável de lista e prop de lista que você transporta, insira o delimitador que separa seus valores. O assistente de atualização não pode obter delimitadores do Adobe Analytics e você não pode continuar até que cada um tenha um delimitador.

## Análise de variáveis {#variable-analysis}

Se a propriedade das tags enviar dados para mais de um conjunto de relatórios, primeiro escolha o conjunto de relatórios a ser mapeado. A guia **[!UICONTROL Análise de variáveis]** sinaliza as variáveis que podem precisar de uma decisão antes de você mapeá-las:

* Variáveis que parecem coletar os mesmos dados. Confirme se eles capturam as mesmas informações e decida se desejam mesclá-las em uma única variável ou mantê-las separadas.
* Variáveis que não coletaram dados recentemente.
* Variáveis cujos valores são todos &quot;Não especificado&quot;.

## Comparar conjuntos de relatórios {#compare}

Se a propriedade das tags enviar dados para mais de um conjunto de relatórios, a guia **[!UICONTROL Comparar conjuntos de relatórios]** comparará as configurações de cada variável em até três desses conjuntos de relatórios. Use-a para localizar variáveis configuradas de forma diferente entre conjuntos de relatórios antes de mapeá-las para um esquema.

## Atualizar dados do conjunto de relatórios {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification_refresh"
>title="Atualizar dados do conjunto de relatórios"
>abstract="Verifica novamente os conjuntos de relatórios vinculados a essa propriedade de tags, incluindo suas configurações de variável e dados recentes, e executa novamente a análise de variável. Se o assistente de atualização ainda não encontrou conjuntos de relatórios, ele os procurará na propriedade de tags primeiro. Suas seleções e decisões são mantidas."

<!-- markdownlint-enable MD034 -->

Você pode alterar quais conjuntos de relatórios o assistente de atualização analisa durante esta etapa. Se a configuração do conjunto de relatórios for alterada enquanto a migração estiver em andamento, selecione **[!UICONTROL Atualizar dados do conjunto de relatórios]** para executar a análise novamente. O assistente de atualização mantém as seleções e decisões existentes.

Quando terminar, selecione **[!UICONTROL Salvar e continuar]** para ir para o [mapeamento XDM](xdm-mapping.md).
