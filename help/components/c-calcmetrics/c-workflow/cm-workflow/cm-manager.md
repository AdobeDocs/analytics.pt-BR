---
description: A página Métricas calculadas oferece várias formas de cuidar de métricas, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.
title: Gerenciador de métricas calculadas
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: df9c6d59ef5f5c43d0e1ef822bd23bc0e09ff20e
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 10%

---

# Gerenciador de métricas calculadas

A página Métricas calculadas oferece várias formas de cuidar de métricas, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.

A página Métricas calculadas mostra todos os segmentos seus e que foram compartilhados com você. Os usuários de nível administrativo podem visualizar todas as métricas personalizadas na organização.

<!-- add screenshot -->

## Acessar o gerenciador de métricas calculadas

1. No Adobe Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Métricas calculadas**].

## Ações disponíveis no Gerenciador de métricas calculadas

No Gerenciador de métricas calculadas, é possível:

* [Filtrar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [Marcar métricas calculadas como favoritas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [Aprovar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [Marcar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [Compartilhar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* Exportar uma métrica calculada para um arquivo CSV.

* [Copiar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* Excluir métricas calculadas

## Configurar colunas

Você pode configurar as informações exibidas para cada métrica calculada no Gerenciador de métricas calculadas, configurando as colunas exibidas.

Para configurar as colunas visíveis no Gerenciador de métricas calculadas:

1. No Adobe Analytics, selecione a guia **[!UICONTROL Componentes]** e selecione **[!UICONTROL Métricas calculadas]**.

1. No gerenciador de métricas calculadas, selecione o ícone **Personalizar colunas** ![Ícone Personalizar colunas](assets/customize-columns-icon.png) e selecione as colunas que deseja exibir no gerenciador de métricas calculadas.

   As seguintes colunas estão disponíveis:

   | Título da coluna | Descrição |
   |---|---|
   | Favoritos | Exibe ícones de estrela ao lado de cada métrica calculada, permitindo marcar métricas calculadas como favoritos. Para obter mais informações, consulte [Marcar métricas calculadas como favoritos](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | Título e descrição | Esses valores são fornecidos no Criador de métrica calculada. Para editar o título e a descrição, selecione o link de título para abrir o Criador de métrica calculada. |
   | Conjunto de relatórios | Indica em qual conjunto de relatórios a métrica foi salva pela última vez. |
   | Proprietário | Indica o proprietário da métrica personalizada. Como um usuário não administrativo, você pode ver somente as métricas que possui ou que foram compartilhadas com você. |
   | Tags | Mostra as tags aplicadas à métrica, por você ou por pessoas que compartilharam a métrica calculada com você. |
   | Compartilhado com | Lista indivíduos ou grupos (somente administrador) ou Todos (somente administrador) com os quais você compartilhou a métrica calculada. <p>Quando uma métrica calculada está sendo compartilhada, um ícone de compartilhamento é exibido ao lado do nome da métrica calculada.</p> |
   | Data de modificação | Indica a data em que a métrica personalizada foi modificada pela última vez. |
   | Usado em | Mostra em quantos componentes a métrica calculada está sendo usada atualmente. <p>Por exemplo, se a métrica calculada estiver sendo usada em 40 projetos e 2 alertas, o valor dessa coluna será exibido como [!UICONTROL **42 componentes**]. <p>Selecione o valor desta coluna para ver o detalhamento de onde a métrica calculada está sendo usada (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Alertas (2)**]).</p><p>As métricas calculadas podem ser usadas em qualquer um dos seguintes tipos de componentes:</p> <ul><li>Alertas</li><li>Projetos</li><li>Projetos programados</li></ul><p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. [Configure as colunas](#configure-columns) para exibi-las.</li><li>Se não houver dados nesta coluna para um determinado componente, mas ela tiver uma data [!UICONTROL **Última utilização**], o componente pode ter sido usado em uma análise sem ser salvo.</li><li>Essas informações estão disponíveis somente para administradores do sistema.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> |
   | Última utilização | Mostra a data em que a métrica calculada foi usada pela última vez em qualquer um dos seguintes tipos de componentes: <ul><li>Alertas</li><li>Métricas calculadas</li><li>Projetos</li><li>Projetos programados</li></ul> <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</li><li>Para alguns componentes, essa coluna pode não conter dados se o componente tiver sido usado pela última vez antes de setembro de 2023.</li><li>Essas informações estão disponíveis somente para administradores do sistema.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |

   {style="table-layout:auto"}
