---
description: Etapas que podem descrever como evitar os dados de classificação no arquivo de classificação.
seo-description: Etapas que podem descrever como evitar os dados de classificação no arquivo de classificação.
seo-title: Evitar os dados de classificação
solution: Analytics
subtopic: Classificações
title: Evitar os dados de classificação
topic: Ferramentas administrativas
uuid: 724 edcc 5-4990-4 f 24-afbb -9 aef 301791 a 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Evitar os dados de classificação

Etapas que podem descrever como evitar os dados de classificação no arquivo de classificação.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Garanta que o formato do arquivo de classificação seja da versão 2.1.

   Se a versão 2.1 estiver habilitada, você verá uma linha parecida com:

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Marque o campo que contém caracteres especiais entre aspas (`"`).

Um caractere entre aspas pode aparecer em uma célula escaped ao substituí-la ou dois caracteres entre aspas (`" "`). Por exemplo:

```
My String "of data"
```

Escaped seria:

```
"My String ""of data"""
```
