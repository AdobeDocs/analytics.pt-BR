---
description: Saiba como copiar uma planilha de uma pasta de trabalho de origem para uma ou mais pastas de trabalho de destino.
title: Como copiar solicitações e planilhas entre pastas de trabalho
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
TQID: https://experienceleague.adobe.com/0GVqb80fMIVJlip2dWGgzllmCGG2Hc8368WZlThzzh0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 379
ht-degree: 21%

---

# Copiar solicitações e planilhas entre pastas de trabalho

{{legacy-arb}}

Copie uma planilha inteira em uma pasta de trabalho de origem em uma planilha em uma ou mais pastas de trabalho de destino. Para fazer isso, você deve ter pelo menos duas pastas de trabalho abertas na mesma instância do Excel:

* A primeira pasta de trabalho de origem contém uma planilha (planilha) com solicitações mapeadas a células.

* As pastas de trabalho de destino adicionais são os destinos. Para cada nova pasta de trabalho de destino, você deve fazer logon no mesmo conjunto de relatórios que a pasta de trabalho de origem antes de poder colar planilhas contendo solicitações.

>[!NOTE]
>
>Você deve fazer logon na pasta de trabalho de destino usando o mesmo conjunto de relatórios que a pasta de trabalho de origem. As solicitações em ambas as pastas de trabalho devem ser criadas usando o mesmo logon de conjunto de relatórios.

1. Clique com o botão direito do mouse na planilha na pasta de trabalho de origem e selecione **[!UICONTROL Copiar planilha com solicitações]**.
1. Na pasta de trabalho de destino, clique com o botão direito do mouse na planilha e selecione **[!UICONTROL Colar planilha com solicitações]**.

   A mesma instância do Excel significa que apenas um único processo do Excel ([!DNL excel.exe]) está em execução no computador de cada vez. Se você iniciar duas instâncias do Excel e tentar copiar uma planilha de uma pasta de trabalho na primeira instância do Excel para uma pasta de trabalho na segunda instância do Excel, o Report Builder não apresentará a opção de colar uma planilha no menu de atalho da segunda instância do Excel.

   Se você fizer logon nas pastas de trabalho de origem e de destino usando conjuntos de relatórios diferentes, os únicos resultados vistos da operação de colagem serão aqueles que afetam a formatação da pasta de trabalho de destino. O Report Builder exibe uma mensagem declarando que as informações para as solicitações derivadas de um conjunto de relatórios especificado (na pasta de trabalho de origem) não estão disponíveis na pasta de trabalho de destino. Para revelar as solicitações coladas na pasta de trabalho de destino, você deve fazer logon na pasta de trabalho de destino usando o mesmo conjunto de relatórios que a pasta de trabalho de origem.

   Você pode copiar e colar uma ou mais solicitações de uma planilha em uma pasta de trabalho para uma planilha em outra pasta de trabalho, desde que a segunda pasta de trabalho esteja aberta como outro documento na mesma instância do Excel. As solicitações em ambas as pastas de trabalho devem ser criadas usando o mesmo logon de conjunto de relatórios.
