---
description: Você pode agendar relatórios para envio de acordo com a hora e o formato de arquivo definidos.
seo-description: Você pode agendar relatórios para envio de acordo com a hora e o formato de arquivo definidos.
seo-title: Agendar uma solicitação de dados
solution: Analytics
title: Agendar uma solicitação de dados
topic: Construtor de relatórios
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: 62937df0a763f6b9b34389d968c5641056b47aa8

---


# Agendar uma pasta de trabalho

Você pode agendar pastas de trabalho, especificar opções avançadas de entrega, especificar destinatários e visualizar o histórico da programação. As opções avançadas de entrega permitem que você configure pastas de trabalho que deseja enviar em um horário específico ou em intervalos. Você também pode especificar o formato de arquivo para enviar a pasta de trabalho.

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. O limite de tamanho do arquivo é de 5 MB para um upload de pasta de trabalho.

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. (Consulte [Agendamento e distribuição de relatórios](/help/analyze/reports-analytics/scheduling.md) na ajuda do Relatórios e análises).

>[!NOTE]
>
>Você deve ter o Excel 2007 ou o pacote de compatibilidade instalado para programar uma pasta de trabalho. Você pode ter no máximo 10 pastas de trabalho programadas por licença do Construtor de relatórios. No entanto, é possível aumentar esse número ao subtrair de outras licenças. To do so, go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. Uma pasta de trabalho programada (ou enviada para a Biblioteca de pastas de trabalho) e que não foi tocada (atualizada, substituída) em mais de 28 meses será excluída.

>[!NOTE]
>
>A "Hora de entrega"/"Hora do dia" inserida pelo usuário especifica o tempo em que a pasta de trabalho deve começar o processamento, não o tempo que será realmente entregue. A hora real em que a pasta de trabalho será entregue baseia-se principalmente no tempo que leva para processar (pastas de trabalho complexas e grandes levam mais tempo para processar do que pastas de trabalho simples). Por exemplo, se uma pasta de trabalho levar 15 minutos para processar, o tempo de entrega real terá pelo menos 15 minutos após o "Tempo de entrega" especificado originalmente/"Hora do dia".
>Além disso, há vários outros fatores que podem aumentar ainda mais o atraso antes da entrega da pasta de trabalho:
>
> * **Executar muitos horários diferentes do mesmo tipo ao mesmo tempo** pode sobrecarregar o sistema. O sistema de programação permite somente algumas (5-10) pastas de trabalho de qualquer tipo para serem executadas simultaneamente. Portanto, quando mais de 5-10 todos estão programados de uma vez, alguns precisam aguardar que outras pastas de trabalho terminem antes que possam começar a processar. Esse problema pode ser reduzido ao agendar as pastas de trabalho de uma empresa em momentos quebrados durante o dia ou hora, em vez de simultaneamente.
> * Além do tipo de pasta de trabalho específico, as pastas de trabalho também serão aguardadas se a empresa tiver **mais de 15-20 de qualquer tipo de pasta de trabalho programada de uma vez (em todos os tipos de pasta de trabalho diferentes)**. Isso pode ser reduzido ao detalhar os tempos de programação em vez de ter muitas executado ao mesmo tempo.
> * **Os problemas nos serviços** a jusante com os quais o Agendador depende também podem afetar a entrega de pastas de trabalho. Por exemplo, se você estiver usando as apis de forma independente para executar pastas de trabalho e preencher a fila de solicitação da API, suas pastas de trabalho programadas podem ser entregues lentamente enquanto você compete por esse recurso.
> * **A latência do conjunto de relatórios** (um atraso na coleção de dados) também pode atrasar algumas pastas de trabalho programadas.


**Para agendar uma pasta de trabalho**

1. Gere e salve uma pasta de trabalho.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   A guia [!UICONTROL Relatórios agendados] resume todas as tarefas que você tiver criado, bem como o número de tarefas restantes.
1. Na guia **Relatórios agendados**, clique em **[!UICONTROL Novo]**.
1. O assistente básico de agendamento mostrará:

   ![](assets/simple-schedule-wizard.png)

1. No [!UICONTROL Assistente básico de agendamento], configure as seguintes opções:

* **Selecionar Relatório**: O nome da pasta de trabalho. Para novas pastas de trabalho agendadas, este campo é preenchido com o nome da pasta de trabalho ativa.

