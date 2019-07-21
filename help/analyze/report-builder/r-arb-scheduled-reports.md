---
description: Descrições dos campos para o Gerenciador de tarefas agendadas.
seo-description: Descrições dos campos para o Gerenciador de tarefas agendadas.
seo-title: Gerenciador de tarefa agendada
solution: Analytics
title: Gerenciador de tarefa agendada
topic: Construtor de relatórios
uuid: dec 259 f 0-2 a 04-4 c 94-abbc -5008 cf 2 f 1 cb 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Gerenciador de tarefa agendada

Descrições dos campos para o Gerenciador de tarefas agendadas.

O Gerenciador de tarefas agendadas permite que você visualize uma lista de relatórios agendados existentes, juntamente com seus destinatários, detalhes do agendamento e formatos de arquivo. Ele também permite a reativação de pastas de trabalho agendadas que não foram executadas.

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Guia<b> Relatórios agendados</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome do Relatório </p> </td> 
   <td colname="col2"> <p>Indica o nome da tarefa agendada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Email/FTP </p> </td> 
   <td colname="col2"> <p>O endereço de email ou do FTP do destinatário. </p> <p>Observação: se o email estiver selecionado, os relatórios com mais de 1 MB são anexados automaticamente ao email como um arquivo .zip. Este recurso ajuda a manter o tamanho pequeno dos arquivos anexados e não pode ser desativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opções de publicação </p> </td> 
   <td colname="col2"> <p>Essa coluna listará o Power BI se ums das <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#concept_0C4105AA10F9460A872C2489C9CD7945" format="dita" scope="local"> opções de publicação do Power BI</a> estiver selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agendar </p> </td> 
   <td colname="col2"> <p>O tipo de entrega agendado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato do arquivo </p> </td> 
   <td colname="col2"> <p> O formato de entrega do relatório, como Excel, PDF, HTML, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reativar </p> </td> 
   <td colname="col2"> <p>Quando ocorre falha de execução de uma pasta de trabalho agendada, o Construtor de relatórios tenta executá-la mais duas vezes a cada quinze minutos. Depois de três tentativas mal sucedidas, o Construtor de relatórios desativa o agendamento e exibe o botão <span class="wintitle">Reativar</span>. Quando você reativa uma pasta de trabalho, a entrega agendada é reiniciada a partir do momento em que foi desativada. </p> <p>Por exemplo, se uma pasta de trabalho agendada foi desativada há 14 dias e você a reativar hoje, ela será executada para todos os dias que estiverem faltando e será entregue 14 vezes. Se não quiser que a pasta de trabalho seja entregue para os dias que estiverem faltando, você poderá excluir a pasta de trabalho agendada e, em seguida, criar uma nova pasta de trabalho agendada usando os mesmos parâmetros de agendamento. </p> <p> <p>Observação: você não deve reativar uma pasta de trabalho, a menos que saiba o motivo de o sistema tê-la desativado. Uma solução para o problema é baixar uma pasta de trabalho desativada e atualizá-la no lado do cliente. Se não encontrar nenhum erro, você deve conseguir reativá-la. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Último envio </p> </td> 
   <td colname="col2"> <p>A data e a hora quando o relatório foi enviado pela última vez. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guia <b>Destinatário</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Email do destinatário </p> </td> 
   <td colname="col2"> O destinatário do email do relatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Relatórios </p> </td> 
   <td colname="col2"> Os relatórios que são enviados a cada destinatário. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guia <b>Histórico de relatórios</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome do arquivo </p> </td> 
   <td colname="col2"> Indica o nome da tarefa agendada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data </p> </td> 
   <td colname="col2"> A data e a hora quando o relatório foi enviado pela última vez. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> O status indica se o relatório foi enviado ou não. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Email/FTP </p> </td> 
   <td colname="col2"> O endereço de email ou FTP do destinatário do relatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formato do arquivo </p> </td> 
   <td colname="col2"> O formato de entrega do relatório, como Excel, PDF, HTML, etc. </td> 
  </tr> 
 </tbody> 
</table>
