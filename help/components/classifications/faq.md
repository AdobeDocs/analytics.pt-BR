---
title: Perguntas frequentes sobre classificações
description: Perguntas frequentes sobre o uso de classificações.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '344'
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

## Posso usar o importador de classificação para classificar itens de dimensão que ainda não existem?

Sim, *entretanto, isso conta cada item de dimensão como uma chamada de servidor faturável.*

* Os itens de Dimension que já existem não incorrem em nenhum custo extra.
* O uso do construtor de regras de classificação não classifica itens inexistentes e, portanto, não implica nenhum custo extra.

## Como posso classificar valores que contêm caracteres especiais?

Geralmente, não é recomendado usar caracteres especiais, como vírgulas ou aspas de duplo no relatórios. No entanto, em alguns casos, a sua utilização é necessária. Se os valores do relatórios contiverem os caracteres que você escolher classificar, use as seguintes etapas:

1. Faça logon no Adobe Analytics e navegue até **[!UICONTROL Admin]** > Importador **** de classificação.
2. Click the **[!UICONTROL Browser export]** tab.
3. Defina as configurações de exportação e certifique-se de que &#39;Saída de cotação&#39; NÃO esteja selecionado.
4. Clique em **[!UICONTROL Exportar arquivo]** e abra o arquivo baixado em um editor de planilhas.
5. Na linha 1, localize a célula C1, que contém o valor `v:2.0`. Altere o valor para `v:2.1` e aplique as classificações desejadas à pasta de trabalho.
6. Carregue o arquivo como faria com qualquer outra classificação.

## O que são classificações numéricas 2?

As classificações numéricas 2 permitem classificar itens de dimensão como métricas baseadas em tempo. Eles foram removidos da interface do usuário do Analytics em julho de 2019.
