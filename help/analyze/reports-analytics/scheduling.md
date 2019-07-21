---
description: Informações sobre agendamento, download e distribuição de relatórios.
seo-description: Informações sobre agendamento, download e distribuição de relatórios.
seo-title: Programação e distribuição do relatório
solution: Analytics
subtopic: Agendar
title: Programação e distribuição do relatório
topic: Reports and Analytics
uuid: 1230 b 0 f 3-e 026-4 b 83-b 231-14 d 6 f 75 a 3836
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Programação e distribuição do relatório

Informações sobre agendamento, download e distribuição de relatórios.

## Report schedule and distribution {#concept_4EA333DFC7FD4E9CA086385A3DA10BE9}

Informações sobre agendamento, download e distribuição de relatórios.

Ao agendar um relatório para entrega no aplicativo Adobe Analytics, você pode usar as ferramentas de Agendamento e Distribuição para saber quais arquivos foram enviados automaticamente e modificar ou encerrar as entregas.

Devido às diferenças entre os mecanismos e plataformas de processamento, os diversos tipos de relatórios do Adobe Analytics que podem ser baixados e agendados têm diferentes limitações em relação ao número máximo de linhas que podem ser processadas em uma única solicitação. Estes são os limites de cada um:

* Word, CSV, Excel, HTML e PDF: o mesmo número de linhas visíveis no relatório. Por padrão, esse limite é de 50 linhas, mas ele pode ser aumentado para até 200. Relatórios de Detalhamento têm um limite rígido de 50 linhas.
* Extrações de dados: 50.000 linhas
* Data Warehouse: ilimitado

Observe que essas limitações referem-se a relatórios individuais agendados e baixados; os painéis são limitados à quantidade de espaço disponível em um reportlet.

## Enviar um relatório {#task_27642CD33D484FD0BF59EBD159EEF52C}

Etapas que descrevem como fazer o download e enviar por email relatórios em vários formatos, além de agendar a entrega de um relatório.

<!-- 

t_send_report.xml

 -->

1. Run a report, then click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.
1. Especifique as opções de entrega:

   | Opção | Descrição |
   |--- |--- |
   | Formato | Selecione PDF ou HTML. |
   | Enviar para | Forneça o endereço de email do destinatário.. |
   | Assunto | Assunto do email. |
   | Agendamento | Selecione para enviar o relatório imediatamente ou em um intervalo diferente. |

1. Click **[!UICONTROL Advanced Delivery Options]** to specify a delivery schedule.

   <table id="choicetable_2934E54FEE6E4D33B07EAC21F6DF628E"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Opção </th> 
   <th class="chdeschd"> Descrição </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Nome do arquivo de relatório</strong></td> 
   <td class="chdesc stentry"> <p>Digite o nome do relatório. O formato padrão é <code>&lt;nome do relatório&gt; de &lt;conjunto&gt; - &lt;intervalo de datas do relatório&gt; </code>. </p> <p>Para especificar um nome personalizado, selecione <span class="uicontrol">Personalizado </span>. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Formato do Relatório</strong></td> 
   <td class="chdesc stentry"> <p>Permite que você especifique PDF, CSV, Excel, HTML, Word, ou formatos móveis para a entrega. Se você selecionar CSV, você também pode especificar a codificação para CSV: </p> <p> 
      <ul id="ul_4A2EB8D9512246589994052CF482BFD7"> 
      <li id="li_A4FC4D795A9D4F92AAB187ACDFBA180D"> <p> <span class="uicontrol"> Shift-JIS</span>: codificação de caracteres japoneses. </p> </li> 
      <li id="li_405C7EC97F994D649A50F84466FADA3D"> <p> <span class="uicontrol"> EUC-JP</span>: código Unix Extended, principalmente para japonês, coreano e chinês simplificado. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Conteúdos do relatório</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Número de linhas na tabela</span>: especifique o número de linhas que devem ficar visíveis na tabela do relatório que você está enviando. </p> <p> <span class="uicontrol"> Idioma para cabeçalho e rodapé</span>: especifique o idioma para o cabeçalho e rodapé. </p> <p> <span class="uicontrol"> comentários</span>: especifique o texto a ser exibido no começo do relatório. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Enviar arquivo de assinatura digital</strong></td> 
   <td class="chdesc stentry"> <p>Quando você solicita um relatório, como um relatório marcado ou solicitações do data warehouse, é possível solicitar uma assinatura de dados. A assinatura digital da Adobe não restringe quem tem acesso aos dados, mas a finalidade do Arquivo de assinatura digital (.sig) é verificar a validade do arquivo de relatório fornecido. Usando a assinatura digital, os destinatários do relatório podem se certificar de que o arquivo veio da Adobe e que não foi alterado. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Destino do Relatório</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Email</span>: permite definir as configurações de endereço de email, o assunto e notas. </p> <p> <span class="uicontrol"> FTP</span>: permite configurar as definições de FTP, incluindo o host, porta, diretório, nome de usuário e senha. </p> </td> 
   </tr> 
   </table>

