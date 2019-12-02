---
title: Gerenciar trabalhos do feed de dados
description: Saiba como gerenciar trabalhos individuais em feeds de dados.
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Gerenciar trabalhos do feed de dados

Os trabalhos são tarefas individuais que geram um arquivo compactado. Eles são criados e governados por feeds.

Acesse o gerenciamento de tarefas do feed de dados seguindo estas etapas:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
2. Clique no menu de 9 linhas na parte superior direita e clique em [!UICONTROL Analytics].
3. No menu superior, clique em [!UICONTROL Admin] &gt; Feeds [!UICONTROL de dados].
4. Clique na guia Tarefas perto da parte superior.

![Menu de feed de dados](assets/AdminMenu.png)

## Navegação na interface

Uma tarefa de feed de dados é uma única instância onde a Adobe processa e gera um arquivo compactado para uma determinada janela de relatório. O gestor de postos de trabalho fornece uma visão mais aprofundada para ver o estado dos postos de trabalho individuais.

![Tarefas](assets/jobs.jpg)

### Filtros e pesquisa

Use filtros e pesquise para localizar o trabalho exato que você está procurando.

Na extremidade esquerda, clique no ícone de filtro para mostrar ou ocultar as opções de filtragem. Os filtros são organizados por categoria. Clique na divisa para recolher ou expandir as categorias de filtragem. Clique na caixa de seleção para aplicar esse filtro.

![Filtro](assets/jobs-filter.jpg)

Use a pesquisa para localizar um trabalho por nome.

![Pesquisar](assets/search.jpg)

### Feeds e tarefas

Clique na guia Feeds para ver os feeds abrangentes que criam esses trabalhos. See [Manage data feeds](df-manage-feeds.md).

### Colunas

Cada tarefa mostra várias colunas fornecendo informações sobre ela. Clique em um cabeçalho de coluna para classificá-lo em ordem crescente. Clique novamente em um cabeçalho de coluna para classificá-lo em ordem decrescente. Se não conseguir ver uma coluna específica, clique no ícone de coluna na parte superior direita.

![Ícone Coluna](assets/job-cols.jpg)

* **ID** do feed: Exibe a ID do feed, um identificador exclusivo. Os trabalhos criados pelo mesmo feed têm a mesma ID do feed.
* **ID** do trabalho: Um identificador exclusivo para a tarefa. Todos os trabalhos têm uma ID de trabalho diferente.
* **Nome** do feed: Coluna obrigatória. Exibe o nome do feed. As tarefas criadas pelo mesmo feed têm o mesmo Nome do feed.
* **Conjunto** de relatórios: O conjunto de relatórios do qual o trabalho faz referência aos dados.
* **ID** do conjunto de relatórios: O identificador exclusivo do conjunto de relatórios.
* **Hora** de início: A hora em que o trabalho começou. A data e a hora são mostradas no fuso horário do conjunto de relatórios com deslocamento GMT. Os feeds diários normalmente começam perto da meia-noite no fuso horário do conjunto de relatórios.
* **Status**: O status do feed.
   * Aguardando dados: A tarefa está operacional e os dados da janela de relatório estão sendo coletados.
   * Processando: A tarefa está criando os arquivos de dados e se preparando para enviá-los.
   * Concluído: A tarefa foi concluída sem problemas.
   * Falha: O trabalho não foi concluído. Consulte [Solução de problemas de trabalhos](jobs-troubleshooting.md) para ajudar a determinar a causa da falha.
   * Aguardando exportação: Os dados da janela de relatórios ainda não foram totalmente processados.
   * Sem dados: Não há dados no conjunto de relatórios para a janela de relatórios solicitada.
* **Hora** de conclusão: A hora em que o trabalho terminou. A data e a hora são mostradas no fuso horário do conjunto de relatórios com deslocamento GMT.
* **Data** Solicitada: A janela de relatório do arquivo. Os feeds diários normalmente mostram de 00:00 às 23:59 com um deslocamento GMT, indicando um dia inteiro com base no fuso horário do conjunto de relatórios. Os feeds por hora mostram a hora individual para a qual o trabalho é feito.
