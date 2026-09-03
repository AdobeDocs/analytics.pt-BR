---
description: Saiba mais sobre as descrições de campo para o Gerenciador de tarefas agendadas.
title: Sobre o Gerenciador de tarefas agendadas
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
TQID: https://experienceleague.adobe.com/bH-sAinp0Hf0X9qesfrJMIUYdDqjrev5Hd7mRpihDLM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 788
ht-degree: 25%

---

# Gerenciador de tarefa agendada

{{legacy-arb}}

O [!UICONTROL Gerenciador de Tarefas Agendadas] permite ver uma lista de relatórios agendados existentes, juntamente com seus destinatários, detalhes de agendamento e formatos de arquivo. Também permite reativar pastas de trabalho agendadas que falharam na execução.

## Pausa de tarefas agendadas mais antigas

Em 21 de abril de 2022, lançamos alterações em tarefas agendadas do Report Builder como parte de nossos esforços de otimização de desempenho e entrega. Essas alterações incluíam a remoção da capacidade de programar entregas “terminadas após x ocorrências”. Em resposta a várias solicitações de clientes que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de maneira limitada até **31 de janeiro de 2023**.

Você continuará a poder agendar tarefas do Report Builder por hora e encerrá-las após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; a opção “terminar após x ocorrências” permanecerá indisponível para todos os outros intervalos de entrega (diário, semanal, mensal e anual).

Observe que essa opção foi removida em 31 de janeiro de 2023.
Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe.

Esta pausa se aplica especificamente a **qualquer tarefa criada antes de 31 de janeiro de 2020**. Nenhuma tarefa, pasta de trabalho ou dados serão excluídos. As tarefas com mais de dois anos serão pausadas e nenhuma tarefa agendada adicional será enviada.

Todas as tarefas que deseja retomar o envio podem ser reativadas. Faça logon no Report Builder e inicie o [!UICONTROL Gerenciador de tarefas agendadas]. Clique em **[!UICONTROL Reativar]** para a tarefa agendada que você deseja retomar o envio. Qualquer tarefa reativada terá uma expiração padrão de 18 meses, a menos que uma data de expiração mais curta seja escolhida.

Além disso, qualquer tarefa com uma data de criação inferior a dois anos e sem data de expiração atual (ou com uma data de expiração superior a dois anos) terá uma data de expiração padrão de 18 meses aplicada a ela. A nova data de expiração será segunda-feira, 15 de outubro de 2023. É possível editar essa data de expiração para que seja menor que 18 meses, mas não maior. No momento da expiração, a tarefa será pausada. No entanto, é possível reativar a tarefa com uma nova data de expiração de 18 meses. Nenhuma tarefa, pasta de trabalho ou dados serão excluídos.

A finalidade dessa pausa é gerenciar e manter com eficiência nosso banco de dados de tarefas agendadas para garantir o desempenho e o delivery ideais para tarefas e pastas de trabalho necessárias. Isto servirá como nossa nova política de governança daqui em diante. Depois de 31 de janeiro de 2023, todas as tarefas terão uma data de expiração máxima de 18 meses. Após 18 meses, as tarefas expiradas serão pausadas e poderão ser reativadas conforme necessário.

## Configurar tarefas agendadas

| Campo | Descrição |
| --- | --- |
| **[!UICONTROL Guia Relatórios agendados]** | |
| [!UICONTROL Nome do Relatório] | Indica o nome da tarefa agendada. |
| [!UICONTROL Email/FTP] | O endereço de email ou FTP do recipient. **Observação:** se o email estiver selecionado, os relatórios com mais de 1 MB serão anexados automaticamente ao email como um arquivo .zip. Este recurso ajuda a manter o tamanho pequeno dos arquivos anexados e não pode ser desativado |
| [!UICONTROL Opções de Publicação] | Esta coluna listará o Power BI se uma das [opções de publicação do Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) estiver selecionada. |
| [!UICONTROL Agendar] | O tipo de delivery agendado. |
| [!UICONTROL Formato de arquivo] | O formato de entrega do relatório, como Excel, PDF, HTML e assim por diante. |
| [!UICONTROL Reativar] | Quando ocorre falha de execução de uma pasta de trabalho agendada, o Report Builder tenta executá-la mais duas vezes a cada quinze minutos. Após três tentativas mal sucedidas, o Report Builder desativa o agendamento e exibe o botão Reativar. Quando você reativa uma pasta de trabalho, o delivery agendado é reiniciado a partir do momento em que ela é desativada.<p>Por exemplo, se uma pasta de trabalho agendada foi desativada há 14 dias e você a reativar hoje, ela será executada para todos os dias que estiverem faltando e será entregue 14 vezes. Se não quiser que a pasta de trabalho seja entregue para os dias que faltam, exclua a pasta de trabalho agendada e crie uma nova pasta de trabalho agendada usando os mesmos parâmetros de agendamento.<p>**Observação:** não reative uma pasta de trabalho, a menos que você saiba o motivo da desativação pelo sistema. Para solucionar problemas, baixe uma pasta de trabalho desativada e atualize-a no lado do cliente. Se não houver erros, você poderá reativá-lo. |
| [!UICONTROL Último envio] | A data e a hora em que o relatório foi enviado pela última vez. |
| **Guia Destinatário** | |
| [!UICONTROL Email de destinatário] | O destinatário do email do relatório. |
| [!UICONTROL Relatórios] | Os relatórios enviados para cada recipient. |
| **Guia Histórico de Relatórios** | |
| [!UICONTROL Nome do arquivo] | Indica o nome da tarefa agendada. |
| [!UICONTROL Data] | A data e a hora em que o relatório foi enviado pela última vez. |
| [!UICONTROL Status] | O status indica se o relatório foi enviado ou não foi enviado. |
| [!UICONTROL Email/FTP] | O endereço de email ou FTP do recipient do relatório. |
| [!UICONTROL Formato de arquivo] | O formato de entrega do relatório, como Excel, PDF, HTML e assim por diante. |
