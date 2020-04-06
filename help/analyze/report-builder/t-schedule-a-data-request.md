---
description: Você pode agendar relatórios para envio de acordo com a hora e o formato de arquivo definidos.
title: Programar uma solicitação de dados
topic: Report builder
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Programar pastas de trabalho

Você pode programar pastas de trabalho, especificar opções avançadas de entrega, especificar destinatários e visualizar o histórico da programação. As opções avançadas de entrega permitem configurar pastas de trabalho que você deseja enviar em um horário ou em intervalos específicos. Também é possível especificar o formato do arquivo para enviar a pasta de trabalho.

Por exemplo, você pode programar a entrega imediata de pastas de trabalho ou com uma programação recorrente e especificar o formato do arquivo nas [!DNL Advanced Delivery Options]. O limite de tamanho do arquivo de uma pasta de trabalho ser carregada é de 5 MB.

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. (Consulte [Agendamento e distribuição de relatórios](/help/analyze/reports-analytics/scheduling.md) na ajuda do Reports &amp; Analytics).

>[!NOTE] Você precisa ter o Excel 2007 ou o pacote de compatibilidade instalado para programar um relatório. Você pode ter no máximo 10 pastas de trabalho programadas por licença do Report Builder. No entanto, é possível aumentar esse número ao subtrair de outras licenças. Para fazer isso, vá para **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Report Builder Reports]**. Uma pasta de trabalho programada (ou carregada na Biblioteca de pastas de trabalho) e que não foi tocada (atualizada, substituída) em mais de 28 meses, será excluída.

>[!NOTE] A &quot;Hora de entrega&quot;/&quot;Hora do dia&quot; inserida pelo usuário especifica a hora em que a pasta de trabalho deve começar a ser processada, não a hora em que ela será realmente entregue. O tempo real em que a pasta de trabalho será entregue baseia-se principalmente no tempo necessário para o processamento (pastas de trabalho complexas e grandes demoram mais para serem processadas do que pastas de trabalho mais simples). Por exemplo, se uma pasta de trabalho levar 15 minutos para ser processada, o tempo de entrega real será de pelo menos 15 minutos depois do &quot;Tempo de entrega&quot;/&quot;Hora do dia&quot; especificado originalmente.
>Além disso, há vários outros fatores que podem aumentar ainda mais o atraso, antes que a pasta de trabalho seja realmente entregue:
>
> * **A execução de várias programações diferentes do mesmo tipo ao mesmo tempo** pode sobrecarregar o sistema. O sistema de programação permite que algumas (5-10) pastas de trabalho de qualquer tipo sejam executadas simultaneamente, de modo que, quando mais de 5-10 estiverem programadas ao mesmo tempo, algumas precisarão aguardar a conclusão de outras pastas de trabalho na fila para que possam começar a processar. Esse problema pode ser atenuado pela programação de pastas de trabalho de uma empresa em horários escalonados ao longo do dia ou da hora, e não simultaneamente.
> * Além do tipo de pasta de trabalho específico, as pastas de trabalho também aguardarão na fila, se a empresa tiver **mais de 15 a 20 de qualquer tipo de pasta de trabalho programadas ao mesmo tempo (em todos os tipos diferentes de pasta de trabalho)**. Isso pode ser atenuado por horários de programação escalonados, em vez de muitas pastas de trabalho serem executadas ao mesmo tempo.
> * **Problemas em serviços downstream** nos quais o Agendador depende também podem afetar a entrega de pastas de trabalho. Por exemplo, se você estiver usando independentemente as APIs para executar pastas de trabalho e preencher a fila de solicitações da API, suas pastas de trabalho agendadas podem ser entregues lentamente enquanto você compete por esse recurso.
> * A **latência do conjunto de relatórios** (um atraso na coleta de dados) também pode atrasar algumas pastas de trabalho programadas.


## Agendar uma pasta de trabalho

1. Gere e salve uma pasta de trabalho.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   The [!UICONTROL Scheduled Reports] tab summarizes all the tasks you have created, as well as the number of remaining tasks.
1. Na **[!UICONTROL Scheduled Reports]** guia, clique em **[!UICONTROL New]**.
1. O assistente básico de agendamento mostrará:

   ![](assets/simple-schedule-wizard.png)

