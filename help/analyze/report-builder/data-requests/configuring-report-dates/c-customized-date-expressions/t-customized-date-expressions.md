---
description: Você pode construir uma expressão personalizada para especificar um intervalo complexo de datas.
title: Visão geral das Expressões de datas personalizadas
topic: Report builder
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
translation-type: tm+mt
source-git-commit: 9e1fdd7785b7323e4f667eab58a1f107272493f0

---


# Visão geral das Expressões de datas personalizadas

Você pode construir uma expressão personalizada para especificar um intervalo complexo de datas.

Recomenda-se consultar um calendário ao criar expressões, para que o número de semanas e dias seja especificado corretamente. O Excel tem várias funções incorporadas que permitem calcular o número de dias, dias úteis, meses e anos entre as datas. Você pode usar essas funções em fórmulas para calcular outros intervalos, como semanas e trimestres.

**Para habilitar expressões personalizadas**

1. Na página [!UICONTROL Request Wizard: Step 1], em vez de usar &quot;Datas predefinidas&quot;, selecione **[!UICONTROL Rolling Dates]**. Observe como as opções abaixo mudam.

   ![](assets/rolldates1.png)

1. Alternar para semanal, mensal, trimestral ou anual.
1. Para obter mais opções de personalização, clique em **[!UICONTROL Show Advanced Options]**. Ao selecionar opções na seção superior, você pode ver facilmente a sintaxe para expressões de datas personalizadas.

   ![](assets/rolldates2.png)

1. Ativar **[!UICONTROL Customize Expression]**. Ao selecionar as opções em **[!UICONTROL Rolling Dates]**, você pode ver facilmente a sintaxe das expressões de data personalizadas.

   ![](assets/rolldates5.png)

   Você pode usar Opções avançadas para combinar e combinar expressões de datas personalizadas. Por exemplo, se você quiser ver dados do primeiro ano até o final do último mês completo, eles poderão escrever o seguinte:De: cy To: cm-1d. Você pode ver que no assistente, ele confirma essas datas como sendo 1/1/2020-1/31/2020.

   Por exemplo, se você alterar as datas acima para rolar mensalmente do primeiro dia três meses atrás para o primeiro dia deste mês, as datas na parte de opções avançadas se atualizarão para refletir isso:

   ![](assets/rolldates3.png)

