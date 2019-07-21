---
description: Você pode agendar relatórios para envio de acordo com a hora e o formato de arquivo definidos.
seo-description: Você pode agendar relatórios para envio de acordo com a hora e o formato de arquivo definidos.
seo-title: Agendar uma solicitação de dados
solution: Analytics
title: Agendar uma solicitação de dados
topic: Construtor de relatórios
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# Agendar uma solicitação de dados

Você pode agendar relatórios para envio de acordo com a hora e o formato de arquivo definidos.

**Para agendar uma solicitação de dados**

1. Gere e salve um relatório.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   A guia [!UICONTROL Relatórios agendados] resume todas as tarefas que você tiver criado, bem como o número de tarefas restantes.
1. Na guia **Relatórios agendados**, clique em **[!UICONTROL Novo]**.
1. O assistente básico de agendamento mostrará:

   ![](assets/simple-schedule-wizard.png)

1. No [!UICONTROL Assistente básico de agendamento], configure as seguintes opções:

* **Selecionar Relatório**: O nome do relatório. Para novos relatórios agendados, este campo é preenchido com o nome da pasta de trabalho ativa.

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
   <td colname="col2"> <p>Exibe a página <span class="wintitle">Selecionar relatório</span>. Você pode selecionar um relatório do servidor (onde todas as pastas de trabalho previamente agendadas estão armazenadas), ou de sua máquina local. Se você selecionar uma pasta de trabalho na unidade local no formato <span class="filepath">.xls</span>, o sistema converterá o arquivo em <span class="filepath">.xlsx</span>. Como parte da conversão, o arquivo é aberto no Excel e ativado. Se a pasta de trabalho selecionada para o relatório agendado tiver o mesmo nome de arquivo da pasta de trabalho aberta no momento no Excel, o sistema selecionará o arquivo local em vez do arquivo carregado previamente. Se você selecionar um relatório do repositório de agendamento, uma cópia da pasta de trabalho será criada no servidor, com seu nome de arquivo atualizado com 1, e o relatório agendado recém-criado usará a pasta de trabalho copiada. </p> </td> 
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
   <td colname="col2"> <p>O destinatário do email do relatório. </p> </td> 
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
   <td colname="col2"> <p> Permite especificar quando enviar o relatório. (Imediatamente, a cada hora, diariamente, semanalmente, mensalmente e anualmente.) </p> </td> 
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
   <td colname="col2"> <p>Permite agendar o relatório imediatamente ou para um momento posterior. A hora do dia é relativa ao fuso horário especificado no computador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Padrão de recorrência </p> </td> 
   <td colname="col2"> <p>Envia o relatório com base em suas seleções. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de recorrência </p> </td> 
   <td colname="col2"> <p>Permite especificar quando começar e parar de receber o relatório. </p> <p> <p>Observação: agendar um relatório no primeiro dia de qualquer período corrente (semana, mês, trimestre ou ano) retorna dados somente para o primeiro dia. </p> </p> </td> 
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
   <td colname="col2"> <p> Se você enviar o relatório agendado para várias listas de publicação, o relatório será executado uma vez para cada lista. Conjuntos de relatórios variáveis são substituídos pelo conjunto de relatórios atribuído à lista de publicação. </p> </td> 
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

   O Construtor de relatórios exibe o relatório agendado no [Gerenciador de tarefas agendadas](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).
