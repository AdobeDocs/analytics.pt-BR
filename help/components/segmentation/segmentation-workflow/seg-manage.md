---
description: O Gerenciador de segmentos oferece várias formas de cuidar de segmentos, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.
title: Gerenciar segmentos (Gerenciador de segmentos)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 8e8f59f747ddacc5462cbc177d199a5e0e91908a
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 27%

---

# Gerenciador de segmentos

O Gerenciador de segmentos oferece várias formas de cuidar de segmentos, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O Gerenciador de segmentos do Analytics mostra todos os seus segmentos e os compartilhados com você. Os usuários de nível administrativo podem visualizar todos os segmentos na organização. Essa visão geral apresenta a interface do usuário e os recursos do Gerenciador de segmentos.

![Gerenciador de segmentos](assets/segments-manager.png)

## Acessar o Gerenciador de segmentos

1. No Adobe Analytics, selecione a guia **[!UICONTROL Componentes]** e, em seguida, selecione **[!UICONTROL Segmentos]**.

   Ou

   Em um relatório existente, selecione o ícone de Segmentos ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) na navegação à esquerda e selecione **[!UICONTROL Gerenciar]**.

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

1. No Adobe Analytics, selecione a guia **[!UICONTROL Componentes]** e, em seguida, selecione **[!UICONTROL Segmentos]**.

1. No Gerenciador de segmentos, selecione o ícone **Personalizar colunas** ![Ícone Personalizar colunas](assets/customize-columns-icon.png) e selecione as colunas que deseja exibir no Gerenciador de segmentos.

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
   | Usado em | Mostra onde os segmentos estão sendo usados atualmente e quantas vezes eles estão sendo usados em cada área. <p>Por exemplo, se o segmento estiver sendo usado em 40 projetos e 2 alertas, o valor dessa coluna será exibido como [!UICONTROL **42 componentes**].</p> <p>Selecione o valor desta coluna para ver o detalhamento de onde os segmentos estão sendo usados (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Alertas (2)**]). Além disso, é possível visualizar a lista de itens em que os segmentos estão sendo usados. Por exemplo, para ver a lista de projetos em que estão sendo usados, selecione o link [!UICONTROL **Projetos (40)**].</p><p>Cada uma das áreas a seguir mostra o número de instâncias de segmentos sendo usadas nessa área:</p>  <ul><li>[!UICONTROL **Projetos**]<p>Contém segmentos que foram [criados no construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) e estão disponíveis para todos os projetos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contém segmentos que foram [criados como segmentos rápidos](/help/analyze/analysis-workspace/components/segments/quick-segments.md) e estão disponíveis somente em um único projeto.</p></li><li>[!UICONTROL **Projetos programados**]</li><li>[!UICONTROL **Scorecards para dispositivos móveis**]</li><li>[!UICONTROL **Anotações**]</li><li>[!UICONTROL **Alertas**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Selecionar essa opção baixa um arquivo CSV com as seguintes colunas de dados:</p><ul><li>Nome do Report Builder</li><li>Último acesso</li><li>ID de usuário IMS acessada pela última vez</li><li>Nome do usuário acessado por último</li></ul><p>Ao visualizar informações sobre o Report Builder, as informações de uso estarão disponíveis a partir de setembro de 2024.</p></li></ul><p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações estão disponíveis somente para administradores do sistema.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. [Configure as colunas](#configure-columns) para exibi-las.</li><li>Se um segmento inclui outro segmento em sua definição, o uso desse segmento não será mostrado na coluna [!UICONTROL **Usado em**]. Se um segmento for incluído na definição de outro tipo de componente (como uma métrica calculada), o uso será mostrado na coluna [!UICONTROL **Usado em**].</li><li>Essas informações não incluem o uso da API ou da Data Warehouse.</li><li>Se não houver dados nesta coluna para um determinado componente, mas ela tiver uma data [!UICONTROL **Última utilização**], o componente pode ter sido usado em uma análise sem ser salvo.</li><li>As informações de uso disponíveis são a partir de setembro de 2023.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> |
   | Última utilização | Mostra a data em que o segmento foi usado pela última vez em qualquer um dos seguintes tipos de componentes: <ul><li>Alertas</li><li>Métricas calculadas</li><li>Projetos</li><li>Projetos programados</li><li>Segmentos</li></ul> <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</li><li>Para alguns componentes, essa coluna pode não conter dados se o componente tiver sido usado pela última vez antes de setembro de 2023.</li><li>Essas informações estão disponíveis somente para administradores do sistema.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |

   {style="table-layout:auto"}

## Vídeo passo a passo {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

Este [vídeo do sobre o Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=pt-BR) proporciona uma breve visão geral sobre como usar o Gerenciador de segmentos.


