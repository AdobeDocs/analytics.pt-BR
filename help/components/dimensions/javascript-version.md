---
title: Versão do JavaScript
description: A versão do JavaScript compatível com o navegador do visitante.
feature: Dimensions
source-git-commit: a68e13c9232ef8d975fd1256168a0addf677f5ac
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 10%
---
# Versão do JavaScript

A &quot;versão do JavaScript&quot; [dimensão](overview.md) informa a versão do JavaScript com suporte pelo navegador do visitante. Ela não relata a versão da biblioteca do AppMeasurement.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse. Se você quiser usar a versão do JavaScript em outras soluções do Analytics, considere copiar o valor em uma [eVar](evar.md) em cada ocorrência.

## Preencher esta dimensão com dados

O AppMeasurement detecta automaticamente os recursos do JavaScript no navegador e envia um valor de versão no parâmetro de cadeia de caracteres de consulta `j`. Não há variável de implementação a ser definida. Essa detecção usa rótulos de versão herdados do JavaScript; não é uma medida abrangente do suporte a recursos modernos do ECMAScript.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (coletado automaticamente) |
| **Web SDK / campo XDM** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **Parâmetro de consulta** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Coluna da API de Inserção de Dados em Massa** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **Limite de bytes** | 5 bytes |
| **Persistência** | Hit |

## Itens de dimensão

Os itens do Dimension incluem os valores de versão do JavaScript coletados dos navegadores dos visitantes, como `1.5` e `1.6`.
