---
title: Perguntas frequentes sobre classificações
description: Perguntas frequentes sobre o uso de classificações.
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
translation-type: tm+mt
source-git-commit: ecef181e0d2ab06c68a5af2b50f14f4c7dd7c285
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 92%

---

# Perguntas frequentes sobre classificações

Perguntas frequentes sobre o uso de classificações.

## Como posso classificar o item de dimensão “0”?

Os arquivos de classificação carregados com um valor chave ou um valor de classificação igual a zero (`0`) resultam em um erro. Inclui todos os valores que contêm apenas zeros (`00`, `000`etc.). Há vários métodos para resolver esse problema:

* **Implementar valores alternativos**: usar um valor de texto diferente de `"0"` é a melhor maneira e a mais fácil de resolver esse problema. Por exemplo, altere `s.campaign = "0";` na implementação para `s.campaign = "Zero";`.

* **Usar regras de processamento**: você pode modificar itens de dimensão entre a coleta de dados e seus armazenamentos em um conjunto de relatórios. Crie a seguinte regra de processamento:

   *Se a [dimensão] for igual a `0`, substitua o valor da [dimensão] pelo valor personalizado `Zero`.*

* **Solicitar uma regra VISTA**: um consultor dos Serviços de engenharia configura uma regra do lado do servidor para você com um custo extra. Entre em contato com o Gerente de conta de sua organização para solicitar uma regra VISTA.

## Posso usar o importador de classificação para classificar itens de dimensão que ainda não existem?

Sim, *entretanto, cada item de dimensão será contado como uma chamada de servidor faturável.*

* Os itens de dimensão que já existem não incorrem em nenhum custo extra.
* O uso do construtor de regras de classificação não classifica itens inexistentes e, portanto, não implica nenhum custo extra.

## Como posso classificar valores que contêm caracteres especiais?

Não há suporte para o uso de espaços em branco à esquerda e à direita nos dados de classificação e de ocorrência, pois o Adobe Analytics truncará os caracteres em branco desses dados.

Geralmente, não é recomendado usar caracteres especiais nos relatórios, como vírgulas ou aspas duplas. No entanto, em alguns casos, a sua utilização é necessária. Se os valores dos relatórios tiverem tais caracteres que você optar por classificar, siga estas etapas:

1. Faça logon no Adobe Analytics e acesse **[!UICONTROL Admin]** > **[!UICONTROL Importador de classificação]**.
2. Clique na guia **[!UICONTROL Exportação de navegador]**.
3. Defina as configurações de exportação e verifique se a opção “Saída de cotação” NÃO está selecionada.
4. Clique em **[!UICONTROL Exportar arquivo]** e abra o arquivo baixado em um editor de planilhas.
5. Na linha 1, localize a célula C1, que contém o valor `v:2.0`. Altere o valor para `v:2.1` e aplique as classificações desejadas à pasta de trabalho.
6. Carregue o arquivo como faria com qualquer outra classificação.

## O que são classificações numéricas 2?

As classificações numéricas 2 permitem classificar itens de dimensão como métricas que se baseiam em tempo. Eles foram removidos da interface do Adobe Analytics em julho de 2019.
