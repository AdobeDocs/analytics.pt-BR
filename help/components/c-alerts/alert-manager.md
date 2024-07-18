---
description: Gerenciar alertas.
title: Visão geral do Alert Manager
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 9a6c2e7c2f83882f6df630f975b0c44e75a2ed7a
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 31%

---

# Gerenciador de alertas

O gerenciador de Alertas está estruturado de maneira semelhante ao [Gerenciador de Segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=pt-BR) e ao [Gerenciador de Métricas Calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=pt-BR).

![](assets/alert-manager.png)

## Acessar o gerenciador de Alertas

1. No Adobe Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Alertas**].

## Ações disponíveis no gerenciador de alertas

No gerenciador de Alertas, é possível:

* Acesse o Criador de alertas, clicando em **[!UICONTROL + Adicionar]**.
* Marcar alertas. Isso permite organizá-los para facilitar o uso.
* Excluir alertas.
* Renomear alertas.
* Aprovar alertas.
* Copiar alertas.
* Ativar/desativar alertas.
* **Renovar** uma data de expiração para o alerta. Quando um ou mais alertas são selecionados, podem ser renovados ao clicar em **[!UICONTROL Renovar]**. Isso estende as datas de expiração em 1 ano a partir do dia de **[!UICONTROL Renovação]**, independentemente da data de expiração original.
* Exportar um alerta para um arquivo .CSV.
* Editar alertas ao clicar duas vezes no título do alerta.
* Pesquisar por alertas.
* Adicionar alertas a outros conjuntos de relatórios.
* Especificar/alterar o proprietário de um alerta.
* Adicionar outros filtros.
* Definir uma **data de expiração** para o alerta.

## Configurar colunas

Você pode configurar as informações exibidas para cada alerta no Gerenciador de alertas, configurando as colunas exibidas.

Para configurar as colunas visíveis no Gerenciador de alertas:

1. No Adobe Analytics, selecione a guia **[!UICONTROL Componentes]** e selecione **[!UICONTROL Alertas]**.

1. No Gerenciador de alertas, selecione o ícone **Personalizar colunas** ![Ícone Personalizar colunas](assets/customize-columns-icon.png) e selecione as colunas que deseja exibir no gerenciador de alertas.

   As seguintes colunas estão disponíveis:

   | Título da coluna | Descrição |
   |---|---|
   | Favoritos | Exibe ícones de estrela ao lado de cada alerta, permitindo marcar os alertas como favoritos. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Título e descrição | Esses valores são fornecidos no Criador de alertas. Para editar o título e a descrição, selecione o link de título para abrir o Criador de alertas. |
   | Conjunto de relatórios | Indica em qual conjunto de relatórios o alerta foi salvo pela última vez. |
   | Proprietário | Indica quem possui o alerta. Como um usuário não administrativo, você pode ver somente os alertas que possui ou que foram compartilhados com você. |
   | Tags | Mostra marcas que foram aplicadas ao alerta por você ou por pessoas que compartilharam o alerta com você. |
   | Compartilhado com | Lista indivíduos ou grupos (somente administrador) ou Todos (somente administrador) com os quais você compartilhou o alerta. |
   | Data de modificação | Indica a data em que o alerta foi modificado pela última vez. |
   | Última utilização | Mostra a data em que o alerta foi usado pela última vez. <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</li><li>Para alguns componentes, essa coluna pode não conter dados se o componente tiver sido usado pela última vez antes de setembro de 2023.</li></ul> |

   {style="table-layout:auto"}
