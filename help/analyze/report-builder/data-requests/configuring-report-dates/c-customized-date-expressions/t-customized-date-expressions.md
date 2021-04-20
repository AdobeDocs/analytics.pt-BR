---
description: Você pode construir uma expressão personalizada para especificar um intervalo complexo de datas.
title: Visão geral das Expressões de datas personalizadas
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 30%

---


# Visão geral das Expressões de datas personalizadas

Você pode construir uma expressão personalizada para especificar um intervalo complexo de datas.

Recomendamos consultar um calendário ao criar expressões, para especificar o número de semanas e dias corretamente. O Excel tem várias funções incorporadas que permitem calcular o número de dias, dias úteis, meses e anos entre as datas. Você pode usar essas funções em fórmulas para calcular outros intervalos, como semanas e trimestres.

**Para habilitar expressões personalizadas**

Este é um exemplo de uso de **[!UICONTROL Datas do acumulado]**.

1. No [!UICONTROL Assistente de solicitações: Etapa 1], em vez de usar **[!UICONTROL Datas predefinidas]**, selecione **[!UICONTROL Datas do acumulado]**.

   ![](assets/rolldates1.png)

1. Alterne para semanal, mensal, trimestral ou anual contínuo. Observe como as opções abaixo mudam.
1. Para obter mais opções de personalização, clique em **[!UICONTROL Mostrar opções avançadas]**.

   ![](assets/rolldates2.png)

1. Por exemplo, se você alterar as datas acima para acumulado mensalmente do primeiro dia três meses atrás para o primeiro dia deste mês, as datas na porção de opções avançadas se atualizarão para refletir que:

   ![](assets/rolldatesfor3.png)

1. Habilite **[!UICONTROL Personalizar expressão]**. Ao selecionar opções em **[!UICONTROL Datas do acumulado]**, é possível ver facilmente a sintaxe das expressões de data personalizadas.

   ![](assets/rolldatesfor5.png)

   Você pode usar as Opções avançadas para combinar expressões de datas personalizadas. Por exemplo, se você quiser ver dados do primeiro ano até o final do último mês completo, poderá inserir o seguinte: `From: cy` `To: cm-1d`. No assistente, essas datas são mostradas como 1/1/2020-1/31/2020.
