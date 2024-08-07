---
description: As teclas não classificadas são reunidas nos relatórios de classificação como um único item da linha identificado como Nenhum. Pode ser útil para renomear Nenhum para algo mais descritivo.
title: Chaves não classificadas
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 94%

---

# Chaves não classificadas

As teclas não classificadas são reunidas nos relatórios de classificação como um único item da linha identificado como Nenhum. Pode ser útil para renomear Nenhum para algo mais descritivo.

## Chaves não classificadas {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Chaves não classificadas são reunidas nos relatórios de classificação como um único item da linha identificado *`None`*. Pode ser útil para renomear *`None`* para algo mais descritivo.

Por exemplo, digamos que seus códigos de rastreamento tenham informações que definem o tipo de campanha via celular à qual o código de rastreamento está associado. Você está usando a classificação (Tipo de campanha móvel) para reunir esses códigos de rastreamento em categorias, como Web móvel, aplicativo iOS, aplicativo Android e assim por diante. Algumas campanhas talvez não sejam campanhas móveis, não sendo classificadas com um tipo de campanha móvel. Todos os códigos de rastreamento não classificados seriam agrupados em *`None`* no relatório [!UICONTROL Tipo de campanha móvel].

## Renomear a tecla de classificação Nenhum {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Para renomear uma tecla não classificada que é exibida como *`none`* no relatório:

1. Utilizando o importador, exporte classificações para um arquivo local.
1. Adicione uma linha ao arquivo e digite `~none~` na coluna Tecla.
1. Na linha adicionada, digite o mais nome descritivo na devida coluna de classificação.

   Para seguir o exemplo desta documentação, você poderá digitar &quot;campanha não móvel&quot; em uma coluna nomeada [!UICONTROL Tipo de campanha via celular].

   Essa entrada é renomeada de *`None`* para *`non-mobile campaign`* no relatório [!UICONTROL Tipo de campanha móvel].

   ![Exemplo de uma chave não classificada](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Importar os dados](/help/components/classifications/importer/import-file.md) de volta para o sistema.
