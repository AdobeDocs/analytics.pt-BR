---
description: As teclas não classificadas são reunidas nos relatórios de classificação como um único item de linha identificado como Nenhum. Pode ser útil para renomear Nenhum para algo mais descritivo.
seo-description: As teclas não classificadas são reunidas nos relatórios de classificação como um único item de linha identificado como Nenhum. Pode ser útil para renomear Nenhum para algo mais descritivo.
seo-title: Teclas não classificadas
solution: Analytics
subtopic: Classificações
title: Teclas não classificadas
topic: Ferramentas administrativas
uuid: b 73 a 9161-0 c 6 f -4 c 8 d -900 b -54 ab 2 c 36147 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Teclas não classificadas

As teclas não classificadas são reunidas nos relatórios de classificação como um único item de linha identificado como Nenhum. Pode ser útil para renomear Nenhum para algo mais descritivo.

## Non-classified keys {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Teclas não classificadas são reunidas nos relatórios de classificação como um único item de linha identificado *`None`*. It can be useful to rename *`None`* to something more descriptive.

Por exemplo, digamos que seus códigos de rastreamento possuam informações que definam o tipo de campanha móvel à qual o código de rastreamento está associado. Você está usando a classificação (Tipo de campanha móvel) para reunir esses códigos de rastreamento em categorias, como Web móvel, aplicativo iOS, aplicativo Android e assim por diante. Algumas campanhas talvez não sejam campanhas móveis, não sendo classificadas com um tipo de campanha móvel. Todos os códigos de rastreamento não classificados seriam reunidos em *`None`* no relatório de [!UICONTROL Tipo de campanha móvel].

## Renomear a tecla de classificação Nenhum {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steps that describe how to rename a non-classified key that displays as *`none`* in reporting.

1. Utilizando o importador, exporte classificações para um arquivo local.
1. Add a row to the file, and type [!DNL ~none~] in the Key column.
1. Na linha adicionada, digite o mais nome descritivo na devida coluna de classificação. 

   Para seguir o exemplo deste documento, você poderá digitar "campanha não móvel" em uma coluna nomeada [!UICONTROL Nome da campanha móvel].

   Essa entrada renomeia *`None`* ao *`non-mobile campaign`* relatório [!UICONTROL de Tipo] de campanha móvel.
1. [Importar os dados](../../../components/c-classifications2/c-classifications-importer/import-file.md#concept_F88785E2BDFD448CB5D1DA3491466B0D) de volta para o sistema.
