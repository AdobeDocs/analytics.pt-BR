---
description: Etapas que podem descrever como evitar os dados de classificação no arquivo de classificação.
subtopic: Classifications
title: Evitar os dados de classificação
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 100%

---


# Evitar os dados de classificação

Etapas que podem descrever como evitar os dados de classificação no arquivo de classificação.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Garanta que o formato do arquivo de classificação seja da versão 2.1.

   Se a versão 2.1 estiver habilitada, você verá uma linha parecida com:

   >[!NOTE]
   >
   >Para especificar o formato para a versão 2.1, habilite o **[!UICONTROL Quoted Output]** ao exportar o arquivo na página do [!UICONTROL Importador de classificação] ([!UICONTROL Exportar navegador] ou [!UICONTROL Exportar FTP]).

1. Marque o campo que contém caracteres especiais entre aspas (`"`).

Um caractere entre aspas pode aparecer em uma célula escaped ao substituí-la ou dois caracteres entre aspas (`" "`). Por exemplo:

```
My String "of data"
```

Escaped seria:

```
"My String ""of data"""
```
