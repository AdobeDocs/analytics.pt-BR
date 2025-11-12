---
description: Como adicionar, editar, aplicar e filtrar segmentos do Adobe Analytics no Report Builder.
title: Gerenciar segmentos (Report Builder)
feature: Report Builder
role: User, Admin
exl-id: c4ad89e0-91c9-47e1-a226-69d82fdb8918
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 31%

---

# Gerenciar segmentos

{{legacy-arb}}

Como adicionar, editar, aplicar e filtrar segmentos do Adobe Analytics no Report Builder.

O Report Builder apresenta um painel de segmentação na Etapa 1 do Assistente de solicitações que permite criar e gerenciar segmentos.

![Captura de tela mostrando as opções de Segmento para Adicionar, Editar ou Limpar segmentos e realçando os ícones Controlar, Filtrar e Atualizar.](assets/seg_dialog.png)

## Adicionar ou editar segmentos {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>Para adicionar ou editar segmentos, a interface de segmentos do Report Builder inicia o construtor de segmentos do Analytics em uma janela do Microsoft Internet Explorer. Sua sessão do Report Builder permanecerá ativa. Não há suporte para navegadores diferentes do Internet Explorer para esta operação.

1. No painel de segmentos da Etapa 1 do Assistente de solicitações, clique em **[!UICONTROL Adicionar]**.
1. Uma janela do Internet Explorer é aberta, abrindo a interface do Construtor de segmentos do Analytics. Para obter informações sobre como criar segmentos, consulte a [segmentação do Analytics](/help/components/segmentation/seg-home.md).
1. Depois de definir e salvar o segmento, volte para o Assistente de solicitações.
1. Clique no ícone Atualizar para atualizar a lista de segmentos.

>[!IMPORTANT]
>
>Essa lista está armazenada em cache e o segmento criado recentemente não será exibido, até que você faça uma atualização.

## Criar segmentos em contexto {#section_6DD2C663B2854469AA1075438F907678}

É possível ter combinações específicas de dimensões de relatórios que você deseja transformar em um segmento. É possível criar esses segmentos na interface do Report Builder. Por exemplo, selecione algumas páginas de uma saída de solicitação de página e crie um segmento com base nesses valores.

1. Selecione os itens de saída de relatório que você deseja transformar em um segmento.
1. Clique com o botão direito para selecionar **[!UICONTROL Criar segmento no contexto em]** e especifique o contêiner apropriado (Contêiner de ocorrências, Contêiner de visitas, Contêiner de visitantes).

   ![Captura de tela mostrando Criar segmento no contexto nas opções de contêiner selecionadas e disponíveis.](assets/seg_in_context.png)

   Para obter mais informações sobre containers, consulte o [Guia de Segmentação](/help/components/segmentation/seg-home.md).

1. A Interface do usuário do construtor de segmentos agora será inicializada no Internet Explorer. A interface do usuário do Construtor de segmentos será inicializada com o contêiner e o filtro especificados.
1. Depois de adicionar um nome e uma descrição ao segmento, salve-o.
1. Retorne ao Report Builder e clique no ícone Atualizar para atualizar a lista de segmentos.
1. Agora você está pronto para aplicar esse segmento.

## Pesquisar por e aplicar segmentos

Qualquer segmento criado no Reports &amp; Analytics (agora encerrado), Report Builder ou Data Warehouse aparece na lista de segmentos. Para atualizar a lista, clique no ícone Atualizar ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg).

Você pode aplicar um ou mais segmentos a qualquer solicitação. Isso inclui segmentos sequenciais.

1. Vá até a lista suspensa **[!UICONTROL Segmento]** e clique na seta pequena para baixo na caixa **[!UICONTROL Escolher segmento]** para exibir todos os segmentos.

1. Marque quais segmentos você deseja aplicar.

   ![Captura de tela mostrando os segmentos selecionados.](assets/seg_list.png)

>[!NOTE]
>
>Caso seja o Administrador ou não, no Report Builder é possível visualizar apenas os segmentos de sua propriedade e aqueles que foram compartilhados com você.

## Filtrar segmentos {#filter}

