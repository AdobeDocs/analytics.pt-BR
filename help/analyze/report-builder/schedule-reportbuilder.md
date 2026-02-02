---
title: Agendar pastas de trabalho usando o Report Builder
description: Saiba como usar o recurso de agendamento no Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 40e1feb0-64bc-40e6-83cb-4a1ea7e2d0cc
source-git-commit: 8b6d8a4efec59b693a69984880d8f374ae0cfabc
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 26%

---

# Agendar pastas de trabalho compartilhando por email

>[!NOTE]
>
>Além de agendar pastas de trabalho para compartilhamento por email, conforme descrito nesta seção, você pode agendar pastas de trabalho para serem exportadas para destinos na nuvem, conforme descrito em [Agendar pastas de trabalho para exportação para destinos na nuvem](/help/analyze/report-builder/report-builder-export.md).

Depois de salvar a pasta de trabalho e concluir a análise, é possível compartilhar facilmente a pasta de trabalho com outras pessoas em sua equipe usando o recurso de programação. O recurso Programação permite criar um uma programação que atualiza automaticamente os dados na pasta de trabalho e envia por email o arquivo .xlsx da pasta de trabalho do Excel como um anexo para o público-alvo especificado em uma data e hora específicas. Configurar uma programação fornece atualizações regulares aos recipients automaticamente. Você também pode usar o recurso de programação para enviar a pasta de trabalho uma vez sem programar atualizações automáticas.

Você pode criar várias programações para uma única pasta de trabalho. Por exemplo, você pode enviar uma pasta de trabalho para sua equipe diariamente e enviar a pasta de trabalho para seu gerente uma vez por semana criando duas programações diferentes.

O recurso Programação também permite que você configure a proteção por senha para uma pasta de trabalho e edite pastas de trabalho previamente programadas.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Agendar pastas de trabalho](https://video.tv.adobe.com/v/3413079?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Agendar uma pasta de trabalho

Para programar uma pasta de trabalho:

1. Selecione **[!UICONTROL Agendar]** no hub do Report Builder para criar um agendamento para que você possa distribuir automaticamente um arquivo de pasta de trabalho do Excel (.xlsx) para um indivíduo ou grupo.

   ![Selecione o botão Agendar para criar um agendamento.](./assets/schedule.png){zoomable="yes"}

1. Selecione **[!UICONTROL Agendar pasta de trabalho]** ou ![Adicionar](/help/assets/icons/Add.svg) para criar uma nova pasta de trabalho agendada.

   ![A janela Agendar pastas de trabalho.](./assets/schedule-workbook.png){zoomable="yes"}

   O painel de programação exibe algumas informações predefinidas sobre a pasta de trabalho, como o nome da pasta de trabalho e a última data em que a pasta de trabalho foi modificada.

### Arquivo

Na seção **[!UICONTROL Arquivo]**, forneça detalhes sobre o tipo de arquivo, o nome e uma senha para proteger o arquivo.

![O painel de agendamento.](./assets/schedule-pane.png){zoomable="yes"}

1. Use ![TableSelect](/help/assets/icons/TableSelect.svg) para selecionar a pasta de trabalho atual, se ainda não estiver selecionada.

1. (Opcional) Insira um **[!UICONTROL Nome do arquivo]**.

   O nome de arquivo da pasta de trabalho é padronizado como o nome da pasta de trabalho, mas você pode alterar o nome do arquivo, se desejar.

1. Selecione um **[!UICONTROL Tipo de arquivo]**.

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   Ao selecionar **[!UICONTROL CSV]**, saiba que a pasta de trabalho agendada é enviada como um anexo zip. Algumas administrações de e-mail corporativas podem bloquear e-mails com anexos zip. Você verá um aviso adequadamente.

1. (Opcional) Selecione **[!UICONTROL Anexar carimbo de data/hora ao nome do arquivo]**.

   Você pode anexar um carimbo de data e hora ao nome do arquivo para identificar a data em que a pasta de trabalho foi atualizada. Um carimbo de data e hora é útil para ver qual versão de uma pasta de trabalho foi enviada em uma data específica. Quando selecionado, você pode escolher entre:

   * **[!UICONTROL Formato ISO de data]**, que resulta na anexação de `YYYY-MM-DD` ao nome de arquivo.
   * **[!UICONTROL Formato ISO de data + carimbo de data/hora]**, que resulta na anexação de `YYYY-MM-DD_HH-MM-SS` ao nome de arquivo.

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. Digite uma senha em **[!UICONTROL Proteger a pasta de trabalho com senha]**. Uma senha válida exige pelo menos 8 caracteres, um número e um caractere especial. Selecione ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) para exibir a senha e ![Visibility](/help/assets/icons/Visibility.svg) para ocultar a senha (padrão).