1. Na página [!UICONTROL Basic Scheduling Wizard], configure as seguintes opções:

| Campo | Descrição |
|--- |--- |
| Selecionar Relatório | O nome da pasta de trabalho. Para novos relatórios agendados, esse campo é preenchido com o nome da pasta de trabalho ativa. |
| Selecionar | Exibe a página Selecionar relatório. Você pode selecionar um relatório do servidor (onde todas as pastas de trabalho previamente agendadas estão armazenadas), ou de sua máquina local. Se você selecionar uma pasta de trabalho na unidade local no formato .xls, o sistema converterá o arquivo em .xlsx. Como parte da conversão, o arquivo é aberto no Excel e ativado. Se a pasta de trabalho selecionada para o relatório agendado tiver o mesmo nome de arquivo que a pasta de trabalho atualmente aberta no Excel, o sistema selecionará o arquivo local em vez do arquivo carregado anteriormente. Se você selecionar um relatório do repositório de agendamento, uma cópia da pasta de trabalho será criada no servidor, com seu nome de arquivo atualizado com 1 e o relatório agendado recém-criado usará a pasta de trabalho copiada. |
| Personalizar | Permite personalizar o formato de data. |
| Para | Exibe seu Catálogo de Endereços do Outlook, se aplicável. |
| Enviar para: Email | O destinatário do e-mail da pasta de trabalho. |
| Enviar para: Lista de publicação | Exibe uma lista de listas de distribuição disponíveis para esta empresa. |
| Power BI | Consulte [Publicar pasta de trabalho no Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) para obter mais informações. |
| Assunto | Uma descrição definida pelo usuário. |
| Agendamento | Permite especificar quando enviar a pasta de trabalho. (Imediatamente, a cada hora, diariamente, semanalmente, mensalmente e anualmente.) |

## Opções avançadas de entrega

1. Clique **[!UICONTROL Advanced Delivery Options]** para configurar as opções de arquivo e publicação:

| Campo | Descrição |
|--- |--- |
| Guia **Agendamento** |  |
| Hora de entrega | Permite programar o relatório imediatamente ou para um momento posterior. A hora do dia é relativa ao fuso horário especificado no computador. |
| Padrão de recorrência | Envia a pasta de trabalho com base em suas seleções. |
| Intervalo de recorrência | Permite especificar quando começar e parar de receber a pasta de trabalho.   Observação: programar um relatório no primeiro dia de qualquer período corrente (semana, mês, trimestre ou ano) retorna dados somente para o primeiro dia. |
| Guia **Opções de arquivo** |  |
| Formato do arquivo | Permite selecionar um formato de entrega do Excel 2007 (.xlsx) ou 2003 (.xls), .pdf, .csv, .mht, .txt e .xml. |
| Destino do arquivo | Especifica email ou FTP. As opções na página mudam, dependendo da sua seleção. Para FTP, você deve garantir que o host esteja disponível externamente. |
| Lista de Publicação | Se você enviar a pasta de trabalho agendada para várias listas de publicação, a pasta de trabalho será executada uma vez para cada lista. Conjuntos de relatórios variáveis são substituídos pelo conjunto de relatórios atribuído à lista de publicação. |
| Idioma do conteúdo do arquivo | Especifica o idioma que deseja usar para a carta de apresentação. Você pode selecionar chinês (simplificado ou tradicional), alemão, francês, japonês, coreano, português brasileiro ou espanhol. |
| Guia **Opções de publicação** |  |
| Publicação no Power BI | <ul><li>Publicar pasta de trabalho no Power BI</li><li>Publicar todas as solicitações do Report Builder como conjuntos de dados do Power BI</li><li>Publicar todas as tabelas formatadas como conjuntos de dados do Power BI</li></ul> |
| Rotule este Relatório do Power BI como | Detalhes da rotulagem |

1. Clique em **[!UICONTROL OK]**, em seguida, clique em **[!UICONTROL Exit]**.

   O Report Builder exibe a pasta de trabalho agendada no [Gerenciador de tarefas agendadas](/help/analyze/report-builder/r-arb-scheduled-reports.md).

