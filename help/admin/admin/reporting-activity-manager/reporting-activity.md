---
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Gerenciador de Atividades de relatórios
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 02273690b98ca456862194e814ff2c72f87d7b41
workflow-type: tm+mt
source-wordcount: '1761'
ht-degree: 18%

---

# Exibir atividade de relatórios no Gerenciador de atividades de relatórios

{{release-limited-testing}}

A variável [!UICONTROL Gerenciador de atividades de relatórios] O permite que os administradores diagnostiquem e corrijam rapidamente os problemas de capacidade dos relatórios durante o pico dos relatórios.

Para obter mais informações sobre o Gerente de atividades de relatórios, incluindo os principais benefícios e requisitos de permissão, consulte [Visão geral do Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Exibir atividade de relatórios para todos os conjuntos de relatórios {#view-all-report-suites}

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

   Uma lista de seus conjuntos de relatórios base ativados é exibida.

   ![fila de relatórios](/help/admin/admin/assets/reporting-activity1.png)

1. (Opcional) Você pode pesquisar ou filtrar a lista de conjuntos de relatórios:

   * Use o campo de pesquisa para pesquisar um conjunto de relatórios específico. Comece digitando o nome ou a ID do conjunto de relatórios e a lista de atualizações dos conjuntos de relatórios à medida que você digita.

   * Selecione o [!UICONTROL **Filtro**] ícone ![Ícone Filtrar](assets/filter-icon.png) para expandir a lista de opções de filtro. Você pode filtrar por [!UICONTROL **Favoritos**] ou [!UICONTROL **Status**].

     Para marcar um conjunto de relatórios como favorito, selecione o ícone de estrela à esquerda do nome do conjunto de relatórios.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Exibir informações de utilização sobre cada conjunto de relatórios. Você pode selecionar um cabeçalho de coluna para classificar a tabela por essa coluna.

   As seguintes colunas estão disponíveis:

   | Elemento da interface | Descrição |
   | --- | --- |
   | **[!UICONTROL Conjunto de relatórios]** | O conjunto de relatórios base cuja atividade de relatório você está monitorando. |
   | **[!UICONTROL Conjuntos de relatórios virtuais]** | Mostra todos os conjuntos de relatórios virtuais que são alimentados para esse conjunto de relatórios base. Os conjuntos de relatórios virtuais adicionam complexidade às solicitações de relatórios devido a níveis adicionais de filtragem e segmentação aplicadas. Todas as solicitações provenientes dos conjuntos de relatórios virtuais são combinadas no conjunto de relatório base.<p>Por exemplo, se você tiver 10 solicitações provenientes de 5 conjuntos de relatórios virtuais, são 50 solicitações no conjunto de relatórios base. Dessa forma, você pode atingir rapidamente a capacidade. |
   | **[!UICONTROL Utilização da capacidade]** | A porcentagem da capacidade de relatório do conjunto de relatórios que está sendo usada, em tempo real. <p>**Nota** Uma capacidade de uso de 100% não necessariamente sugere que você deve começar a cancelar imediatamente as solicitações de relatórios. A capacidade de uso de 100% pode estar íntegra se o tempo médio de espera for razoável. Por outro lado, a capacidade de uso de 100% pode sugerir um problema se o número de solicitações em fila também estiver crescendo.</p> |
   | **[!UICONTROL Solicitações na fila]** | O número de solicitações aguardando para serem processadas. <!-- ??? --> |
   | **[!UICONTROL Tempo de espera na fila]** | O tempo médio de espera antes do início do processamento das solicitações. <!-- ???? --> |
   | **[!UICONTROL Status]** | Os status possíveis são: <ul><li>[!UICONTROL **Ativo**] (azul): os relatórios foram executados no conjunto de relatórios e a atividade dele está sendo monitorada.</li><li>[!UICONTROL **Inativo**] (cinza): nenhum relatório foi executado no conjunto de relatórios. Esse status é exibido somente quando os conjuntos de relatórios são criados pela primeira vez.</li></ul> |

   {style="table-layout:auto"}

## Exibir atividade de relatórios para um único conjunto de relatórios

1. No Adobe Analytics, selecione [!UICONTROL **Admin**] > [!UICONTROL **Gerenciador de atividades de relatórios**].

1. Selecione o título vinculado do conjunto de relatórios para o qual deseja exibir detalhes.

   Os dados da atividade de relatórios são exibidos para o conjunto de relatórios selecionado.

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. Use os gráficos e tabelas disponíveis para entender a atividade de relatórios no conjunto de relatórios.

   * [Visualizar gráficos](#view-graphs)

   * [Exibir tabela](#view-table)

### Visualizar gráficos

Os gráficos a seguir estão disponíveis para ajudá-lo a entender melhor a atividade que está acontecendo no conjunto de relatórios.

Se os gráficos não estiverem visíveis, selecione a variável [!UICONTROL **Mostrar gráficos**] botão.

#### Gráfico de utilização {#utilization}

O gráfico Utilização mostra a utilização de relatórios do conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para ver os pontos no tempo em que a porcentagem de capacidade de uso foi mais alta naquele minuto.

* **Eixo X**: a capacidade de uso de relatórios nas últimas 2 horas.
* **Eixo Y**: a porcentagem da capacidade de uso do relatório, por minuto.

  ![gráfico de utilização](assets/utilization-graph.png)

#### Gráfico de usuários distintos

O gráfico Usuários distintos mostra a atividade de relatórios do conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para visualizar os pontos no tempo em que o número máximo de usuários foi mais alto naquele minuto.

* **Eixo X**: a atividade de relatórios no período das últimas 2 horas.
* **Eixo Y**: o número de usuários que fizeram solicitações de relatórios, por minuto.

  ![Gráfico de usuários distintos](assets/distinct-users-graph.png)

#### Gráfico de solicitações

O gráfico Solicitações mostra o número de solicitações processadas e concluídas do conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para visualizar os pontos no tempo em que o número máximo de solicitações foi mais alto naquele minuto.

* **Eixo X**: o número de solicitações processadas e concluídas no último intervalo de tempo de 2 horas.
* **Eixo Y**: o número de solicitações processadas (em roxo) e solicitações concluídas (em verde), por minuto.

  ![Gráfico de usuários distintos](assets/requests-graph.png)

#### Gráfico de enfileiramento

O gráfico Enfileiramento mostra o tempo médio de espera na fila (em segundos) para as solicitações de relatório do conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para exibir os pontos no tempo em que o tempo médio máximo de espera foi mais alto para esse minuto.

* **Eixo X**: o tempo médio de espera da fila para solicitações de relatórios nos últimos 2 horas.
* **Eixo Y**: o tempo médio de espera (em segundos).

  ![Gráfico de usuários distintos](assets/queueing-graph.png)

### Exibir tabela {#view-table}

Você pode optar por exibir dados escolhendo qualquer uma das seguintes tabs na parte superior da tabela de dados: [!UICONTROL **Solicitação**], [!UICONTROL **Usuário**], [!UICONTROL **Projeto**] ou [!UICONTROL **Aplicativo**].

>[!TIP]
>
>É possível selecionar [!UICONTROL **Ocultar gráficos**] para mostrar somente a tabela.

![guias de tabela](assets/indiv-report-ste-table-tabs.png)

#### Exibir dados por solicitação

Ao selecionar a variável [!UICONTROL **Solicitação**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **ID da solicitação**] | Pode ser usado para fins de solução de problemas. |
| [!UICONTROL **Tempo de execução**] | Por quanto tempo a solicitação está em execução. |
| [!UICONTROL **Hora de início**] | Quando a solicitação iniciou o processamento (com base no horário local do administrador). |
| [!UICONTROL **Tempo de espera**] | Por quanto tempo a solicitação está aguardando antes de ser processada. Esse valor geralmente está em &quot;0&quot; quando há capacidade suficiente. |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 1.4 ou 2.0</li><li>Alertas inteligentes</li></ul> |
| [!UICONTROL **Usuário**] | O usuário que iniciou a solicitação. <p>**Nota:** Se o valor dessa coluna for [!UICONTROL **Não reconhecido**], isso significa que o usuário está em uma empresa de logon na qual você não tem permissões administrativas.</p> |
| [!UICONTROL **Projeto**] | Nomes de projeto salvos do Espaço de trabalho, IDs de relatório da API etc. (Os metadados podem variar em vários aplicativos.) |
| [!UICONTROL **Status**] | Indicadores de status: <ul><li>**Em execução**: a solicitação está sendo atualmente processada.</li><li>**Pendente**: a solicitação está aguardando para ser processada.</li></ul> |
| [!UICONTROL **Complexidade**] | Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação. <p>Os valores possíveis incluem:</p> <ul><li>[!UICONTROL **Baixa**]</li><li>[!UICONTROL **Médio**]</li><li>[!UICONTROL **Alta**]</li></ul>Esse valor é influenciado pelos valores nas seguintes colunas:<ul><li>[!UICONTROL **Limites do mês**]</li><li>[!UICONTROL **Colunas**]</li><li>[!UICONTROL **Segmentos**]</li></ul> |
| [!UICONTROL **Limites do mês**] | O número de meses incluídos em uma solicitação. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Colunas**] | O número de métricas e divisões na solicitação. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Segmentos**] | O número de segmentos aplicados à solicitação. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por usuário

Ao selecionar a variável [!UICONTROL **Usuário**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Usuário**] | O usuário que iniciou a solicitação. Se o valor dessa coluna for [!UICONTROL **Não reconhecido**], isso significa que o usuário está em uma empresa de logon na qual você não tem permissões administrativas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações iniciadas pelo usuário. |
| [!UICONTROL **Número de projetos**] | O número de projetos associados ao usuário. <!-- ??? --> |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 1.4 ou 2.0</li><li>Alertas inteligentes</li></ul> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações iniciadas pelo usuário. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p><ul><li>[!UICONTROL **Média de limites mensais**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Média de limites mensais**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por projeto

Ao selecionar a variável [!UICONTROL **Projeto**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Projeto**] | O projeto em que as solicitações foram iniciadas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações associadas ao projeto. |
| [!UICONTROL **Número de usuários**] | O número de usuários associados ao projeto. <!-- ??? --> |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 1.4 ou 2.0</li><li>Alertas inteligentes</li></ul> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações incluídas no projeto. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p><ul><li>[!UICONTROL **Média de limites mensais**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Média de limites mensais**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por aplicativo

Ao selecionar a variável [!UICONTROL **Aplicativo**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Aplicativo**] | O aplicativo em que as solicitações foram iniciadas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações associadas ao aplicativo. |
| [!UICONTROL **Número de usuários**] | O número de usuários associados ao aplicativo. <!--???--> |
| [!UICONTROL **Número de projetos**] | O número de projetos associados ao aplicativo. <!--???--> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações associadas ao aplicativo. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:<ul><li>[!UICONTROL **Média de limites mensais**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Média de limites mensais**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}


