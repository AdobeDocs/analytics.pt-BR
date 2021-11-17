---
description: Envie um projeto do Analysis Workspace por email ou agende o seu envio.
keywords: Analysis Workspace
title: Agendar projetos
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
source-git-commit: 9b0b62691600a682bc53a3aa3b50b8addad32a41
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 78%

---

# Agendar projetos

No **menu Compartilhar**, do Workspace, você pode enviar projetos do Analysis Workspace por email para recipient selecionados. Os arquivos podem ser enviados no formato CSV ou PDF.

## Enviar arquivo agora

Para enviar um arquivo imediatamente aos recipients por email:

1. Clique em **Compartilhar > Enviar arquivo agora**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. Clique em **Enviar agora**.
1. (Opcional) Clique em **Mostrar opções de agendamento** para especificar um agendamento de delivery.

![Enviar arquivo agora](assets/send-file-now.png)

## Enviar arquivo agendado

Para enviar um arquivo por email de acordo com uma programação recorrente a recipients:

1. Clique em **Compartilhar > Enviar arquivo programado**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. Especifique o intervalo ao longo do qual a programação deve ser entregue, modificando as entradas Início e Término. A data de término deve estar no prazo de um ano a partir do dia em que a programação foi criada ou modificada.
1. Especifique a frequência do delivery. Cada frequência permite personalizações diferentes.
1. Clique em **Enviar de acordo com a programação**.

![](assets/send-on-schedule.png)

## Gerenciador de agendamento de projetos

Os projetos programados do Analysis Workspace podem ser gerenciados em **Analytics > Componentes > Projetos programados**.

No Gerenciador de agendamento de projetos, é possível editar e excluir agendamentos de projetos recorrentes. Procure um agendamento na barra de pesquisa ou usando as opções de filtro no painel esquerdo. Você pode filtrar por tag, programação aprovada, proprietários e muito mais.

![](assets/scheduled-project-manager2.png)

| Campo | Descrição |
| --- | --- |
| Favoritos | Selecionar o ícone de estrela torna este agendamento favorito. |
| ID de agendamento | Essa ID é usada principalmente para fins de depuração. |
| Título e descrição | Título e descrição deste projeto. |
| Proprietário | A pessoa que criou e é proprietária do projeto. |
| Tags | (opcional) A marcação é uma boa maneira de organizar projetos. Todos os usuários podem criar tags e aplicar uma ou mais tags a um projeto. No entanto, você pode ver tags somente para os projetos que possui ou que foram compartilhados com você. |
| Entregue para | O(s) destinatário(s) deste projeto agendado(s). |
| Data de validade | A data de expiração padrão é um ano após a data de criação. |
| Frequência | Com que frequência você deseja que esse projeto de agendamento seja enviado aos recipients. |
| Tempo de execução | Em que hora do dia esse projeto agendado é enviado. |
| Número de Consultas | O número de queries em relação a este projeto. |

## Ações comuns

As ações a seguir são comuns no Gerenciador de projetos programados:

| Ação | Descrição |
|---|---|
| **Editar programação** | Clique no título da programação para atualizar as configurações de delivery. |
| **Excluir programação** | Selecione o projeto programado na lista e clique em Excluir no menu. Essa ação eliminará o calendário selecionado para o projeto; o projeto em si não será excluído. |
| **Adicionar tags** | Selecione o projeto programado na lista e escolha “Tag” ou “Aprovar” para organizar as programações e facilitar a pesquisa. |
| **Exibir programações com falha** | Acesse o painel esquerdo > Outros filtros > Falha para visualizar as programações que apresentaram falhas. |
| **Exibir programações expiradas** | Acesse o painel esquerdo > Outros filtros > Expirado para ver as programações que expiraram. Clique no título da programação para configurar uma nova programação de delivery. |
| **Exibir ID de programação** | Acesse as opções de coluna na parte superior direita e adicione a coluna ID de programação à tabela. A ID programada geralmente é útil para depuração. |

O Gerenciador de agendamento de projetos mostra os itens criados por um usuário específico. Se a conta de usuário estiver desabilitada no aplicativo, todas as entregas programadas são interrompidas. A propriedade do projeto programado pode ser **transferida** para um novo usuário em **Admin > Usuários e ativos do Analytics > Transferir ativos**.