### Email

Na seção **[!UICONTROL Email]**, forneça os destinatários, o assunto e a descrição do email.

![Configurações de email de agendamento](assets/schedule-email.png){zoomable="yes"}

1. Insira os **Recipients**. Você pode inserir o nome de uma pessoa reconhecida em sua organização. Ou você pode inserir um endereço de email de uma pessoa que esteja fora da sua organização.

1. Insira o **Assunto** do email e uma descrição para seus recipients. O assunto assume o padrão do nome do arquivo da pasta de trabalho, mas você pode modificar o assunto, se necessário. Você pode adicionar detalhes na seção de descrição.

1. Opcionalmente, você pode inserir uma descrição na área de texto **[!UICONTROL Descrição]**.


### Agendar

Na seção **[!UICONTROL Agendar]**, você pode definir o agendamento para enviar os emails com a pasta de trabalho para seus destinatários.

![Definição de agendamento](assets/schedule-enable.png){zoomable="yes"}

1. Selecione **[!UICONTROL Mostrar opções de agendamento]** para definir um agendamento.

1. Insira uma data de início em **[!UICONTROL A partir de]**. Como alternativa, selecione ![Calendário](/help/assets/icons/Calendar.svg) para escolher uma data de início no calendário.

1. Insira uma data de término em **[!UICONTROL Terminando em]**. Como alternativa, selecione ![Calendário](/help/assets/icons/Calendar.svg) para escolher uma data de término no calendário.

1. Selecione uma **[!UICONTROL Frequência]**. Dependendo da frequência selecionada, você tem opções adicionais. Consulte a tabela abaixo.

   | Frequência | Opções |
   |---|---|
   | **[!UICONTROL Enviar por hora]** | Insira um valor para **[!UICONTROL Enviar a cada número de horas]**. |
   | **[!UICONTROL Enviar diariamente]** | Selecione uma **[!UICONTROL Frequência diária]**: **[!UICONTROL Enviar todos os dias]**, **[!UICONTROL Enviar todos os dias da semana]** ou **[!UICONTROL Frequência personalizada]**.<br/>Se você selecionar **[!UICONTROL Frequência personalizada]**, insira um valor para **[!UICONTROL Enviar todos os números de dias]**. |
   | **[!UICONTROL Enviar semanalmente]** | Insira um valor para **[!UICONTROL Enviar a cada número de semanas]**. E selecione um **[!UICONTROL Dia da semana]**. |
   | **[!UICONTROL Enviar mensalmente por dia da semana]** | Selecione um **[!UICONTROL Dia da semana]** e uma **[!UICONTROL Semana do mês]**. |
   | **[!UICONTROL Enviar mensalmente por dia do mês]** | Selecione um valor de **[!UICONTROL Enviar neste dia do mês]**. |
   | **[!UICONTROL Enviar anualmente por dia do mês]** | Selecione um **[!UICONTROL Dia da semana]**, selecione uma **[!UICONTROL Semana do mês]** e selecione um **[!UICONTROL Mensal do ano]**. |
   | **[!UICONTROL Enviar anualmente por data específica]** | Selecione um **[!UICONTROL Mês do ano]** e selecione um valor de **[!UICONTROL Enviar neste dia do mês]**. |

### Enviar

Para enviar a pasta de trabalho:

