---
description: Saiba mais sobre as descrições de campo para o Gerenciador de tarefas agendadas.
title: Sobre o Gerenciador de tarefas agendadas
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 42%

---

# Gerenciador de tarefa agendada

{{legacy-arb}}

O [!UICONTROL Gerenciador de Tarefas Agendadas] permite ver uma lista de relatórios agendados existentes, juntamente com seus destinatários, detalhes de agendamento e formatos de arquivo. Ele também permite a reativação de pastas de trabalho agendadas que não foram executadas.

## Pausa de tarefas agendadas mais antigas

Em 21 de abril de 2022, lançamos alterações em tarefas agendadas do Report Builder como parte de nossos esforços de otimização de desempenho e entrega. Essas alterações incluíam a remoção da capacidade de programar entregas “terminadas após x ocorrências”. Em resposta a várias solicitações de clientes que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de maneira limitada até **31 de janeiro de 2023**.

Você continuará a poder agendar tarefas de Report Builder por hora e terminá-las após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; a opção &quot;terminar após x ocorrências&quot; permanecerá indisponível para todos os outros intervalos de entrega (diário, semanal, mensal e anual).

Observe que essa opção foi removida em 31 de janeiro de 2023.
Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente do Adobe.

Esta pausa se aplica especificamente a **qualquer tarefa criada antes de 31 de janeiro de 2020**. Nenhuma tarefa, pasta de trabalho ou dados serão excluídos. As tarefas com mais de dois anos serão pausadas e nenhuma tarefa agendada adicional será enviada.

Todas as tarefas que deseja retomar o envio podem ser reativadas. Faça logon no Report Builder e inicie o [!UICONTROL Gerenciador de tarefas agendadas]. Clique em **[!UICONTROL Reativar]** para a tarefa agendada que você deseja retomar o envio. Qualquer tarefa reativada terá uma expiração padrão de 18 meses, a menos que uma data de expiração mais curta seja escolhida.

Além disso, qualquer tarefa com uma data de criação inferior a dois anos e sem data de expiração atual (ou com uma data de expiração superior a dois anos) terá uma data de expiração padrão de 18 meses aplicada a ela. A nova data de expiração será segunda-feira, 15 de outubro de 2023. É possível editar essa data de expiração para que seja menor que 18 meses, mas não maior. No momento da expiração, a tarefa será pausada. No entanto, é possível reativar a tarefa com uma nova data de expiração de 18 meses. Nenhuma tarefa, pasta de trabalho ou dado será excluído.

A finalidade dessa pausa é gerenciar e manter com eficiência nosso banco de dados de tarefas agendadas para garantir o desempenho e o delivery ideais para tarefas e pastas de trabalho necessárias. Isto servirá como nossa nova política de governança daqui em diante. Depois de 31 de janeiro de 2023, todas as tarefas terão uma data de expiração máxima de 18 meses. Após 18 meses, as tarefas expiradas serão pausadas e poderão ser reativadas conforme necessário.

## Configurar tarefas agendadas

| Campo | Descrição |
| --- | --- |
| **[!UICONTROL Guia Relatórios agendados]** | |
| [!UICONTROL Nome do Relatório] | Indica o nome da tarefa agendada. |
| [!UICONTROL Email/FTP] | O endereço de email ou FTP do recipient. **Observação:** se o email estiver selecionado, os relatórios com mais de 1 MB são anexados automaticamente ao email como um arquivo .zip. Este recurso ajuda a manter o tamanho pequeno dos arquivos anexados e não pode ser desativado |
| [!UICONTROL Opções de Publicação] | Esta coluna listará Power BI se uma das [opções de publicação do Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/legacy-report-builder/publish-powerbi/power-bi.html?lang=pt-BR) estiver selecionada. |
| [!UICONTROL Agenda] | O tipo de entrega agendado. |
| [!UICONTROL Formato de arquivo] | O formato de entrega do relatório, como Excel, PDF, HTML, etc. |
| [!UICONTROL Reativar] | Quando ocorre falha de execução de uma pasta de trabalho agendada, o Report Builder tenta executá-la mais duas vezes a cada quinze minutos. Após três tentativas mal sucedidas, o Report Builder desativa o agendamento e exibe o botão Reativar. Quando você reativa uma pasta de trabalho, a entrega agendada é reiniciada a partir do momento em que foi desativada.<p>Por exemplo, se uma pasta de trabalho agendada foi desativada há 14 dias e você a reativar hoje, ela será executada para todos os dias que estiverem faltando e será entregue 14 vezes. Se não quiser que a pasta de trabalho seja entregue para os dias que estiverem faltando, você poderá excluir a pasta de trabalho agendada e, em seguida, criar uma nova pasta de trabalho agendada usando os mesmos parâmetros de agendamento.<p>**Observação:** não reative uma pasta de trabalho, a menos que você saiba o motivo da desativação pelo sistema. Para solucionar problemas, baixe uma pasta de trabalho desativada e atualize-a no lado do cliente. Se não encontrar nenhum erro, você deve conseguir reativá-la. |
| [!UICONTROL Último envio] | A data e a hora quando o relatório foi enviado pela última vez. |
| **Guia Destinatário** | |
| [!UICONTROL Email de destinatário] | O destinatário do email do relatório. |
| [!UICONTROL Relatórios] | Os relatórios enviados para cada recipient. |
| **Guia Histórico de Relatórios** | |
| [!UICONTROL Nome do arquivo] | Indica o nome da tarefa agendada. |
| [!UICONTROL Data] | A data e a hora quando o relatório foi enviado pela última vez. |
| [!UICONTROL Status] | O status indica se o relatório foi enviado ou não. |
| [!UICONTROL Email/FTP] | O endereço de email ou FTP do destinatário do relatório. |
| [!UICONTROL Formato de arquivo] | O formato de entrega do relatório, como Excel, PDF, HTML, etc. |
