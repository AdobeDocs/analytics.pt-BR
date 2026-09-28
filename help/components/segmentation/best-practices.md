---
title: Práticas recomendadas
description: Conheça algumas práticas recomendadas de segmentação.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
TQID: 'https://experienceleague.adobe.com/PJi-kkv6HL3jHEKArltzxMGk9BVtZ-Mr1ivHMkhxt88'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c47a19a5-f47b-4e53-afe0-e230da195ebe
    internal-label: Segmentation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 60%
---
# Práticas recomendadas de segmentação

Segmentos complexos geralmente são necessários para obter os dados desejados. Se os segmentos complexos forem ineficientes e usados em um conjunto de relatórios grande, a execução dos relatórios levará consideravelmente mais tempo. Considere os seguintes recursos ao criar ou editar um segmento para minimizar a complexidade.

## Usar somente o operador `Contains` como último recurso

O operador [**[!UICONTROL Contém ]**](/help/components/segmentation/seg-reference/seg-operators.md) é um dos recursos de processamento mais intensos na segmentação, pois o operador precisa analisar todo o conteúdo de cada valor. Considere o uso de outros operadores, como**[!UICONTROL  Começa com ]**ou**[!UICONTROL  Termina com ]**, se os valores desejados estiverem no início ou no fim de uma cadeia de caracteres.

Se um operador **[!UICONTROL Contém]** em um segmento retornar um grande número de resultados, o tempo limite do relatório normalmente é excedido. Por exemplo, se você criou um segmento em que **[!UICONTROL Referenciador]** **[!UICONTROL é igual a]** `"."`, o segmento pesquisa o conteúdo de cada valor. Considere usar o operador **[!UICONTROL Existe]**.

## Usar classificações para agrupar itens de dimensão

Se você tiver muitas condições de segmento, elas podem degradar rapidamente o desempenho do segmento. Por exemplo, **[!UICONTROL Página]** **[!UICONTROL é igual a]** `X` **[!UICONTROL OU]** **[!UICONTROL Página]** **[!UICONTROL é igual a]** `Y` **[!UICONTROL OU]** **[!UICONTROL Página]** **[!UICONTROL é igual a]** `Z` repetido com centenas de valores diferentes. Em vez de anotar essas centenas de condições, classifique todos os valores desejados em um segmento e use o valor classificado em um segmento.

1. Crie uma classificação para a variável com a qual você está trabalhando.
2. Baixe o modelo de classificação e abra-o no editor de planilha ou texto desejado.
3. Atribua o mesmo valor a cada item de dimensão que você gostaria de incluir no seu segmento.
4. Use o importador de classificação para importar a planilha de volta para o Adobe Analytics
5. Quando a classificação terminar de processar, crie um segmento usando o valor classificado.

Esse método aumenta bastante o desempenho e fornece uma maneira fácil de modificar as condições do segmento. Em vez de editar o segmento com valores diferentes, você pode adicionar ou remover itens de dimensão da classificação.
