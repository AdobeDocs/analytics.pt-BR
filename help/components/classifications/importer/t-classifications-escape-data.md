---
description: Etapas que podem descrever como evitar os dados de classificação no arquivo de classificação.
title: Evitar os dados de classificação
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
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
