---
description: Gerenciar alertas.
title: Visão geral do Alert Manager
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 637f498c8abee0f3c83780bccd0447f2e3a804e3
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 33%

---

# Gerenciador de alertas

O gerenciador de Alertas está estruturado da mesma forma que o [Gerenciador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=pt-BR) e a variável [Gerenciador de métrica calculada](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=pt-BR).

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

1. No Adobe Analytics, selecione a variável **[!UICONTROL Componentes]** e selecione **[!UICONTROL Alertas]**.

1. No Gerenciador de alertas, selecione a variável **Personalizar colunas** ícone ![Ícone Personalizar colunas](assets/customize-columns-icon.png), em seguida, selecione as colunas que deseja exibir no gerenciador de Alertas.

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
   | Última utilização | **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra a data em que o alerta foi usado pela última vez.</p> <p>Essas informações podem ajudar você a determinar se um alerta é importante para os usuários em sua organização ou se deve ser excluído.</p><p>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</p> |

   {style="table-layout:auto"}
