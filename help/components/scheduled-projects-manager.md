---
description: Consulte e gerencie relatórios programados na organização.
title: Gerenciador de projetos programados
feature: Admin Tools
source-git-commit: d65ef389ae9bc3164be928ffe64cc805b8b1e59d
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 86%

---

# Projetos programados

Os projetos programados do Analysis Workspace podem ser gerenciados em **Analytics > Componentes > Projetos programados**.

Ao gerenciar projetos agendados, você pode editar e excluir agendamentos de projetos recorrentes:

* Alterar o tipo de arquivo (.csv ou PDF)
* Atualizar a descrição do projeto
* Adicionar ou remover destinatários
* Alterar a frequência

Para modificar um projeto agendado

1. Selecionar **Analytics > Componentes > Projetos agendados**.
1. Procure uma programação na barra de pesquisa ou usando as opções de filtro no painel esquerdo. Você pode filtrar por [!UICONTROL Tags], [!UICONTROL Proprietários], [!UICONTROL Favoritos] e muito mais.

![Captura de tela mostrando a lista de projetos agendados com a coluna exibindo o título, o proprietário, as tags, as entregas a e outras colunas descritas na seção Colunas disponíveis.](assets/scheduled-project-manager2.png)

## Colunas disponíveis

| Campo | Descrição |
| --- | --- |
| [!UICONTROL Favoritos] | Selecionar o ícone de estrela torna esta programação uma favorita. |
| [!UICONTROL ID da programação] | Essa ID é usada principalmente para fins de depuração. |
| [!UICONTROL Título e descrição] | Título e descrição deste projeto. |
| [!UICONTROL Proprietário] | A pessoa que criou e é proprietária do projeto. |
| [!UICONTROL Tags] | (opcional) Adicionar tags é uma boa maneira de organizar projetos. Todos os usuários podem criar tags e aplicar uma ou mais tags a um projeto. No entanto, é possível visualizar tags somente para os projetos que você possui ou que foram compartilhados com você. |
| [!UICONTROL Entregue a] | O(s) destinatário(s) deste projeto programado. |
| [!UICONTROL Data de expiração] | Para qualquer frequência de projeto programado, é possível definir a data de expiração de até um ano no futuro. |
| [!UICONTROL Frequência] | Com que frequência deseja que esse projeto programado seja enviado ao(s) destinatário(s). |
| [!UICONTROL Tempo de execução] | Em que hora do dia esse projeto programado será enviado. |
| [!UICONTROL Número de consultas] | O número de consultas relativas a este projeto. |

## Ações comuns

As ações a seguir são comuns no Gerenciador de projetos programados:

| Ação | Descrição |
|---|---|
| **[!UICONTROL Editar]** | Clique no título da programação para atualizar as configurações de entrega. |
| **[!UICONTROL Excluir]** | Selecione o projeto programado na lista e clique em Excluir no menu. Essa ação eliminará o calendário selecionado para o projeto; o projeto em si não será excluído. |
| **[!UICONTROL Tag]** | Selecione o projeto programado na lista e escolha “Tag” ou “Aprovar” para organizar as programações e facilitar a pesquisa. |
| **[!UICONTROL Exibir programações com falha]** | Acesse o painel esquerdo > Outros filtros > Falha para visualizar as programações que apresentaram falhas. |
| **[!UICONTROL Exibir programações expiradas]** | Acesse o painel esquerdo > Outros filtros > Expirado para ver as programações que expiraram. Clique no título da programação para configurar uma nova programação de entrega. |
| **[!UICONTROL Exibir ID de programação]** | Acesse as opções de coluna na parte superior direita e adicione a coluna ID de programação à tabela. A ID programada geralmente é útil para depuração. |

O Gerenciador de projetos programados mostra os itens criados por um usuário específico. Se a conta de usuário for desabilitada no aplicativo, todas as entregas programadas serão interrompidas. A propriedade do projeto programado pode ser transferida para um novo usuário em **Administrador** > **Usuários e ativos do Analytics** > **Transferir ativos**.