1. Click **[!UICONTROL Scheduling Options]**.

   <table id="choicetable_589A39087F4C497D8913364FFF0125B7"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Opção </th> 
   <th class="chdeschd"> Descrição </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Enviar relatório agora</strong></td> 
   <td class="chdesc stentry"> <p>Envia o relatório imediatamente. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Agendar para mais tarde</strong></td> 
   <td class="chdesc stentry"> <p>Exibe opções para especificar um período de tempo e opções de entrega. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Intervalo de tempo dos relatórios</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Fixo</span>: impede que a data avance com o passar do tempo. </p> <p> <span class="uicontrol">Em andamento</span>: permite que a data avance com o passar do tempo. Algumas considerações: </p> <p> 
      <ul id="ul_5CDCCBEFEB364800A428614183A0E6A1"> 
      <li id="li_37B8F32A9E3B4979B5239A58F0C5A71C"> <p>Se você selecionar em andamento para as datas de início e fim, e você selecionar um relatório diário para o dia anterior, você receberá um email a cada dia com um relatório do dia anterior. </p> </li> 
      <li id="li_83FFD2400C6A453783CDD9BB3B9BA3F9"> <p>Se você selecionar fixo para a data de início e em andamento para a data de término, você receberá no primeiro dia um relatório do dia anterior. O segundo dia você receberá um relatório dos dois dias anteriores, no terceiro dia você receberá um relatório dos últimos três dias, e assim por diante. </p> </li> 
      <li id="li_28F8552D699841BC942058247D39DBB9"> <p>Se você selecionar fixo para as datas de início e término, a cada dia você receberá um relatório idêntico dos dias que você especificou. </p> </li> 
      <li id="li_A594A6E2A4044ED6AC0A80F88EB203B3"> <p>Você não pode selecionar uma data de início em andamento e uma data de término fixa. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Frequência de entrega</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Por hora</span>: envia um email a cada hora, ou qualquer outro intervalo de horas. </p> <p> <span class="uicontrol">Diariamente</span>: envia um email todos os dias, em dias alternados, a cada três dias, ou qualquer outro intervalo de dias. Você também pode enviá-lo a cada dia da semana. </p> <p> <span class="uicontrol">Semanalmente</span>: envia o email toda semana, a cada duas semanas, a cada três semanas, ou qualquer outro intervalo de semanas. Você também pode especificar em qual dia da semana ele é enviado. </p> <p> <span class="uicontrol"> Mensalmente</span>: especifica o intervalo em número de meses, e você também pode selecionar o dia do mês em que será enviado, ou o dia da semana em uma semana específica do mês. </p> <p> <span class="uicontrol"> Anualmente</span>: especifica o dia do ano em que o relatório é enviado, ou você pode enviar em um dia específico da semana em qualquer semana do ano. </p> <p> <span class="uicontrol"> Hora do dia</span>: aplica-se ao fuso horário anexado ao conjunto de relatórios selecionado. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Opções de finalização de entrega</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Nunca finalizar</span>: sem prazo final. </p> <p> <span class="uicontrol"> Terminar após &lt;value&gt; ocorrências</span>: especifica o número de ocorrências antes de terminar a entrega. </p> <p> <span class="uicontrol"> Finalizar em</span>: permite especificar uma data específica. </p> <p>Se você desejar processar os dados na mesma data dos dados do relatório, o relatório conterá somente os dados que foram inseridos no banco de dados do no momento em que o relatório for enviado. Como o processamento completo para um dia pode demorar até 24 horas, os dados completos podem não estar disponíveis no momento em que o relatório é enviado. Para obter os dados completos, sempre defina o tempo de processamento durante 24 horas após o término do período do relatório. </p> </td> 
   </tr> 
   </table>

