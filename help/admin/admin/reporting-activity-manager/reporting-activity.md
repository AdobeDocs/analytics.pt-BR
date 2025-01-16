---
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Gerenciador de Atividades de relatórios
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 75d8705170169a0ef9f1ee59b12e4bb2c3afac7a
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 14%

---

# Exibir atividade de relatórios no Gerenciador de atividades de relatórios

O [!UICONTROL Gerenciador de Atividades de Relatórios] permite que os administradores diagnostiquem e corrijam rapidamente problemas de capacidade de relatórios durante os horários de pico de relatórios.

Para obter mais informações sobre o Gerenciador de Atividades de relatórios, incluindo os principais benefícios e requisitos de permissão, consulte [Visão geral do Gerenciador de Atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Exibir atividade de relatórios para todos os conjuntos de relatórios {#view-all-report-suites}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_reportingactivitymanager_connections"
>title="Conexões"
>abstract="Esta tabela mostra as conexões para as quais você tem direitos de gerenciar a atividade de relatórios. As informações sobre cada conexão estão disponíveis em cada coluna da tabela."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_reportingactivitymanager_connections"
>title="Conexões"
>abstract="Esta tabela mostra as conexões para as quais você tem direitos de gerenciar a atividade de relatórios. As informações sobre cada conexão estão disponíveis em cada coluna da tabela."

<!-- markdownlint-enable MD034 -->

1. No Adobe Analytics, vá para **[!UICONTROL Admin]** > **[!UICONTROL Gerente de Atividades de Relatórios]**.

   Uma lista de seus conjuntos de relatórios base ativados é exibida.

   ![fila de relatórios](assets/reporting-activity1.png)

1. (Opcional) Você pode pesquisar ou filtrar a lista de conjuntos de relatórios:

   * Use o campo de pesquisa para pesquisar um conjunto de relatórios específico. Comece digitando o nome ou a ID do conjunto de relatórios e a lista de atualizações dos conjuntos de relatórios à medida que você digita.

   * Selecione o ícone [!UICONTROL **Filtro**] ![Ícone Filtro](assets/filter-icon.png) para expandir a lista de opções de filtro. Você pode filtrar por [!UICONTROL **Favoritos**] ou [!UICONTROL **Status**].

     Para marcar um conjunto de relatórios como favorito, selecione o ícone de estrela à esquerda do nome do conjunto de relatórios.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Exibir informações de utilização sobre cada conjunto de relatórios. Os dados mostrados na tabela representam a atividade de relatório do conjunto de relatórios no momento em que a página foi carregada pela última vez.

   As seguintes colunas estão disponíveis:

   | Elemento da interface | Descrição |
   | --- | --- |
   | **[!UICONTROL Conjunto de relatórios]** | O conjunto de relatórios base cuja atividade de relatório você está monitorando. |
   | **[!UICONTROL Conjuntos de relatórios virtuais]** | Mostra todos os conjuntos de relatórios virtuais que são alimentados para esse conjunto de relatórios base. Os conjuntos de relatórios virtuais adicionam complexidade às solicitações de relatórios devido a níveis adicionais de filtragem e segmentação aplicadas. Todas as solicitações provenientes dos conjuntos de relatórios virtuais são combinadas no conjunto de relatório base. |
   | **[!UICONTROL Utilização da capacidade]** | A porcentagem da capacidade de relatório do conjunto de relatórios que está sendo usada, em tempo real. <p>**Observação** Uma capacidade de uso de 100% não necessariamente sugere que você deve começar a cancelar imediatamente as solicitações de relatórios. A capacidade de uso de 100% pode estar íntegra se o tempo médio de espera for razoável. Por outro lado, a capacidade de uso de 100% pode sugerir um problema se o número de solicitações em fila também estiver crescendo.</p> |
   | **[!UICONTROL Solicitações na fila]** | O número de solicitações aguardando para serem processadas. <!-- ??? --> |
   | **[!UICONTROL Tempo de espera da fila]** | O tempo médio de espera antes do início do processamento das solicitações. <!-- ???? --> |
   | **[!UICONTROL Status]** | Os status possíveis são: <ul><li>[!UICONTROL **Ativo**] (azul): os relatórios foram executados no conjunto de relatórios nas últimas 2 horas. Os dados mostrados na tabela representam a capacidade de relatório do conjunto de relatórios no momento em que a página foi carregada pela última vez.</li><li>[!UICONTROL **Inativo**] (cinza): nenhum relatório foi executado no conjunto de relatórios nas últimas 2 horas, portanto, nenhum dado foi exibido para o conjunto de relatórios.</li></ul> |

   {style="table-layout:auto"}

## Exibir atividade de relatórios para um único conjunto de relatórios

1. No Adobe Analytics, selecione [!UICONTROL **Administrador**] > [!UICONTROL **Gerente de Atividades de Relatórios**].

1. Selecione o título vinculado do conjunto de relatórios para o qual deseja exibir detalhes.

   Os dados da atividade de relatórios são exibidos para o conjunto de relatórios selecionado.

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. (Opcional) Quando uma conexão é carregada pela primeira vez no Gerenciador de atividades de relatórios, os dados exibidos representam as métricas de utilização atuais. Para ver as métricas atualizadas após o carregamento inicial, clique no botão [!UICONTROL **Atualizar**] para atualizar manualmente a página.

1. Use os gráficos e tabelas disponíveis para entender a atividade de relatórios no conjunto de relatórios.

   * [Visualizar gráficos](#view-graphs)

   * [Exibir tabela](#view-table)

### Visualizar gráficos

Os gráficos a seguir estão disponíveis para ajudá-lo a entender melhor a atividade que está acontecendo no conjunto de relatórios.

Se os gráficos não estiverem visíveis, selecione o botão [!UICONTROL **Mostrar gráficos**].

#### Gráfico de utilização {#utilization}

O gráfico Utilização mostra a utilização de relatórios do conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para ver os pontos no tempo em que a porcentagem de capacidade de uso foi mais alta naquele minuto.

* **Eixo X**: a capacidade de uso dos relatórios nas últimas 2 horas.
* **Eixo Y**: a porcentagem da capacidade de uso do relatório por minuto.

  ![gráfico de utilização](assets/utilization-graph.png)

#### Gráfico de usuários distintos

O gráfico Usuários distintos mostra a atividade de relatórios do conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para visualizar os pontos no tempo em que o número máximo de usuários foi mais alto naquele minuto.

* **Eixo X**: a atividade de relatório no último intervalo de tempo de 2 horas.
* **Eixo Y**: o número de usuários que fizeram solicitações de relatórios, por minuto.

  ![Gráfico de usuários distintos](assets/distinct-users-graph.png)

#### Gráfico de solicitações

O gráfico Solicitações mostra o número de solicitações processadas e em fila para o conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para visualizar os pontos no tempo em que o número máximo de solicitações foi mais alto naquele minuto.

* **Eixo X**: o número de solicitações processadas e concluídas durante o último período de 2 horas.
* **Eixo Y**: o número de solicitações processadas (em verde) e solicitações enfileiradas (em roxo), por minuto.

  ![Gráfico de usuários distintos](assets/requests-graph.png)

#### Gráfico de enfileiramento

O gráfico Enfileiramento mostra o tempo médio de espera na fila (em segundos) para as solicitações de relatório do conjunto de relatórios selecionado nas últimas 2 horas.

Passe o mouse sobre o gráfico para exibir os pontos no tempo em que o tempo médio máximo de espera foi mais alto para esse minuto.

* **Eixo X**: o tempo médio de espera de fila para solicitações de relatórios durante o último período de 2 horas.
* **Eixo Y**: o tempo médio de espera (em segundos).

  ![Gráfico de usuários distintos](assets/queueing-graph.png)

### Exibir tabela {#view-table}

Ao exibir a tabela, considere o seguinte:

* Você pode optar por exibir dados escolhendo qualquer uma das seguintes guias na parte superior da tabela de dados: [!UICONTROL **Solicitação**], [!UICONTROL **Usuário**], [!UICONTROL **Projeto**] ou [!UICONTROL **Aplicativo**].

* Você pode pesquisar ou filtrar a lista de conexões:

   * Use o campo de pesquisa para procurar uma conexão específica. Comece a digitar o nome ou ID da conexão e a lista de conexões será atualizada conforme você digitar.

   * Selecione o ícone [!UICONTROL **Filtro**] ![Ícone Filtro](assets/filter-icon.png) para expandir a lista de opções de filtro. Você pode filtrar por [!UICONTROL **Status**], [!UICONTROL **Complexidade**], [!UICONTROL **Aplicativo**], [!UICONTROL **Usuário**] ou [!UICONTROL **Projeto**].

   * Você pode selecionar [!UICONTROL **Ocultar gráficos**] para mostrar apenas a tabela.

![guias de tabela](assets/report-activity-tabs.png)

#### Exibir dados por solicitação

Ao selecionar a guia [!UICONTROL **Solicitação**], as seguintes colunas ficam disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **ID da Solicitação**] | Um identificador exclusivo que pode ser usado para fins de solução de problemas. Para copiar a ID, selecione a solicitação e a opção [!UICONTROL **Copiar IDs de solicitação**]. |
| [!UICONTROL **Tempo de execução**] | Por quanto tempo a solicitação está em execução. |
| [!UICONTROL **Hora de início**] | Quando a solicitação iniciou o processamento (com base no horário local do administrador). |
| [!UICONTROL **Tempo de espera**] | Por quanto tempo a solicitação está aguardando antes de ser processada. Esse valor geralmente está em &quot;0&quot; quando há capacidade suficiente. |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 1.4 ou 2.0</li><li>Alertas</li><li>Compartilhar com qualquer pessoa através de links</li><li>Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics</li></ul> |
| [!UICONTROL **Usuário**] | O usuário que iniciou a solicitação. <p>**Observação:** se o valor desta coluna for [!UICONTROL **Não reconhecido**], significa que o usuário está em uma empresa de logon onde você não tem permissões administrativas.</p> |
| [!UICONTROL **Projeto**] | Nomes de projeto salvos do Espaço de trabalho, IDs de relatório da API etc. (Os metadados podem variar em vários aplicativos.) |
| [!UICONTROL **Status**] | Indicadores de status: <ul><li>**Em execução**: a solicitação está sendo atualmente processada.</li><li>**Pendente**: a solicitação está aguardando para ser processada.</li></ul> |
| [!UICONTROL **Complexidade**] | Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação. <p>Os valores possíveis incluem:</p> <ul><li>[!UICONTROL **Baixo**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **Alta**]</li></ul>Esse valor é influenciado pelos valores nas seguintes colunas:<ul><li>[!UICONTROL **Limites de mês**]</li><li>[!UICONTROL **Colunas**]</li><li>[!UICONTROL **Segmentos**]</li></ul> |
| [!UICONTROL **Limites de mês**] | O número de meses incluídos em uma solicitação. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Colunas**] | O número de métricas e divisões na solicitação. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Segmentos**] | O número de segmentos aplicados à solicitação. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por usuário

Ao selecionar a guia [!UICONTROL **Usuário**], as seguintes colunas ficam disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Usuário**] | O usuário que iniciou a solicitação. Se o valor desta coluna for [!UICONTROL **Não reconhecido**], significa que o usuário está em uma empresa de logon onde você não tem permissões administrativas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações iniciadas pelo usuário. |
| [!UICONTROL **Número de projetos**] | O número de projetos associados ao usuário. <!-- ??? --> |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 1.4 ou 2.0</li><li>Alertas</li><li>Compartilhar com qualquer pessoa através de links</li><li>Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics</li></ul> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações iniciadas pelo usuário. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p><ul><li>[!UICONTROL **Limites médios de mês**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Limites médios de mês**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por projeto

Quando você seleciona a guia [!UICONTROL **Projeto**], as seguintes colunas ficam disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Projeto**] | O projeto em que as solicitações foram iniciadas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações associadas ao projeto. |
| [!UICONTROL **Número de usuários**] | O número de usuários associados ao projeto. <!-- ??? --> |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 1.4 ou 2.0</li><li>Alertas</li><li>Compartilhar com qualquer pessoa através de links</li><li>Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics</li></ul> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações incluídas no projeto. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p><ul><li>[!UICONTROL **Limites médios de mês**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Limites médios de mês**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por aplicativo

Ao selecionar a guia [!UICONTROL **Aplicativo**], as seguintes colunas ficam disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Aplicativo**] | O aplicativo em que as solicitações foram iniciadas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações associadas ao aplicativo. |
| [!UICONTROL **Número de usuários**] | O número de usuários associados ao aplicativo. <!--???--> |
| [!UICONTROL **Número de projetos**] | O número de projetos associados ao aplicativo. <!--???--> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações associadas ao aplicativo. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:<ul><li>[!UICONTROL **Média de Limites de Mês**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Limites médios de mês**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

<!--

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
|  |  |

{style="table-layout:auto"}

-->