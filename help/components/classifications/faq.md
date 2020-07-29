---
title: Perguntas frequentes sobre classificações
description: Perguntas frequentes sobre o uso de classificações.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Perguntas frequentes sobre classificações

Perguntas frequentes sobre o uso de classificações.

## Como posso classificar o item de dimensão &quot;0&quot;?

Os arquivos de classificação carregados com um valor chave ou um valor de classificação igual a zero (`0`) resultam em um erro. Inclui todos os valores que contêm apenas zeros (`00`, `000`etc.). Há vários métodos para resolver esse problema:

* **Implementar valores** alternativos: Usar um valor de texto diferente do `"0"` é a melhor e mais fácil maneira de resolver esse problema. Por exemplo, altere `s.campaign = "0";` a implementação para `s.campaign = "Zero";`.

* **Usar regras** de processamento: Você pode modificar itens de dimensão entre a coleta de dados e seus armazenamentos em um conjunto de relatórios. Crie a seguinte regra de processamento:

   *Se a[dimensão]for igual`0`, substitua o valor da[dimensão]pelo valor personalizado`Zero`.*

* **Solicite uma regra** VISTA: Um consultor dos Serviços de engenharia configura uma regra do lado do servidor para você com um custo extra. Entre em contato com o Gerente de conta de sua organização para solicitar uma regra VISTA.

## Posso usar o carregador para classificar itens de dimensão que ainda não existem?

Sim, *entretanto, isso conta cada item de dimensão como uma chamada de servidor faturável.*

* Os itens de Dimension que já existem não incorrem em nenhum custo extra.
* O uso do construtor de regras de classificação não classifica itens inexistentes e, portanto, não implica nenhum custo extra.
