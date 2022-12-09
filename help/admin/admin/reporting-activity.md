---
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Gerenciador de Atividades de relatórios
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 94%

---

# Gerenciador de Atividades de relatórios

>[!NOTE]
>
>Esta funcionalidade está atualmente em teste beta.

O [!UICONTROL Gerente de atividades de relatórios] permite ver a capacidade de gerar relatórios para cada conjunto de relatórios na sua organização. Ele oferece a você, como Administrador, visibilidade detalhada do consumo de relatórios e ajuda a diagnosticar e corrigir problemas de capacidade facilmente durante os horários de pico de relatórios.

Quando sua organização atinge a capacidade de solicitação de relatórios e apresenta uma degradação no desempenho dos relatórios, você agora tem uma maneira de autodiagnosticar problemas de relatórios sem a intervenção do Atendimento ao cliente da Adobe ou da engenharia. Você pode gerenciar facilmente as filas de relatórios em uma única interface e agir imediatamente para melhorar a experiência dos usuários. Esta ferramenta:

* Informa você, em tempo real, sobre sua capacidade atual de geração de relatórios em seus conjuntos de relatórios.
* Fornece informações detalhadas de consulta de relatório sobre solicitações de relatórios atuais, estejam na fila ou em progresso.
* Permite otimizar a fila de relatórios, priorizando algumas e cancelando outras solicitações de relatórios para liberar capacidade. Em outras palavras, você pode perguntar em tempo real: este relatório é necessário neste momento ou posso cancelá-lo em favor de relatórios mais urgentes?

## Acessar o Gerenciador de atividade de relatórios

No Adobe Analytics, os administradores acessam **[!UICONTROL Administrador]** > **[!UICONTROL Gerente de atividade de relatórios]**.

## Permissões

Você precisa da permissão Administrador de produto do Analytics (no Adobe Admin Console) para gerenciar a atividade de relatórios.

![permissão](/help/admin/admin/assets/rep-mgr-permission.png)

## Exibir a fila de relatórios

Ao abrir a página de visão geral do [!UICONTROL Gerente de atividades de relatórios], você verá uma lista dos seus conjuntos de relatórios base ativados.

![fila de relatórios](/help/admin/admin/assets/reporting-activity1.png)

| Elemento da interface | Descrição |
| --- | --- |
| **[!UICONTROL Conjunto de relatórios]** | O conjunto de relatórios base cuja atividade de relatório você está monitorando. |
| **[!UICONTROL Conjunto de relatórios virtuais]** | Mostra todos os conjuntos de relatórios virtuais que são alimentados para esse conjunto de relatórios base. Os conjuntos de relatórios virtuais adicionam complexidade às solicitações de relatórios devido a níveis adicionais de filtragem e segmentação aplicadas. Todas as solicitações provenientes dos conjuntos de relatórios virtuais são combinadas e chegam ao conjunto de relatórios base.<p>Por exemplo, se você tiver 10 solicitações provenientes de 5 VRSs, são 50 solicitações no conjunto de relatórios base. Dessa forma, você pode atingir rapidamente a capacidade. |
| **[!UICONTROL Capacidade de uso]** | Em relação à porcentagem, quanto da capacidade de relatórios do conjunto de relatórios está sendo usada, em tempo real. |
| **[!UICONTROL Status]** | Quatro indicadores de status possíveis: <ul><li>**Vermelho - [!UICONTROL Na capacidade]**: o conjunto de relatórios é maximizado em termos de capacidade de relatório. (100%) </li><li>**Amarelo - [!UICONTROL Próximo da capacidade]**: este conjunto de relatórios corre o risco de atingir sua capacidade máxima. (90% - 99%)</li><li>**Verde - [!UICONTROL Tudo bem]**: há muita capacidade de gerar relatórios. (0% - 89%)</li><li>**Cinza - [!UICONTROL Status pendente/Não ativado]**: capacidade do relatório não disponível.</li></ul> |

{style=&quot;table-layout:auto&quot;}

### Outras ações da atividade de relatório

* Clique em **[!UICONTROL Atualizar]** na parte superior direita para atualizar os resultados.
* Clique na estrela à esquerda do nome do conjunto de relatórios para marcar este conjunto de relatórios como favorito.
* Marque a opção **[!UICONTROL Favoritos]** no canto superior esquerdo para mostrar os favoritos.
* Pesquise por conjuntos de relatórios por nome ou por ID na barra de pesquisa.
* Filtre os conjuntos de relatórios pelo status.

## Exibir atividade de relatórios para conjuntos de relatórios individuais

