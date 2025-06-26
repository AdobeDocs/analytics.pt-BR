---
description: Envie um projeto do Analysis Workspace por email ou agende sua entrega.
keywords: Analysis Workspace
title: Agendar projetos
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
source-git-commit: d4d0eeac4f1f29e4c68e80b6fa0fe987a1fb32b9
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 32%

---

# Enviar arquivos para outras pessoas

Você pode enviar relatórios do Adobe Analytics como arquivos para usuários selecionados por email. Você pode enviar arquivos ad hoc ou pode configurar arquivos para serem enviados de acordo com uma programação. Os arquivos podem ser enviados no formato CSV ou PDF.

As tags aplicadas ao projeto são automaticamente aplicadas à exportação.

Outros métodos de exportação de dados do Adobe Analytics também estão disponíveis, conforme descrito em [Visão geral da exportação](/help/export/home.md).

![Enviar arquivo](assets/send-file.png)

## Enviar arquivo

Para enviar um arquivo aos recipients por email:

1. Selecione **[!UICONTROL Compartilhar] > [!UICONTROL Enviar arquivo]**.
1. Especifique o tipo de arquivo:
   * [!UICONTROL **CSV**]: escolha essa opção se desejar dados de texto simples.
   * [!UICONTROL **PDF**]: escolha essa opção se desejar que o arquivo baixado contenha todas as tabelas e visualizações exibidas (visíveis) no projeto.
1. (Opcional) Use **[!UICONTROL Descrição]** para adicionar uma descrição a ser incluída no email.
1. Adicione recipients ou grupos. Você também pode inserir endereços de email.
1. (Opcional) Selecione **[!UICONTROL Mostrar opções de agendamento]** para [agendar uma exportação de arquivo](#schedule-file-export).
1. Clique em **[!UICONTROL Enviar Agora]**. Selecione **[!UICONTROL Cancelar]** para cancelar.


## Programar exportação de arquivo {#schedule}

Para enviar um arquivo por email de acordo com um agendamento para os recipients

1. Selecione **[!UICONTROL Compartilhar] > [!UICONTROL Agendar exportação de arquivo]**.
1. Especifique o tipo de arquivo:
   * [!UICONTROL **CSV**]: escolha essa opção se desejar dados de texto simples.
   * [!UICONTROL **PDF**]: escolha essa opção se desejar que o arquivo baixado contenha todas as tabelas e visualizações exibidas (visíveis) no projeto.
1. (Opcional) Use **[!UICONTROL Descrição]** para adicionar uma descrição a ser incluída no email.
1. Adicione recipients ou grupos. Você também pode inserir endereços de email.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha para [proteger com senha um relatório agendado](#password-protect-a-new-scheduled-project).
1. Verifique se **[!UICONTROL Mostrar opções de agendamento]** está selecionado.
1. Selecione uma **[!UICONTROL Frequência]**. Você pode selecionar entre:

   | Frequência | Opções |
   |---|---|
   | **[!UICONTROL Enviar por hora]** | Insira um valor para **[!UICONTROL Enviar a cada número de horas]**. |
   | **[!UICONTROL Enviar diariamente]** | Selecione uma **[!UICONTROL Frequência diária]**: **[!UICONTROL Enviar todos os dias]**, **[!UICONTROL Enviar todos os dias da semana]** ou **[!UICONTROL Frequência personalizada]**.<br/>Se você selecionar **[!UICONTROL Frequência personalizada]**, insira um valor para **[!UICONTROL Enviar todos os números de dias]**. |
   | **[!UICONTROL Enviar semanalmente]** | Insira um valor para **[!UICONTROL Enviar a cada número de semanas]**. E selecione um **[!UICONTROL Dia da semana]**. |
   | **[!UICONTROL Enviar mensalmente por dia da semana]** | Selecione um **[!UICONTROL Dia da semana]** e uma **[!UICONTROL Semana do mês]**. |
   | **[!UICONTROL Enviar mensalmente por dia do mês]** | Selecione um valor de **[!UICONTROL Enviar neste dia do mês]**. |
   | **[!UICONTROL Enviar anualmente por dia do mês]** | Selecione um **[!UICONTROL Dia da semana]**, selecione uma **[!UICONTROL Semana do mês]** e selecione um **[!UICONTROL Mensal do ano]**. |
   | **[!UICONTROL Enviar anualmente por data específica]** | Selecione um **[!UICONTROL Mês do ano]** e selecione um valor de **[!UICONTROL Enviar neste dia do mês]**. |

1. Insira uma data de início em **[!UICONTROL A partir de]**. Como alternativa, selecione ![Calendário](/help/assets/icons/Calendar.svg) para escolher uma data de início no calendário.

1. Insira uma data de término em **[!UICONTROL Terminando em]**. Como alternativa, selecione ![Calendário](/help/assets/icons/Calendar.svg) para escolher uma data de término no calendário.
1. Selecione **[!UICONTROL Enviar conforme agendado]**. Selecione **[!UICONTROL Cancelar]** para cancelar.


## Gerenciador de projetos programados {#manager}

Os projetos agendados do Analysis Workspace podem ser gerenciados na interface principal, usando **[!UICONTROL Componentes]** > **[!UICONTROL Projetos agendados]**. Para obter mais informações, consulte [Projetos agendados](/help/components/scheduled-projects-manager.md).

<!--
# Schedule projects

From the Workspace **Share menu**, you can send Analysis Workspace projects using email to selected recipients. Files can be sent in CSV or PDF format. After you share scheduled projects, you can edit the schedule settings to modify the frequency, receipient list, or file type using the Scheduled Projects manager.

## Send file now

To send a file immediately to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Export file]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Add a description to include in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Click **[!UICONTROL Send Now]**.
1. (Optional) Click **[!UICONTROL Show scheduling options]** to specify a delivery schedule.

![Send file now](assets/send-file-now.png)

## Send file on schedule

To send a file on a recurring schedule to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Schedule file export]**.
1. Specify the file type (CSV or PDF).
1. (Optional) Add a description that will be included in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Specify the range the schedule should be delivered over by modifying Starting on and Ending on inputs. The end date must be within a year from the day the schedule is created or modified.
1. Specify the delivery frequency. Each frequency allows for different customizations. 
1. Click **[!UICONTROL Send on schedule]**.

![](assets/send-on-schedule.png)

## Manage scheduled projects

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency


Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

For more information, see [Scheduled projects](/help/components/scheduled-projects-manager.md)
-->
