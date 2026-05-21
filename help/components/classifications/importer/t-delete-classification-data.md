---
description: Etapas que descrevem como excluir ou remover dados de classificação.
title: Excluir dados de classificação
feature: Classifications
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
TQID: https://experienceleague.adobe.com/NZhXTXSwpA-E-6JaGRInMf3TMwHp5A1uMSjaAU1whts
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 85%

---

# Excluir dados de classificação

{{classification-importer-deprecation}}

Às vezes, é necessário remover os dados de classificação depois de serem carregados. Use `~empty~` ou `~deletekey~`, dependendo do que deseja remover.

## Etapas para remover dados de classificação

A remoção de dados de classificação envolve o upload de um arquivo de classificação que contém `~empty~` ou `~deletekey~` nas células apropriadas.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.
1. Clique em **[!UICONTROL Exportação de navegador]**.
1. Selecione o conjunto de relatórios e o conjunto de dados dos quais deseja remover os dados de classificação.
1. Ajuste todas as configurações opcionais para filtrar dados específicos que esteja procurando e clique em **[!UICONTROL Exportar arquivo]**.
1. Após o download do arquivo, abra-o e substitua os valores de classificação por `~empty~` ou `~deletekey~`.
1. Salve o arquivo como um arquivo de texto delimitado por tabulação.
1. Clique em **[!UICONTROL Importar arquivo]** e carregue o arquivo de classificação salvo novamente no Adobe Analytics.

## Excluir um valor de classificação individual

Várias classificações podem pertencer à mesma variável. Por exemplo, você pode ter duas classificações diferentes de eVar1. Se você deseja remover apenas um único valor classificado, substitua o valor de classificação por `~empty~`. Por exemplo:

| SKU do inventário (eVar8) | Nome do inventário | Categoria do inventário |
| --- | --- | --- |
| 857467 | Suéter de pescoço V | Vestuário feminino |
| 948203 | Tornozeleira | Jóias |
| 174391 | Calças brancas de veludo | `~empty~` |

O uso de `~empty~` na classificação Categoria de inventário ainda preserva os dados para a classificação Nome de inventário. O valor `~empty~` exclui apenas os dados de classificação dessa célula.

## Excluir uma linha de classificação inteira

Use `~deletekey~` em qualquer coluna para excluir a linha de classificação inteira. Por exemplo:

| SKU do inventário (eVar8) | Nome do inventário | Categoria do inventário |
| --- | --- | --- |
| 857467 | Suéter de pescoço V | Vestuário feminino |
| 948203 | Tornozeleira | Jóias |
| 174391 | Calças brancas de veludo | `~deletekey~` |

O uso de `~deletekey~` na classificação Categoria do inventário exclui todos os dados de classificação do valor principal `174391`. Como se a linha nunca tivesse sido classificada.

## Imprevistos e dicas

* Se estiver usando `~deletekey~`, você só precisará de um por linha em um arquivo de classificação.
* `~empty~` e `~deletekey~` devem ser correspondências *exatas*. Não são permitidos espaços nem maiúsculas.
* Não é possível excluir valores na coluna principal. Esses valores são transmitidos diretamente para a variável e são permanentes.
* Se você remover um valor de classificação que tenha subclassificações, elas também serão removidas. As classificações não podem existir sem um valor principal, e o pai de uma subclassificação é seu valor principal.
* É possível remover os dados de subclassificação, deixando a classificação principal intacta.