Clique no link de título de um conjunto de relatórios para o qual deseja exibir detalhes.

![conjunto de relatórios](/help/admin/admin/assets/indiv-report-ste.png)

### Gráfico de linhas

O gráfico de linhas mostra a atividade de relatório do conjunto de relatórios selecionado nas últimas 2 horas.

* O eixo x mostra os dados de capacidade dos relatórios nas últimas 2 horas.
* O eixo y mostra o tempo médio de espera de uma consulta, em segundos.
* Você pode passar o mouse sobre o gráfico de linhas para visualizar os pontos no tempo e o tempo médio de espera nesse instante.

   ![detalhe](/help/admin/admin/assets/detail.png)

### Filtro

Você pode filtrar a tabela por Aplicativo (consulte a lista na tabela abaixo), por Usuário e por Projeto.

![filtro](/help/admin/admin/assets/filter.png)

### Números de resumo

![filtro](/help/admin/admin/assets/summary_numbers.png)

Os Números do resumo mostram as seguintes informações:

| Número do resumo | Descrição |
| --- | --- |
| [!UICONTROL Usuários] | O número de usuários que estão enviando solicitações de relatórios para esse conjunto de relatórios. |
| [!UICONTROL Projetos] | Projetos do Espaço de trabalho, pastas de trabalho do Report Builder etc. |
| [!UICONTROL Consultas] | O número de consultas atualmente em execução. |
| [!UICONTROL Tempo Médio de Espera] | O tempo médio de espera para todas as consultas em execução. |
| [!UICONTROL Capacidade de uso] | A capacidade de uso atual deste conjunto de relatórios. |

{style=&quot;table-layout:auto&quot;}

### Tabela

A tabela detalhada abaixo mostra detalhes sobre o conjunto de relatórios.

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL ID da consulta] | Pode ser usado para fins de solução de problemas. |
| [!UICONTROL Tempo de execução] | Por quanto tempo a consulta está em execução. |
| [!UICONTROL Tempo de espera] | Por quanto tempo a consulta está aguardando antes de ser processada. Geralmente em “0” quando há capacidade suficiente. |
| [!UICONTROL Hora inicial] | Quando a consulta iniciou o processamento (horário local do administrador). |
| [!UICONTROL Aplicativo] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 1.4 ou 2.0</li><li>Alertas inteligentes</li></ul> |
| [!UICONTROL Usuário] | O usuário que iniciou a consulta. |
| [!UICONTROL Projeto] | Nomes de projeto salvos do Espaço de trabalho, IDs de relatório da API etc. (Os metadados podem variar em vários aplicativos.) |
| [!UICONTROL Limites do mês] | Quantos limites mensais uma solicitação ultrapassa. Isso aumenta a complexidade da solicitação. |
| [!UICONTROL Colunas] | O número de métricas e detalhamentos no Espaço de trabalho para medir a complexidade da solicitação. |
| [!UICONTROL Segmentos] | Quantos segmentos são aplicados a essa solicitação. Isso aumenta a complexidade da solicitação. |
| [!UICONTROL Status] | Indicadores de status: <ul><li>**Em execução**: a solicitação está sendo atualmente processada.</li><li>**Pendente**: a solicitação está aguardando para ser processada.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Cancelar solicitações de relatórios

Para cancelar uma solicitação

1. Marque a caixa à esquerda de uma ou mais **[!UICONTROL IDs de consulta]** na tabela e clique em **[!UICONTROL Cancelar solicitações]** na parte inferior.

   Também é possível cancelar solicitações em massa ao exibir detalhes por [!UICONTROL Usuário], [!UICONTROL Projeto] ou [!UICONTROL Aplicativo]. As solicitações subsequentes de um projeto, usuário ou aplicativo que não estavam na fila ou em execução no momento do cancelamento ainda podem aparecer quando a atividade é atualizada.

1. Na janela **[!UICONTROL Cancelar consulta x]** que for exibida, você poderá modificar a mensagem de cancelamento, se necessário.
1. Clique em **[!UICONTROL Continuar]**.

   ![cancel-query](/help/admin/admin/assets/cancel-query.png)

Os usuários do aplicativo no Espaço de trabalho, por exemplo, verão o seguinte aviso aparecer em seus projetos:

![cancel-user-notice](/help/admin/admin/assets/cancel-user-facing.png)

## Perguntas frequentes

| Pergunta | Resposta |
| --- | --- |
| Posso adquirir capacidade adicional para relatórios? | Esse recurso estará disponível em breve. |

{style=&quot;table-layout:auto&quot;}
