---
title: Gerenciar anotações
description: Como gerenciar anotações no Espaço de trabalho.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 285bb11eb34ad02bf57227341f9a0931860c5c88
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 64%

---

# Gerenciar anotações

>[!NOTE]
>
>A implantação gradual desse recurso terá início em 23 de março de 2022. Disponibilidade geral: 11 de abril de 2022.

O gerenciador em [!UICONTROL Componentes] > [!UICONTROL Anotações] oferece várias formas de gerenciar anotações, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O gerenciador [!UICONTROL Anotações] mostra todas as anotações que você possui que foram segmentadas para todos os seus projetos e que foram compartilhadas com você.

>[!NOTE]
>
>As [!UICONTROL Anotações] que você criou apenas para um projeto específico não aparecem no gerenciador.

## Interface do usuário do Gerenciador de anotações

![](assets/annotation-mgr.png)

| Elemento da interface | Descrição |
| --- | --- | 
| [!UICONTROL Título e descrição] | Fornecidos no Construtor de anotações. Para editar o título e a descrição, clique no link de título. Isso leva você até o Construtor de anotações. |
| [!UICONTROL Conjunto de relatórios] | O(s) conjunto(s) de relatórios aos quais essa anotação se aplica. |
| [!UICONTROL Proprietário] | Indica quem é o proprietário da anotação. Como um usuário não administrador, você pode ver somente as suas anotações ou as que foram compartilhadas com você. |
| [!UICONTROL Intervalo de datas aplicado] | A data ou o intervalo de datas ao qual essa anotação se aplica. |
| [!UICONTROL Compartilhado com] | Lista com quantos indivíduos ou grupos a anotação foi compartilhada. Clique para obter mais detalhes. |
| [!UICONTROL Data de modificação] | Mostra a data e a hora em que a anotação foi modificada pela última vez. |

## Editar anotações

Editar uma anotação significa que você pode ajustar intervalos de datas, cores, escopo ou se ela se aplica ou não a todos os conjuntos de relatórios ou projetos. É possível editar anotações de duas formas:

* Em um gráfico de linhas, passe o mouse sobre a anotação e clique no ícone de lápis dentro do popover.

* No [!UICONTROL Gerenciador de anotações], clique no título da anotação.

Ambas as opções levam você de volta ao [!UICONTROL Construtor de anotações]. Lá, é possível fazer os ajustes necessários e salvar a nova versão.

## Compartilhar anotações

Ao compartilhar anotações ou trabalhar com anotações compartilhadas com você, lembre-se:

* Digamos que você crie um projeto com anotações somente de projeto e, em seguida, compartilhe o projeto com outro usuário. Essas anotações serão exibidas, mas não poderão ser editadas ou excluídas por ninguém com quem você compartilha o projeto.

* Se você salvar uma anotação e compartilhá-la diretamente com um usuário, ele poderá editar/excluir a anotação somente se tiver direitos de administrador.

* Para recapitular, se o projeto for compartilhado com você, ele será exibido somente nesse projeto. Se a anotação for compartilhada diretamente com você, ela será exibida em todos os projetos nos quais essa anotação pode ser exibida.

## Anotações e fusos horários

Todas as anotações são criadas com um carimbo de data e hora, mas sem informações de horas ou fuso horário. No momento do relatório, o fuso horário do conjunto de relatórios do painel é sempre aplicado. Assim, uma anotação criada para o dia de Natal acontece em 25 de dezembro - independentemente do fuso horário do conjunto de relatórios em que você estiver.

Outro exemplo é o Dia de Ano Novo. A cada hora, um fuso horário diferente dispara fogos de artifício conforme o ano novo começa. Às 22h00, Hora das Montanhas dos EUA, a costa leste dos EUA está disparando o fogo porque já é 12h da Hora do Leste.

## Outras tarefas de anotações

O Gerenciador de anotações permite aos administradores editar, adicionar, marcar, excluir, renomear, aprovar, copiar, exportar e filtrar anotações. Não é visível para usuários não administrativos.

Basta selecionar uma ou mais anotações e a barra de tarefas é exibida.

| Tarefa | Descrição |
| --- | --- |
| [!UICONTROL Adicionar] | Direciona para o construtor de anotações, onde é possível criar novas anotações. |
| [!UICONTROL Tag] | Todos os usuários podem criar tags para anotações e aplicar uma ou mais tags a uma anotação. No entanto, você pode ver tags somente para as anotações que possui. Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis:<ul><li>Tags com base em nomes de equipe, como Marketing social, Marketing móvel</li><li>Tags de projeto (tags de análise), como análises de página de entrada</li><li>Tags de categoria: masculino; geografia</li><li>Tags de fluxo de trabalho: organizado para (uma unidade de negócio específica); Aprovado</li></ul> |
| [!UICONTROL Excluir] | Excluir uma anotação a remove de qualquer projeto em sua organização. |
| [!UICONTROL Renomear] | Renomear uma anotação a renomeia em todos os projetos aos quais foi aplicada. |
| [!UICONTROL Copiar] | Cria uma cópia distinta com sua própria ID de anotação, mas com o mesmo nome e definição. |
| [!UICONTROL Exportar para CSV] | Exporte a definição da anotação para um arquivo CSV. |
| [!UICONTROL Filtro] (painel esquerdo) | Filtre por tags, conjunto de relatórios, proprietários e outros filtros (Meus, Aprovados, Favoritos, Compartilhados comigo e Mostrar todos). |
