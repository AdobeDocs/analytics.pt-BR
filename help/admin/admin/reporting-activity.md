---
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Gerenciador de Atividades de relatórios
feature: Admin Tools
mini-toc-levels: 3
hide: true
hidefromtoc: true
source-git-commit: 123a2131be1a3cb23246e2ba591be645c7025b26
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 7%

---


# Gerenciador de Atividades de relatórios

>[!NOTE]
>
>Essa funcionalidade está atualmente no teste beta.

O Gerente de atividade de relatórios permite visualizar a capacidade de geração de relatórios para cada conjunto de relatórios na organização. Ele oferece a você, como Administrador, visibilidade detalhada do consumo de relatórios e ajuda a diagnosticar e corrigir problemas de capacidade facilmente durante os horários de pico de relatórios. Quando sua organização atinge a capacidade de solicitação de relatórios e apresenta uma degradação no desempenho dos relatórios, você agora tem uma maneira de autodiagnosticar problemas de relatórios sem a intervenção do Atendimento ao cliente do Adobe ou da engenharia. Você pode gerenciar facilmente as filas de relatórios em uma única interface e agir imediatamente &#x200B; &#x200B; para melhorar a experiência dos usuários. Esta ferramenta:

* Informa sobre sua capacidade atual de geração de relatórios em seus conjuntos de relatórios.
* Fornece informações detalhadas de consulta de relatório sobre solicitações de relatórios atuais, estejam na fila e em andamento.
* Permite otimizar a fila de relatórios, priorizando algumas e cancelando outras solicitações de relatórios para liberar capacidade. Em outras palavras, você pode perguntar em tempo real: este relatório é necessário neste momento ou posso anulá-lo a favor de relatórios mais urgentes?

## Acessar o Gerenciador de atividade de relatórios

No Adobe Analytics, os administradores vão para **[!UICONTROL Administrador]** > **[!UICONTROL Gerente de atividade de relatórios]**.

## Exibir a fila de relatórios

Ao abrir a página de visão geral do Gerente de atividade de relatórios , você verá uma lista dos seus conjuntos de relatórios base ativados.

![fila de relatórios](assets/reporting-activity1.png)

| Elemento da interface | Descrição |
| --- | --- |
| **[!UICONTROL Conjunto de relatórios]** | O conjunto de relatórios base cuja atividade de relatório você está monitorando. |
| **[!UICONTROL Conjunto de relatórios virtuais]** | Mostra todos os conjuntos de relatórios virtuais que são alimentados para esse conjunto de relatórios base. Os conjuntos de relatórios virtuais adicionam complexidade às solicitações de relatórios devido a níveis adicionais de filtragem e segmentação aplicadas. Todas as solicitações provenientes dos conjuntos de relatórios virtuais são combinadas e desistem para o conjunto de relatórios base.<p>Por exemplo, se você tiver 10 solicitações provenientes de 5 VRSs, são 50 solicitações no conjunto de relatórios base. Dessa forma, você pode atingir rapidamente a capacidade. |
| **[!UICONTROL Capacidade de uso]** | Em relação à porcentagem, quanto da capacidade de relatórios do conjunto de relatórios está sendo usada, em tempo real. |
| **[!UICONTROL Status]** | Quatro indicadores de status possíveis: <ul><li>**Vermelho - [!UICONTROL Capacidade]**: O conjunto de relatórios é maximizado em termos de capacidade de relatório.</li><li>**Amarelo - [!UICONTROL Capacidade de aprendizado]**: Este conjunto de relatórios corre o risco de atingir sua capacidade máxima.</li><li>**Verde - [!UICONTROL Tudo bem]**: Há muita capacidade de gerar relatórios.</li><li>**[!UICONTROL Status pendente]**: ?</li><li>**Cinza - Indisponível**: O conjunto de relatórios não está configurado para capacidade de relatório.</li></ul> |

### Outras ações da atividade de relatório

* Clique em **[!UICONTROL Atualizar]** na parte superior direita para atualizar os resultados.
* Clique na estrela à esquerda do nome do conjunto de relatórios para marcar este conjunto de relatórios como favorito.
* Verificar **[!UICONTROL Favoritos]** no canto superior esquerdo para mostrar os favoritos.
* Pesquise por conjuntos de relatórios por nome ou por ID na barra de pesquisa.
* Filtre os conjuntos de relatórios por seu status.

## Exibir atividade de relatório para conjuntos de relatórios individuais

Clique no link de título de um conjunto de relatórios para o qual deseja exibir detalhes.

![conjunto de relatórios](assets/indiv-report-ste.png)

### Gráfico de linhas

O gráfico de linhas mostra a atividade de relatório do conjunto de relatórios selecionado nas últimas 2 horas.

* O eixo x mostra os dados de capacidade dos relatórios nas últimas 2 horas.
* O eixo y mostra o tempo médio de espera de uma consulta, em segundos.
* Você pode passar o mouse sobre o gráfico de linha para visualizar os pontos no tempo e o tempo médio de espera desse instante.

   ![detalhe](assets/detail.png)

### Filtro

Você pode filtrar a tabela por Aplicativo (consulte a lista na tabela abaixo), por Usuário e por Projeto.

![filtro](assets/filter.png)

### Números de resumo

![filtro](assets/summary_numbers.png)

Os Números do resumo mostram as seguintes informações:

| Número do resumo | Descrição |
| --- | --- |
| Usuários | Quantos usuários estão enviando solicitações de relatórios para este conjunto de relatórios no momento. |
| Projetos |  |
| Consultas |  |
| Tempo Médio de Espera |  |
| Capacidade de uso | A capacidade de uso atual deste conjunto de relatórios. |

{style=&quot;table-layout:auto&quot;}

### Tabela

A tabela detalhada abaixo mostra

| Coluna | Descrição |
| --- | --- |
| ID da consulta |  |
| Tempo de execução |  |
| Tempo de espera |  |
| Hora inicial |  |
| Aplicativo | Os aplicativos compatíveis com o Gerente de atividade de relatórios são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Workspace</li><li>Report Builder</li><li>IUs do construtor: Segmento, métricas calculadas, anotações, públicos-alvo, etc.</li></ul> |
| Usuário |  |
| Projeto |  |
| Limites do mês |
| Colunas |  |
| Segmentos |  |
| Status |  |

{style=&quot;table-layout:auto&quot;}


