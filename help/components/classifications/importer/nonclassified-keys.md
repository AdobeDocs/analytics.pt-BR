---
description: Teclas não classificadas são agrupadas nos relatórios de classificação como um único item de linha identificado como Nenhum. Pode ser útil para renomear Nenhum para algo mais descritivo.
subtopic: Classifications
title: Chaves não classificadas
feature: Ferramentas administrativas
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
translation-type: tm+mt
source-git-commit: f52baf97efe20b209f51108995a0620b6c19bec0
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 66%

---

# Chaves não classificadas

Teclas não classificadas são agrupadas nos relatórios de classificação como um único item de linha identificado como Nenhum. Pode ser útil para renomear Nenhum para algo mais descritivo.

## Chaves não classificadas {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Teclas não classificadas são agrupadas nos relatórios de classificação como um único item de linha rotulado *`None`*. Pode ser útil para renomear *`None`* para algo mais descritivo.

Por exemplo, suponha que seus códigos de rastreamento contenham informações que definam o tipo de campanha móvel à qual o código de rastreamento está associado. Você está usando a classificação (Tipo de campanha móvel) para reunir esses códigos de rastreamento em categorias, como Web móvel, aplicativo iOS, aplicativo Android e assim por diante. Algumas campanhas talvez não sejam campanhas móveis, não sendo classificadas com um tipo de campanha móvel. Todos os códigos de rastreamento não classificados seriam reunidos em *`None`* no relatório de [!UICONTROL Tipo de campanha móvel].

## Renomear a tecla de classificação Nenhum {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Etapas que descrevem como renomear uma tecla não classificada que é exibida como *`none`* em relatórios.

1. Utilizando o importador, exporte classificações para um arquivo local.
1. Adicione uma linha ao arquivo e digite `~none~` na coluna Tecla.
1. Na linha adicionada, digite o mais nome descritivo na devida coluna de classificação.

   Para seguir o exemplo deste documento, você pode digitar &quot;campanha não móvel&quot; em uma coluna chamada [!UICONTROL Tipo de campanha móvel].

   Essa entrada é renomeada de *`None`* para *`non-mobile campaign`* no relatório [!UICONTROL Tipo de campanha móvel].

   ![Exemplo de uma chave não classificada](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Importar os dados](/help/components/classifications/importer/import-file.md) de volta para o sistema.
