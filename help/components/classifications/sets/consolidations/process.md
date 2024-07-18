---
title: Processo de consolidação do conjunto de classificações
description: O processo completo de consolidação de conjuntos de classificações.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Processo de consolidação do conjunto de classificações

Use essa interface para criar uma consolidação do conjunto de classificações do início ao fim.

## Criação

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Consolidações]** > **[!UICONTROL Adicionar]**

Os seguintes campos estão disponíveis ao criar uma consolidação:

* **[!UICONTROL Nome]**: o nome da consolidação.
* **[!UICONTROL Notificação de problemas]**: uma lista delimitada por vírgulas de endereços de email que são notificados sobre problemas com esta consolidação.
* **[!UICONTROL Conjunto de dados a corresponder]**: uma lista suspensa de todos os conjuntos de classificação.

Depois de selecionar um conjunto de classificações, uma tabela com duas colunas é exibida:

* A coluna direita contém todos os conjuntos de classificações que você deseja consolidar. Ela começa com o conjunto de classificação selecionado usando a lista suspensa acima.
* A coluna da esquerda contém todos os conjuntos de classificações qualificados para serem mesclados com o conjunto de dados selecionado originalmente. **Os esquemas devem corresponder exatamente para se qualificarem para consolidação**. Se os esquemas não corresponderem ao conjunto de classificações selecionado, eles não aparecerão nessa coluna à esquerda.

Arraste os conjuntos de classificações desejados da coluna disponível à esquerda para a coluna de consolidação à direita. Depois que a consolidação receber um nome e dois ou mais conjuntos de classificações estiverem na coluna direita, clique em **[!UICONTROL Salvar e continuar]**.

## Validação

Depois de criar uma consolidação, uma lista de conjuntos de dados de origem é exibida à direita. O botão **[!UICONTROL Validar]** garante que cada conjunto de classificações individual seja válido para esta consolidação. É possível reordenar as etapas de classificação aqui para determinar a prioridade em casos de valores de classificação incompatíveis. **O conjunto de classificações mais alto da lista substitui todos os valores incompatíveis em outros conjuntos de classificações.**

## Executar 

Depois que uma consolidação for validada, você poderá executá-la. A execução de uma consolidação fornece um relatório de similaridade com as seguintes colunas da tabela:

* **[!UICONTROL Nome do conjunto de dados]**: o nome do conjunto de classificações.
* **[!UICONTROL Incompatibilidade]**: a porcentagem de linhas em que os valores de chave não correspondem ao conjunto de classificações de origem. Se a porcentagem de incompatibilidade for alta, é possível que os dados de classificação sejam muito diferentes. Verifique e certifique-se de que os conjuntos de classificações selecionados tenham dados de classificação semelhantes.
* **[!UICONTROL Ausente]**: a porcentagem de linhas em que os valores principais estavam nesse conjunto de classificação, mas não no conjunto de classificação de origem. Todas as linhas ausentes são adicionadas ao conjunto de classificações consolidado.

## Aprovar

Atua como uma última chamada antes de remover os conjuntos de classificações individuais e criar um conjunto de classificações consolidado. Verifique se tudo está correto e clique em **[!UICONTROL Aprovar]**.

Depois de aprovado, o conjunto de classificações consolidado é criado. O status está definido como [!UICONTROL Concluído], e nenhuma outra ação é necessária para a consolidação.
