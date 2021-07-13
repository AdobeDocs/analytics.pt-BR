---
description: Descrições dos campos para o Gerenciador de tarefas agendadas.
title: Gerenciador de tarefa agendada
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 97%

---

# Gerenciador de tarefa agendada

O Gerenciador de tarefas agendadas permite que você visualize uma lista de relatórios agendados existentes, juntamente com seus destinatários, detalhes do agendamento e formatos de arquivo. Ele também permite a reativação de pastas de trabalho agendadas que não foram executadas.

| Campo | Descrição |
| --- | --- |
| Guia **Relatórios agendados** |  |
| Nome do relatório | Indica o nome da tarefa agendada. |
| Email/FTP | O endereço de email ou do FTP do destinatário. **Observação:** se o email estiver selecionado, os relatórios com mais de 1 MB são anexados automaticamente ao email como um arquivo .zip. Este recurso ajuda a manter o tamanho pequeno dos arquivos anexados e não pode ser desativado |
| Opções de publicação | Essa coluna listará o Power BI se uma das [opções de publicação do Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) estiver selecionada. |
| Agendar | O tipo de entrega agendado. |
| Formato do arquivo | O formato de entrega do relatório, como Excel, PDF, HTML, etc. |
| Reativar | Quando ocorre falha de execução de uma pasta de trabalho agendada, o Report Builder tenta executá-la mais duas vezes a cada quinze minutos. Depois de três tentativas mal sucedidas, o Report Builder desativa o agendamento e exibe o botão Reativar. Quando você reativa uma pasta de trabalho, a entrega agendada é reiniciada a partir do momento em que foi desativada.  Por exemplo, se uma pasta de trabalho agendada foi desativada há 14 dias e você a reativar hoje, ela será executada para todos os dias que estiverem faltando e será entregue 14 vezes. Se não quiser que a pasta de trabalho seja entregue para os dias que estiverem faltando, você poderá excluir a pasta de trabalho agendada e, em seguida, criar uma nova pasta de trabalho agendada usando os mesmos parâmetros de agendamento.   Observação: você não deve reativar uma pasta de trabalho, a menos que saiba o motivo de o sistema tê-la desativado. Uma solução para o problema é baixar uma pasta de trabalho desativada e atualizá-la no lado do cliente. Se não encontrar nenhum erro, você deve conseguir reativá-la. |
| Último envio | A data e a hora quando o relatório foi enviado pela última vez. |
| Guia **Destinatário** |  |
| Email do destinatário | O destinatário do email do relatório. |
| Relatórios | Os relatórios que são enviados a cada destinatário. |
| Guia **Histórico de relatórios** |  |
| Nome do arquivo | Indica o nome da tarefa agendada. |
| Data | A data e a hora quando o relatório foi enviado pela última vez. |
| Status | O status indica se o relatório foi enviado ou não. |
| Email/FTP | O endereço de email ou FTP do destinatário do relatório. |
| Formato do arquivo | O formato de entrega do relatório, como Excel, PDF, HTML, etc. |