* Se você não tiver definido um agendamento usando **[!UICONTROL Mostrar opções de agendamento]**, selecione **[!UICONTROL Enviar agora]** para enviar a pasta de trabalho por email imediatamente.
* Se você tiver definido um agendamento usando **[!UICONTROL Mostrar opções de agendamento]**, selecione **[!UICONTROL Enviar de acordo com o agendamento]** para enviar a pasta de trabalho por email usando o agendamento definido.

Em ambos os casos, você verá uma notificação de confirmação na parte inferior do hub do Report Builder.

Para cancelar o envio da pasta de trabalho, selecione **[!UICONTROL Cancelar]**.

## Gerenciar pastas de trabalho programadas

Para obter informações sobre como gerenciar pastas de trabalho já agendadas, consulte [Gerenciar pastas de trabalho agendadas](/help/analyze/report-builder/manage-reportbuilder.md).




<!--

## Schedule a workbook

Use the Schedule button in the Report Builder hub to quickly create a schedule so that you can automatically distribute a workbook Excel file (.xlsx) to an individual or a group.

1. Click the Schedule button in the Report Builder hub.

    ![Click the Schedule button to create a schedule.](./assets/schedule-button.png){width="55%"}

1. Click Schedule Workbook or the plus button in the upper-left to create a new scheduled workbook.

    ![The Schedule workbooks window.](./assets/schedule-workbook.png){width="55%"}

    The scheduling pane displays some pre-defined information about the workbook such as the workbook name and the last date that the workbook was modified.

    ![The scheduling pane.](./assets/schedule-pane.png){width="55%"}

1. (Optional) Enter a file name.

    The workbook file name defaults to the name of the workbook but you can change this if you want. If you\'re sending the same workbook to multiple audiences and you want to name it something a little bit more friendly for a certain audience, you can change the name.

1. (Optional) Select **Append time-stamp to file name**.

    You can append a timestamp to the file name to identify the date the workbook was updated. This is helpful to quickly see which version of a workbook was sent on a specific date. The **Filename preview** shows how the workbook file name will appear in the email when the workbook is distributed. The time-stamp format is YYYY-MM-DD.

1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){width="55%"}

1. Enter **Recipients**. You can enter the name of a person that is recognized in your organization, or you can enter an email address of a person inside or outside of your organization.

1. Enter the **Subject** of the email and a description for your recipients. The subject defaults to the workbook file name but you can modify the subject if needed. You can add details in the description section.

    ![Enter a subject in the Subject field.](./assets/recipients-subject.png){width="55%"}

1. Set up the scheduling options to set the date and time that you want the workbook emailed to your recipients.

    Choose the start and end date and time frames. This can be today's date or a date in the future.

    Choose the **Frequency** from the drop-down menu. You can set the frequency to be hourly, daily, weekly, monthly, or yearly on a specific day. For example, you can set up a schedule to send the workbook on the first Sunday night of the month so that your recipients will have the email in their inbox first thing on Monday morning.

    ![Select the frequency to schedule your report.](./assets/frequency.png){width="55%"}

1. After you set the schedule, click **Send on schedule**.

    ![Click Send on schedule.](./assets/send-on-schedule.png){width="55%"}

    You see a confirmation toast at the bottom of the Report Builder hub and the scheduled workbook is listed under the Workbooks tab.

    ![Confirmation toast](./assets/confirmation-toast.png){width="55%"}

## Schedule a converted workbook {#converted}

1. Schedule a [converted](/help/analyze/report-builder/convert-workbooks.md) legacy workbook.

   A pop up appears, asking if you want to use the scheduling metada from the legacy workbook to create a new scheduled task. 

1. If you select **[!UICONTROL Use]**, Report Builder automatically fills in the legacy scheduling information. 

1. Ensure that this information is correct and schedule. 

1. If you want to send the workbook on a different schedule, schedule a completely fresh scheduled task. 


## Send the workbook one-time only

You can also send out the workbook only once.

1. Un-check **Show scheduling options** 

    ![Click Un-check Show scheduling options to send out a workbook one time.](./assets/send-now.png){width="40%"}

1. Click **Send Now**.

## Manage scheduled workbooks

For information about managing workbooks that are already scheduled, see [Manage scheduled workbooks](/help/analyze/report-builder/manage-schedules-reportbuilder.md).

-->