<table id="table_6D5B1B832EB0451293F1902E2A1D1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Selecionar relatório </p> </td> 
   <td colname="col2"> <p>O nome do relatório. Para novos relatórios agendados, este campo é preenchido com o nome da pasta de trabalho ativa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Selecionar </p> </td> 
   <td colname="col2"> <p>Exibe a página <span class="wintitle">Selecionar relatório</span>. Você pode selecionar um relatório do servidor (onde todas as pastas de trabalho previamente agendadas estão armazenadas), ou de sua máquina local. Se você selecionar uma pasta de trabalho na unidade local no formato <span class="filepath">.xls</span>, o sistema converterá o arquivo em <span class="filepath">.xlsx</span>. Como parte da conversão, o arquivo é aberto no Excel e ativado. Se a pasta de trabalho selecionada para o relatório agendado tiver o mesmo nome de arquivo da pasta de trabalho aberta no momento no Excel, o sistema selecionará o arquivo local em vez do arquivo carregado previamente. Se você selecionar um relatório do repositório agendamento, uma cópia da pasta de trabalho será criada no servidor, com seu nome de arquivo atualizado com 1. O relatório programado recém-criado usa a pasta de trabalho copiada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Personalizar </p> </td> 
   <td colname="col2"> <p>Permite a personalização do formato de data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para </p> </td> 
   <td colname="col2"> <p>Exibe seu Catálogo de endereços do Outlook, se aplicável. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar para: Email </p> </td> 
   <td colname="col2"> <p>O destinatário do email da pasta de trabalho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar para: Lista de publicação </p> </td> 
   <td colname="col2"> <p>Exibe uma lista de listas de distribuição disponíveis para essa empresa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local">Publicação de pasta de trabalho no Microsoft Power BI</a> para mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Assunto </p> </td> 
   <td colname="col2"> <p>Uma descrição definida pelo usuário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agendamento </p> </td> 
   <td colname="col2"> <p> Permite especificar quando enviar a pasta de trabalho. (Imediatamente, a cada hora, diariamente, semanalmente, mensalmente e anualmente.) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

<table id="table_1BA8A5600DE94A33B83B096E69CE15F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Guia <b>Agendamento</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hora de entrega </p> </td> 
   <td colname="col2"> <p>Permite agendar a pasta de trabalho imediatamente ou para um momento posterior. A hora do dia é relativa ao fuso horário especificado no computador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Padrão de recorrência </p> </td> 
   <td colname="col2"> <p>Envia a pasta de trabalho com base em suas seleções. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de recorrência </p> </td> 
   <td colname="col2"> <p>Permite especificar quando começar e parar de receber a pasta de trabalho. </p> <p> <p>Observação: Agendar uma pasta de trabalho no primeiro dia de qualquer período atual (semana, mês, trimestre ou ano) retorna dados apenas para o primeiro dia. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guia <b>Opções de arquivo</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formato do arquivo </p> </td> 
   <td colname="col2"> <p>Permite selecionar um formato de entrega do Excel 2007 (<span class="filepath">.xlsx</span>) ou 2003 (<span class="filepath">.xls</span>), <span class="filepath">.pdf</span>, <span class="filepath">.csv</span>, <span class="filepath">.mht</span>, <span class="filepath">.txt</span> e <span class="filepath">.xml</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Destino do arquivo </p> </td> 
   <td colname="col2"> <p> Especifica Email ou FTP. As opções na página mudam, dependendo da sua seleção. Para FTP, você precisa garantir que o host esteja disponível externamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lista de Publicação </p> </td> 
   <td colname="col2"> <p> Se você enviar a pasta de trabalho agendada para várias listas de publicação, a pasta de trabalho será executada uma vez para cada lista. Conjuntos de relatórios variáveis são substituídos pelo conjunto de relatórios atribuído à lista de publicação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Idioma do conteúdo do arquivo </p> </td> 
   <td colname="col2"> <p>Especifica o idioma a ser usado na carta de apresentação. Você pode selecionar chinês (simplificado ou tradicional), alemão, francês, japonês, coreano, português brasileiro ou espanhol. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guia <b>Opções de publicação</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Publicação no Power BI </p> </td> 
   <td colname="col2"> 
    <ul id="ul_40697E4FB2CE4F34B857FBF153D6D6D5"> 
     <li id="li_023E4750814D415EBC899269C9EA5D46"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> Publicar pasta de trabalho no Power BI</a> </li> 
     <li id="li_9B684BE22AF94ABC903405EE83951A80"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_E48148793E794169B766C73995897B9F" format="dita" scope="local"> Publicar todas as solicitações do Construtor de relatórios como conjuntos de dados do Power BI</a> </li> 
     <li id="li_7B0BD285BC1749D1B2C65759CA97877B"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_6F8422B90D3F4F7EB5D4C97BFFA807AD" format="dita" scope="local"> Publicar todas as tabelas formatadas como conjuntos de dados do Power BI</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rotule esse relatório do Power BI como </p> </td> 
   <td colname="col2"> <p>Detalhes da rotulação </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).