**Filtre** segmentos ao clicar no ícone Filtrar: ![Ícone Filtrar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)

Os filtros disponíveis são:

| Nome do filtro | Descrição |
|---|---|
| Tags | Permite filtrar por segmentos com tags específicas. Observe que os filtros de tags usam o operador AND. Se você marcar duas marcas, o painel direito mostrará segmentos que foram marcados com **ambas** marcas. |
| Proprietários | Permite que você filtre segmentos por proprietário. Observe que os filtros Proprietários usam o operador OR. Se você marcar dois proprietários, o painel direito mostrará os segmentos que pertencem ao proprietário **qualquer**. |
| Outros filtros > Somente *nome do conjunto de relatórios* | Se você aplicar o filtro &quot;Somente *nome do conjunto de relatórios*&quot; no Construtor de segmentos no Adobe Analytics e, em seguida, exibir o Filtro avançado em [!DNL Report Builder], o filtro Avançado exibirá o segmento somente para o conjunto de relatórios selecionados. |
| Outros filtros > Meus | Mostra todos os segmentos que você possui. |
| Outros filtros > Compartilhados comigo | Mostra todos os segmentos que outras pessoas compartilharam com você. |
| Outros filtros > Favoritos | Mostra todos os segmentos que você marcou como Favoritos. |
| Outros filtros > Aprovado | Mostra todos os segmentos oficialmente aprovados. |

## Adicionar um controle de segmento a uma pasta de trabalho {#segment-control}

Adicionar um controle de segmento permite você alternar segmentos de uma pasta de trabalho em vez de precisar ir até o Assistente de solicitação.

1. Clique no ícone de Controle ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) ao lado do menu suspenso de segmentos.

1. Marque todos os segmentos que você deseja exibir no controle de segmentos ou marque **[!UICONTROL Selecionar tudo]**.

   ![Captura de tela da caixa de diálogo Configurações de Controle com todos os segmentos selecionados.](assets/seg_control.png)

1. Observe a opção **[!UICONTROL Atualizar automaticamente solicitações vinculadas após a seleção do item]**.

   * Se marcado, todas as solicitações que usam esse controle serão atualizadas.
   * Se não estiver marcada, os parâmetros de solicitação associados são atualizados, mas as solicitações não são atualizadas.

1. Especifique o local da célula superior esquerda do controle de segmento.

1. Clique em **[!UICONTROL OK]** e o controle de segmento aparece no local especificado.

   ![Captura de tela mostrando o campo suspenso Escolher segmento.](assets/seg_control2.png)

## Atualizar a lista de segmentos {#refresh}

Sempre que você adicionar um novo segmento ou editar um já existente, você deve clicar no ícone Atualizar ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) para atualizar a lista de segmentos em cache.

## Gerenciamento de segmentos em solicitações {#manage}

Antes do v5.4, o Report Builder permitia que os usuários alterassem segmentos em várias solicitações. No entanto, esse processo sempre substituiu os segmentos existentes. Os usuários que queriam adicionar um novo segmento a cada solicitação não podiam fazer isso, pois adicionar o segmento removeria o conjunto anterior de segmentos já atribuído a cada solicitação.

O Report Builder 5.4 permite adicionar, remover, substituir e substituir todos os segmentos em várias solicitações:

1. Selecione várias solicitações em uma pasta de trabalho.
1. Clique com o botão direito do mouse e selecione **[!UICONTROL Editar solicitações]** > **[!UICONTROL Por segmento]**.

   ![Captura de tela mostrando as solicitações de edição e por segmento selecionadas.](assets/edit_by_segment.png)

1. Na caixa de diálogo Editar grupo, selecione uma das quatro opções:

   | Opção | Descrição |
   |---|---|
   | Adicionar segmento | Permite escolher um ou mais segmentos para adicionar à lista de segmentos atuais. |
   | Substituir segmento(s) | Permite escolher quais segmentos substituir por um ou mais segmentos. |
   | Substituir todos os segmentos por | Permite escolher um ou mais segmentos para substituir os segmentos atuais. |
   | Remover segmento(s) | Permite remover segmentos das solicitações. |