## Imprimir um relatório {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Etapas que descrevem como imprimir um relatório.

<!-- 

t_reports_print.xml

 -->

1. Executar um relatório.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Print]**.  ![](assets/print.png)

## Baixar um relatório com as opções básicas {#task_43660107A1C9485D92981CD75B562577}

Baixe informações detalhadas sobre um relatório específico nos formatos PDF, CSV, Excel ou Exportação de dados brutos.

<!-- 

t_download-report.xml

 -->

1. Em **Análises** &gt; **[!UICONTROL Relatórios]**, selecione um relatório a ser exibido.
1. Clique em **[!UICONTROL Baixar]**.

   ![](assets/download_basic.png)

1. Selecionar o formato desejado para o relatório:

   * **[!UICONTROL PDF]**: especifica que o relatório será baixado no formato Adobe PDF e permite compartilhar o relatório com outras pessoas, independentemente do sistema de computador usado.
   * **[!UICONTROL CSV]**: Especifica que o relatório será descarregado em [!DNL .csv] (formato de valores separados por vírgula).
   * **[!UICONTROL Excel]**: especifica que o relatório será baixado no formato do Microsoft Excel e permite compartilhar o relatório com outras pessoas que podem abri-lo em um programa de planilhas.
   * **[!UICONTROL Word]**: especifica que o relatório será baixado no formato do Microsoft Word.
   >[!NOTE]
   >
   >Se você usar um dos formatos de exportação brutos para baixar um relatório e o nome da página estiver em branco, o Adobe Analytics provavelmente não terá tempo suficiente para processar os dados. Baixe o relatório posteriormente.

## Gerenciar relatórios programados {#task_C17677C543454FF2B06D10EA5652DFBC}

Informações sobre como gerenciar relatórios agendados.

<!-- 

t_schedule_manage.xml

 -->

No [!UICONTROL Gerenciador de agendamento de relatório], é possível editar e excluir entregas de relatório recorrentes. Você pode criar prazos de entrega, que enviam seus relatórios via email ou FTP para um endereço especificado. Você pode configurar esses horários para enviar automaticamente relatórios em intervalos especificados por um período de tempo ou indefinidamente, ou interromper a entrega de um relatório periódico.

O [!UICONTROL Gerenciador de agendamento de relatório] mostra os itens criados por um usuários específico. Se a conta de usuário estiver desabilitada na aplicação, todas as entregas programadas são interrompidas.

1. To access the manager, click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**.

## Compartilhar um link de relatório {#task_9711DDE9E140451B8C914EC5513E21EC}

Etapas que descrevem como compartilhar um relatório gerando um link de relatório (URL) para enviar a outro usuário.

<!-- 

t_reports_share_link.xml

 -->

Quando o destinatário clica no link, o sistema solicita ao as credenciais de logon (nome da empresa, nome de usuário e senha). Após o logon, o relatório gerado pelo usuário original é exibido ao destinatário. Restrições de permissão padrão se aplicam.

**Compartilhamento de um link de relatório**

1. Executar um relatório.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Link to This Report]**.

## Cancelar inscrição nos relatórios agendados {#concept_6B48360F935740B6851BA85D32DEF637}

É possível cancelar sua inscrição nos relatórios agendados. Você não vai mais receber os relatórios, mesmo que seu nome de usuário seja adicionado ao relatório agendado novamente.

<!-- 

t_schedule_unsubscribe.xml

 -->

>[!IMPORTANT]
>
>Para que você possa receber novamente o relatório, é necessário criar um novo agendamento.

Para cancelar a inscrição de um relatório agendado:

1. Vá até o email com o link para o relatório cuja inscrição você deseja cancelar.

   ![](assets/unsubscribe-email.png)

1. Clique no link **[!UICONTROL clique aqui]**, ao lado de **[!UICONTROL Cancelar entrega automática deste relatório]**.

1. Confirme que você deseja cancelar a entrega do relatório.

   >[!NOTE]
   >
   >Esse fluxo de trabalho é o mesmo se você for o agendador do relatório ou o destinatário do relatório.

Cancelar a inscrição no relatório não cancela o relatório agendado.

Para cancelar um relatório agendado, navegue até o Gerenciador de agendamentos e clique no X vermelho ao lado do nome do relatório. [Mais...](../../analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
