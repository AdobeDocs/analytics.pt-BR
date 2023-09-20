---
description: O Gerenciador de segmentos oferece várias formas de cuidar de segmentos, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.
title: Gerenciar segmentos (Gerenciador de segmentos)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 637f498c8abee0f3c83780bccd0447f2e3a804e3
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 39%

---

# Gerenciador de segmentos

O Gerenciador de segmentos oferece várias formas de cuidar de segmentos, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O Gerenciador de segmentos do Analytics mostra todos os seus segmentos e os compartilhados com você. Os usuários de nível administrativo podem visualizar todos os segmentos na organização. Essa visão geral apresenta a interface do usuário e os recursos do Gerenciador de segmentos.

![Gerenciador de segmentos](assets/segments-manager.png)

## Acessar o Gerenciador de segmentos

1. No Adobe Analytics, selecione a variável **[!UICONTROL Componentes]** e selecione **[!UICONTROL Segmentos]**.

   Ou

   Em um relatório existente, selecione o ícone Segmentos ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) na navegação à esquerda, selecione **[!UICONTROL Gerenciar]**.

## Ações disponíveis no Gerenciador de segmentos

No Gerenciador de segmentos, é possível:

* [Filtrar segmentos](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Marcar segmentos como favoritos](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Aprovar segmentos](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Marcar segmentos](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Compartilhar segmentos](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Exporte um segmento para um arquivo CSV.

* [Copiar segmentos](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Excluir segmentos](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configurar colunas

Você pode configurar as informações exibidas para cada segmento no Gerenciador de segmentos configurando as colunas exibidas.

Para configurar as colunas visíveis no Gerenciador de segmentos:

1. No Adobe Analytics, selecione a variável **[!UICONTROL Componentes]** e selecione **[!UICONTROL Segmentos]**.

1. No Gerenciador de segmentos, selecione a variável **Personalizar colunas** ícone ![Ícone Personalizar colunas](assets/customize-columns-icon.png), em seguida, selecione as colunas que deseja exibir no Gerenciador de segmentos.

   As seguintes colunas estão disponíveis:

   | Título da coluna | Descrição |
   |---|---|
   | Título e descrição | Esses valores são fornecidos no Construtor de segmentos. Para editar o título e a descrição, selecione o link de título para abrir o Construtor de segmentos. |
   | Favoritos | Exibe ícones de estrela ao lado de cada segmento, permitindo marcar segmentos como favoritos. Para obter mais informações, consulte [Marcar segmentos como favoritos](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Conjuntos de relatórios | Essa coluna indica em qual conjunto de relatórios o segmento foi salvo pela última vez. |
   | Proprietário | Indica quem é o proprietário do segmento. Como um não administrador, você pode visualizar somente seus segmentos ou os compartilhados com você. |
   | Tags (não marcadas no seletor de colunas, portanto, a coluna não aparece) | Tags aplicadas ao segmento, por você ou outras pessoas que compartilharam o segmento com você. |
   | Compartilhado com | Lista indivíduos ou grupos (somente Administrador) ou Todos (somente Administrador) com os quais você compartilhou o segmento. <p>Quando um segmento é compartilhado por você ou com você, um ícone de compartilhamento é exibido ao lado do nome do segmento.</p> |
   | Data de modificação | Mostra a data na qual o segmento foi modificado pela última vez. |
   | Usado em | **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra em qual dos seguintes tipos de componentes o segmento está sendo usado no momento:</p> <ul><li>Alertas</li><li>Métricas calculadas </li><li>Projetos</li><li>Projetos programados</li><li>Segmentos</li></ul> Por exemplo, se o segmento estiver sendo usado em 40 projetos e 2 alertas, essa coluna mostrará [!UICONTROL **Alertas (2), Projetos (40)**]. <p>Essas informações podem ajudar você a determinar se um segmento é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</p><p>Você pode usar o [Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) junto com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |
   | Última utilização | **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra a data em que o segmento foi usado pela última vez em qualquer um dos seguintes tipos de componentes:</p> <ul><li>Alertas</li><li>Métricas calculadas </li><li>Projetos</li><li>Projetos programados</li><li>Segmentos</li></ul> <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</p><p>Você pode usar o [Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) junto com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |

   {style="table-layout:auto"}

## Vídeo passo a passo {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

Este [vídeo do sobre o Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=pt-BR) proporciona uma breve visão geral sobre como usar o Gerenciador de segmentos.


