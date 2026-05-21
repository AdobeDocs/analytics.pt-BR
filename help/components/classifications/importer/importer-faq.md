---
title: Perguntas frequentes sobre classificações
description: Perguntas frequentes sobre o uso de classificações.
feature: Classifications
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
TQID: https://experienceleague.adobe.com/pIwAdewnHA4AB9hyRDRkH6xXvyxx-BceWvDXMydX-ew
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 86%

---

# Perguntas frequentes do importador de classificação

{{classification-importer-deprecation}}

Perguntas frequentes sobre o uso do importador de classificação.

## Como posso classificar o item de dimensão “0”?

Os arquivos de classificação carregados com um valor chave ou um valor de classificação igual a zero (`0`) resultam em um erro. Inclui todos os valores que contêm apenas zeros (`00`, `000`etc.). Há vários métodos para resolver esse problema:

* **Implementar valores alternativos**: usar um valor de texto diferente de `"0"` é a melhor maneira e a mais fácil de resolver esse problema. Por exemplo, altere `s.campaign = "0";` na implementação para `s.campaign = "Zero";`.

* **Usar regras de processamento**: você pode modificar itens de dimensão entre a coleta de dados e seus armazenamentos em um conjunto de relatórios. Crie a seguinte regra de processamento:

  *Se a [dimensão] for igual a `0`, substitua o valor da [dimensão] pelo valor personalizado `Zero`.*

* **Solicitar uma regra VISTA**: um consultor dos Serviços de engenharia configura uma regra do lado do servidor para você com um custo extra. Entre em contato com a equipe de contas da Adobe para solicitar uma regra VISTA.

## Posso usar o importador de classificação para classificar itens de dimensão que ainda não existem?

Sim, *entretanto, cada item de dimensão será contado como uma chamada de servidor faturável.*

* Os itens de dimensão que já existem não incorrem em nenhum custo extra.
* O uso do construtor de regras de classificação não classifica itens inexistentes e, portanto, não implica nenhum custo extra.

## Como posso classificar valores que contêm caracteres especiais?

Não há suporte para o uso de espaços em branco à esquerda e à direita nos dados de classificação e de ocorrência, pois o Adobe Analytics trunca automaticamente caracteres em branco.

Geralmente, não é recomendado usar caracteres especiais nos relatórios, como vírgulas ou aspas duplas. No entanto, em alguns casos, a sua utilização é necessária. Se os valores dos relatórios tiverem tais caracteres que você optar por classificar, siga estas etapas:

1. Faça logon no Adobe Analytics e acesse **[!UICONTROL Admin]** > **[!UICONTROL Importador de classificação]**.
2. Clique na guia **[!UICONTROL Exportação de navegador]**.
3. Defina as configurações de exportação e verifique se a opção “Saída de cotação” NÃO está selecionada.
4. Clique em **[!UICONTROL Exportar arquivo]** e abra o arquivo baixado em um editor de planilhas.
5. Na linha 1, localize a célula C1, que contém o valor `v:2.0`. Altere o valor para `v:2.1` e aplique as classificações desejadas à pasta de trabalho.
6. Carregue o arquivo como faria com qualquer outra classificação.

## O que são classificações numéricas 2?

As classificações numéricas 2 permitem classificar itens de dimensão como métricas que se baseiam em tempo. Eles foram removidos da interface do Adobe Analytics em julho de 2019.

## Como posso evitar dados em um arquivo de classificação?

Marque o campo que contém caracteres especiais entre aspas (`"`). Um caractere entre aspas pode aparecer em uma célula escaped ao substituí-la ou dois caracteres entre aspas (`" "`). Por exemplo:

```
My String "of data"
```

Escapado seria:

```
"My String ""of data"""
```
