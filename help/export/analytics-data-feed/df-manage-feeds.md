---
title: Interface do usuário do feed de dados
description: Saiba como navegar na interface do feed de dados.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 68%

---

# Gerenciar feeds de dados

O gerenciador de feed de dados permite criar, editar e excluir feeds de dados para sua organização. Se você tiver permissões para acessar o gerenciador de feed de dados, poderá gerenciar feeds de dados para todos os conjuntos de relatórios visíveis a você.

Veja um vídeo sobre a interface do Gerenciamento de feeds de dados:

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

Acesse o gerenciamento do feed de dados seguindo estas etapas:

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
1. Selecione o ícone de 9 quadrados no canto superior direito e selecione [!UICONTROL **Analytics**].
1. Na barra de navegação superior, vá para [!UICONTROL **Admin**] > [!UICONTROL **Feeds de dados**].

## Navegar na interface

Ao chegar à página do gerenciador do feed de dados, a interface é semelhante ao seguinte:

![Feeds de dados](assets/feeds.png)

Se nenhum feed for configurado, a página exibe um botão [!UICONTROL Criar novo feed de dados].

### Filtros e pesquisa

Use a pesquisa ou os filtros para localizar um feed específico.

* No campo de pesquisa, comece digitando o nome de um feed. Somente os feeds correspondentes são mostrados na lista de feeds disponíveis.

* Na extremidade esquerda, clique no ícone de filtro para mostrar ou ocultar as opções de filtragem. Os filtros são organizados por categoria. É possível recolher ou expandir categorias de filtragem. Marque a caixa de seleção ao lado de qualquer filtro que deseja aplicar.

  ![Filtro](assets/filters.png)

### Feeds e trabalhos

Selecione o [!UICONTROL **Tarefas**] para exibir trabalhos individuais criados por cada um dos feeds. Consulte [Gerenciar trabalhos de feed de dados](df-manage-jobs.md).

### Adicionar

A variável [!UICONTROL Adicionar] permite criar um novo feed. Consulte [Criar um feed de dados](create-feed.md) para obter mais informações.

### Colunas

Cada feed criado mostra várias colunas fornecendo informações sobre ele. Selecione um cabeçalho de coluna para classificá-lo em ordem crescente. Selecione um cabeçalho de coluna novamente para classificá-lo em ordem decrescente. Se não conseguir ver uma coluna específica, clique no ícone de coluna no canto superior direito.

![Ícone de coluna](assets/cols.jpg)

* **Nome do feed**: coluna obrigatória. Exibe o nome do feed.
* **ID do feed**: exibe a ID do feed, um identificador exclusivo.
* **Conjunto de relatórios**: o conjunto de relatórios do qual o feed faz referência aos dados.
* **ID do conjunto de relatórios**: o identificador exclusivo do conjunto de relatórios.
* **Colunas de dados**: quais colunas de dados estão ativas para o feed. Na maioria dos casos, há colunas demais para exibir nesse formato.
* **Intervalo**: indica se o feed é por hora ou por dia.
* **Tipo de destino**: o tipo de destino do feed. Por exemplo, Amazon S3, GCP ou Azure.
* **Host de destino**: o local onde o arquivo é colocado.
* **Proprietário**: a conta do usuário que criou o feed.
* **Status**: o status do feed.
   * Ativo: o feed é operacional.
   * Aprovação pendente: em algumas circunstâncias, um feed requer a aprovação da Adobe antes de começar a gerar trabalhos.
   * Excluído: o feed é excluído.
   * Concluído: o feed terminou de ser processado. Um feed concluído pode ser editado, suspenso ou cancelado.
   * Pendente: o feed é criado, mas ainda não está ativo. Os feeds permanecem nesse estado por um curto período de transição.
   * Inativo: equivalente a um estado &quot;pausado&quot; ou &quot;em espera&quot;. Se um feed de preenchimento retroativo (um feed que processa apenas dados históricos) for reativado, ele retomará a entrega de trabalhos a partir de onde parou. Se um feed ativo for reativado, ele retomará a entrega de trabalhos a partir de onde parou.
* **Última modificação**: a data em que o feed foi modificado pela última vez. A data e a hora são mostradas no fuso horário do conjunto de relatórios com deslocamento GMT.
* **Data de início**: a data do primeiro trabalho para este feed. A data e a hora são mostradas no fuso horário do conjunto de relatórios com deslocamento GMT.
* **Data final**: a data do último trabalho para este feed. Os feeds de dados em andamento não têm uma data de término.

## Ações do feed de dados

Clique na caixa de seleção ao lado de um feed de dados para revelar as ações disponíveis.

* **Histórico de tarefas**: exibir todos os trabalhos vinculados a esses feeds de dados. Direciona automaticamente para a [interface de gerenciamento de trabalhos](df-manage-jobs.md).
* **Excluir**: exclui o feed de dados, definindo o status como [!UICONTROL Excluído].
* **Copiar**: é necessário [criar um novo feed](create-feed.md) com todas as configurações do feed atual. Não é possível copiar um feed de dados se mais de um estiver selecionado.
* **Pausar**: interrompe o processamento do feed, definindo seu status como [!UICONTROL Inativo].
* **Ativar**: disponível somente para feeds inativos. Os feeds de preenchimento retroativo (feeds que processam apenas dados históricos) retomam o processamento de dados de onde pararam, preenchendo retroativamente qualquer data, se necessário. Os feeds em tempo real retomam o processamento dos dados a partir da hora atual.
