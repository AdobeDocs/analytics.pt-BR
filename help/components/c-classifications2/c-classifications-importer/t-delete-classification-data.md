---
description: Etapas que descrevem como excluir ou remover dados da classificação.
subtopic: Classifications
title: Excluir dados de classificação
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Excluir dados de classificação

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
* Se você estiver removendo um valor de classificação que possua subclassificações, elas também serão removidas. As classificações não podem existir sem um valor principal, e o pai de uma subclassificação é seu valor principal.
* É possível remover dados de subclassificação deixando sua classificação pai intacta.
