---
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Gerenciador de Atividades de relatórios
feature: Admin Tools
hide: true
hidefromtoc: true
source-git-commit: 6ab2f39bdfc3a50c2b91f020c98b0e81da8b2b8e
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 3%

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
| **[!UICONTROL Conjunto de relatórios]** | O conjunto de relatórios base |
| **[!UICONTROL Conjunto de relatórios virtuais]** | Todos os conjuntos de relatórios virtuais que são alimentados neste conjunto de relatórios base. Os conjuntos de relatórios virtuais adicionam complexidade às solicitações de relatórios devido a níveis adicionais de filtragem e segmentação aplicadas. Todas as solicitações provenientes dos conjuntos de relatórios virtuais são combinadas e desistem para o conjunto de relatórios base.<p>Se você tiver 10 solicitações provenientes de 5 VRSs, serão 50 solicitações no conjunto de relatórios base. Dessa forma, você pode atingir rapidamente a capacidade. |
| **[!UICONTROL Capacidade de uso]** | Em relação à porcentagem, quanto da capacidade de relatórios do conjunto de relatórios está sendo usada, em tempo real. |
| **[!UICONTROL Status]** | Quatro indicadores de status possíveis: <ul><li>**Vermelho - Capacidade**: O conjunto de relatórios é maximizado em termos de capacidade de relatório.</li><li>**Amarelo - Capacidade de borbulhamento**: Este conjunto de relatórios corre o risco de atingir sua capacidade máxima.</li><li>**Verde - Disponível**: Há muita capacidade de gerar relatórios.</li><li>**Cinza - Indisponível**: O conjunto de relatórios não está configurado para capacidade de relatório.</li></ul> |

Atualize a página para alterar os resultados.

## Filtrar conjuntos de relatórios

É possível filtrar os conjuntos de relatórios por