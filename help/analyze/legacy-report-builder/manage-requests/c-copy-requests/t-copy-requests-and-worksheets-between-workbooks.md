---
description: Saiba como copiar uma planilha de uma pasta de trabalho de origem para uma ou mais pastas de trabalho de destino.
title: Como copiar solicitações e planilhas entre pastas de trabalho
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 54%

---

# Copiar solicitações e planilhas entre pastas de trabalho

{{legacy-arb}}

Copie uma planilha inteira em uma pasta de trabalho de origem em uma planilha em uma ou mais pastas de trabalho de destino. Para fazer isso, você deve ter pelo menos duas pastas de trabalho abertas na mesma instância do Excel:

* A primeira pasta de trabalho de origem contém uma planilha (planilha) com solicitações mapeadas a células.

* As pastas de trabalho de destino adicionais são os destinos. Para cada nova pasta de trabalho de destino, você deve fazer logon no mesmo conjunto de relatórios que a pasta de trabalho de origem antes de poder colar planilhas contendo solicitações.

>[!NOTE]
>
>Você deve fazer logon na pasta de trabalho de destino usando o mesmo conjunto de relatórios que a pasta de trabalho de origem. As solicitações em ambas as pastas de trabalho precisam ser criadas com o mesmo logon do conjunto de relatórios.

1. Clique com o botão direito do mouse na planilha na pasta de trabalho de origem e selecione **[!UICONTROL Copiar planilha com solicitações]**.
1. Na pasta de trabalho de destino, clique com o botão direito do mouse na planilha e selecione **[!UICONTROL Colar planilha com solicitações]**.

   A mesma instância do Excel significa que apenas um único processo do Excel ([!DNL excel.exe]) está em execução no computador de cada vez. Se você iniciar duas instâncias do Excel e tentar copiar uma planilha de uma pasta de trabalho na primeira instância do Excel para uma pasta de trabalho na segunda instância do Excel, o Report Builder não apresentará a opção de colar uma planilha no menu de atalho da segunda instância do Excel.

   Se você fizer logon nas pastas de trabalho de origem e de destino usando diferentes conjuntos de relatórios, os únicos resultados que você verá da operação de colagem serão os que afetam a formatação da pasta de trabalho de destino. O Report Builder exibe uma mensagem declarando que as informações para as solicitações derivadas de um conjunto de relatórios especificado (na pasta de trabalho de origem) não estão disponíveis na pasta de trabalho de destino. Para revelar as solicitações coladas na pasta de trabalho de destino, você precisa fazer logon na pasta de trabalho de destino usando o mesmo conjunto de relatórios que a pasta de trabalho de origem.

   Você pode copiar e colar uma ou mais solicitações de uma planilha em uma pasta de trabalho para uma planilha em outra pasta de trabalho, desde que a segunda pasta esteja aberta como outro documento na mesma instância do Excel. As solicitações em ambas as pastas de trabalho precisam ser criadas com o mesmo logon do conjunto de relatórios.
