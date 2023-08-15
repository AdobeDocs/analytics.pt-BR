---
description: Consulte e gerencie relatórios agendados na organização.
title: Gerenciador de projetos programados
feature: Admin Tools
source-git-commit: 8d0cf795b0366b2797fa0574ae9faaffb76b005e
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 74%

---

# Projetos programados

Os projetos programados do Analysis Workspace podem ser gerenciados em **Analytics > Componentes > Projetos programados**.

Ao gerenciar projetos agendados, você pode editar e excluir agendamentos de projetos recorrentes. Procure um agendamento na barra de pesquisa ou usando as opções de filtro no painel esquerdo. Você pode filtrar por [!UICONTROL Tags], [!UICONTROL Proprietários], [!UICONTROL Favoritos]e muito mais.

![](assets/scheduled-project-manager2.png)

## Colunas disponíveis

| Campo | Descrição |
| --- | --- |
| [!UICONTROL Favoritos] | Selecionar o ícone de estrela torna esta programação uma favorita. |
| [!UICONTROL ID de agendamento] | Essa ID é usada principalmente para fins de depuração. |
| [!UICONTROL Título e descrição] | Título e descrição deste projeto. |
| [!UICONTROL Proprietário] | A pessoa que criou e é proprietária do projeto. |
| [!UICONTROL Tags] | (opcional) Adicionar tags é uma boa maneira de organizar projetos. Todos os usuários podem criar tags e aplicar uma ou mais tags a um projeto. No entanto, é possível visualizar tags somente para os projetos que você possui ou que foram compartilhados com você. |
| [!UICONTROL Entregue para] | O(s) recipient(s) deste projeto programado. |
| [!UICONTROL Data de validade] | Para qualquer frequência de projeto agendada, você pode definir a data de expiração de até um ano no futuro. |
| [!UICONTROL Frequência] | Com que frequência deseja que esse projeto programado seja enviado ao(s) recipient(s). |
| [!UICONTROL Tempo de execução] | Em que hora do dia esse projeto programado é enviado. |
| [!UICONTROL Número de consultas] | O número de consultas relativas a este projeto. |

## Ações comuns

As ações a seguir são comuns no Gerenciador de projetos programados:

| Ação | Descrição |
|---|---|
| **[!UICONTROL Editar]** | Selecione o título do agendamento para atualizar suas configurações de delivery. |
| **[!UICONTROL Excluir]** | Selecione o projeto programado na lista e clique em Excluir no menu. Essa ação eliminará o calendário selecionado para o projeto; o projeto em si não será excluído. |
| **[!UICONTROL Tag]** | Selecione o projeto programado na lista e escolha “Tag” ou “Aprovar” para organizar as programações e facilitar a pesquisa. |
| **[!UICONTROL Exibir programações com falha]** | Acesse o painel esquerdo > Outros filtros > Falha para visualizar as programações que apresentaram falhas. |
| **[!UICONTROL Exibir programações expiradas]** | Acesse o painel esquerdo > Outros filtros > Expirado para ver as programações que expiraram. Clique no título da programação para configurar uma nova programação de delivery. |
| **[!UICONTROL Exibir ID de programação]** | Acesse as opções de coluna na parte superior direita e adicione a coluna ID de programação à tabela. A ID programada geralmente é útil para depuração. |

O Gerenciador de agendamento de projetos mostra os itens que um usuário específico criou. Se a conta de usuário estiver desabilitada no aplicativo, todas as entregas programadas são interrompidas. A propriedade do projeto agendado pode ser transferida para um novo usuário em **Admin** > **Usuários e ativos do Analytics** > **Transferir ativos**.