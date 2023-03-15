---
description: Você pode construir uma expressão personalizada para especificar um intervalo complexo de datas.
title: Visão geral das Expressões de datas personalizadas
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 29%

---

# Visão geral das Expressões de datas personalizadas

Você pode construir uma expressão personalizada para especificar um intervalo complexo de datas.

Recomendamos que você consulte um calendário ao criar expressões para especificar o número de semanas e dias corretamente. O Excel tem várias funções incorporadas que permitem calcular o número de dias, dias úteis, meses e anos entre as datas. Você pode usar essas funções em fórmulas para calcular outros intervalos, como semanas e trimestres.

**Para habilitar expressões personalizadas**

Este é um exemplo de uso de **[!UICONTROL Datas do acumulado]**.

1. No [!UICONTROL Assistente de solicitações: etapa 1], em vez de usar **[!UICONTROL Datas predefinidas]**, selecione **[!UICONTROL Datas do acumulado]**.

   ![](assets/rolldates1.png)

1. Alterne para Em andamento semanal, mensal, trimestral ou anual. Observe como as opções abaixo são alteradas.
1. Para obter mais opções de personalização, clique em **[!UICONTROL Mostrar opções avançadas]**.

   ![](assets/rolldates2.png)

1. Por exemplo, se você alterar as datas acima para mensal acumulada do primeiro dia três meses atrás para o primeiro dia deste mês, as datas na parte de opções avançadas serão atualizadas para refletir isso:

   ![](assets/rolldatesfor3.png)

1. Ativar **[!UICONTROL Personalizar expressão]**. Ao selecionar opções em **[!UICONTROL Datas do acumulado]**, você pode ver facilmente a sintaxe das expressões de data personalizadas.

   ![](assets/rolldatesfor5.png)

   Você pode usar Opções avançadas para misturar e corresponder expressões de data personalizadas. Por exemplo, se você quiser ver os dados do primeiro dia do ano até o final do último mês completo, poderá inserir o seguinte: `From: cy` `To: cm-1d`. No assistente, essas datas são mostradas como 1/1/2020-1/31/2020.
