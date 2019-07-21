---
description: Copie uma planilha inteira em uma pasta de trabalho de origem em uma planilha em uma ou mais pastas de trabalho de destino.
seo-description: Copie uma planilha inteira em uma pasta de trabalho de origem em uma planilha em uma ou mais pastas de trabalho de destino.
seo-title: Copiar solicitações e planilhas entre pastas de trabalho
solution: Analytics
title: Copiar solicitações e planilhas entre pastas de trabalho
topic: Construtor de relatórios
uuid: 6 b 2 c 4259-d 8 cb -430 e -819 f -38 e 213 dd 2661
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copiar solicitações e planilhas entre pastas de trabalho

Copie uma planilha inteira em uma pasta de trabalho de origem em uma planilha em uma ou mais pastas de trabalho de destino.

Para fazê-lo, você deve ter ao menos duas pastas de trabalho abertas na mesma instância do Excel: a primeira pasta de trabalho de origem contém uma planilha com solicitações mapeadas a células, enquanto as pastas de trabalho de destino adicionais são os destinos. Para cada nova pasta de trabalho de destino, você deve  fazer logon no mesmo conjunto de relatórios como a pasta de trabalho de origem antes de poder colar planilhas contendo solicitações.
1. Clique com o botão direito do mouse na planilha na pasta de trabalho de origem e selecione **[!UICONTROL Copiar planilha com solicitações]**.
1. Na pasta de trabalho de destino, clique com o botão direito do mouse na planilha e selecione **[!UICONTROL Colar planilha com solicitações]**.

   A mesma instância do Excel significa que apenas um único processo do Excel ([!DNL excel.exe]) está em execução no computador de cada vez. Se você iniciar duas instâncias do Excel e tentar copiar uma planilha de uma pasta de trabalho na primeira instância do Excel para uma pasta de trabalho na segunda instância do Excel, o construtor de relatórios não apresentará a opção de colar a planilha no menu de atalho da segunda instância do Excel.

   Se você fizer logon nas pastas de trabalho de origem e de destino usando diferentes conjuntos de relatórios, os únicos resultados que você verá da operação de colagem serão os que afetam a formatação da pasta de trabalho de destino. O Construtor de relatórios exibe uma mensagem declarando que as informações para as solicitações derivadas de um conjunto de relatórios especificado (na pasta de trabalho de origem) não estão disponíveis na pasta de trabalho de destino. Para revelar as solicitações coladas na pasta de trabalho de destino, você precisa fazer logon na pasta de trabalho de destino usando o mesmo conjunto de relatórios que a pasta de trabalho de origem.

   Você pode copiar e colar uma ou mais solicitações de uma planilha em uma pasta de trabalho para uma planilha em outra pasta de trabalho, desde que a segunda pasta esteja aberta como outro documento na mesma instância do Excel. As solicitações em ambas as pastas de trabalho precisam ser criadas com o mesmo logon do conjunto de relatórios.
