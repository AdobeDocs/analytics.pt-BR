---
description: Informações sobre agendamento, download e distribuição de relatórios.
subtopic: Schedule
title: Agendamento e distribuição de relatórios
topic: Reports and analytics
uuid: 1230b0f3-e026-4b83-b231-14d6f75a3836
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Agendamento e distribuição de relatórios

Informações sobre agendamento, download e distribuição de relatórios.

Ao agendar um relatório para delivery em um aplicativo do Adobe Analytics, você pode usar as ferramentas de Agendamento e Distribuição para visualização de quais arquivos foram automaticamente enviados e modificar ou encerrar os delivery.

Devido às diferenças nos mecanismos e plataformas de processamento, os vários tipos de relatórios disponíveis para download e agendados no Adobe Analytics têm diferentes limitações em relação ao número máximo de linhas que podem ser processadas em uma única solicitação. Estes são os limites de cada:

* Word, CSV, Excel, HTML e PDF: O mesmo número de linhas visíveis no relatório. Por padrão, esse limite é de 50 linhas, mas pode aumentar até 200. Os relatórios de detalhamento têm um limite rígido de 50 linhas.
* Extrações de dados: 50.000 linhas
* Data Warehouse: Ilimitado

Essas limitações referem-se a relatórios individuais agendados e baixados; os painéis são limitados à quantidade de espaço disponível em um reportlet.

>[!NOTE] O &quot;Tempo de entrega&quot;/&quot;Horário do dia&quot; inserido pelo usuário especifica o horário em que o relatório deve começar a ser processado, e não o horário em que ele será realmente entregue. O horário real em que o relatório será entregue baseia-se principalmente no tempo necessário para o processamento (relatórios complexos e grandes demoram mais para serem processados do que relatórios mais simples). Por exemplo, se um relatório levar 15 minutos para ser processado, o tempo de entrega real será de pelo menos 15 minutos depois do &quot;Tempo de entrega&quot;/&quot;Horário do dia&quot; especificado originalmente.
>Além disso, existem outros fatores que podem aumentar ainda mais o atraso antes que o relatório seja efetivamente entregue:
>
> * **Execução de vários agendamentos diferentes do mesmo tipo ao mesmo tempo** (por exemplo, muitos painéis, etc.) pode sobrecarregar o sistema. O sistema de Agendamento permite que apenas alguns (5-10) relatórios de qualquer tipo sejam executados simultaneamente. Portanto, quando mais de 5-10 forem agendados de uma só vez, alguns precisarão aguardar a conclusão de outros relatórios para que possam começar o processamento. Esse problema pode ser resolvido agendando os relatórios de uma empresa em momentos alternados ao longo do dia ou da hora, em vez de simultaneamente.
> * Além do tipo de relatório específico (Painéis, etc.), os relatórios também aguardam na fila se a empresa tiver **mais de 15 a 20 de qualquer tipo de relatório agendado de uma só vez (em todos os tipos de relatório diferentes)**. Esse problema pode ser resolvido alternando os horários de agendamento, em vez de executar muitos exatamente ao mesmo tempo.
> * **Problemas nos serviços downstream** de que o Agendador depende também podem afetar a entrega de relatórios. Por exemplo, se você estiver usando as APIs de maneira independente para executar relatórios e preencher a fila de solicitações de API, os relatórios agendados podem ser entregues lentamente enquanto você concorre por esse recurso.
> * A **latência do conjunto de relatórios** (um atraso na coleta de dados) também pode atrasar alguns relatórios agendados.



## Enviar um relatório {#task_27642CD33D484FD0BF59EBD159EEF52C}

Etapas que descrevem como fazer o download e enviar por email relatórios em vários formatos, além de agendar a entrega de um relatório.

1. Run a report, then click **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Especifique as opções de entrega:

   | Opção | Descrição |
   |--- |--- |
   | Formato | Selecione PDF ou HTML. |
   | Enviar para | Forneça um endereço de email para receber o relatório. |
   | Assunto | Assunto do email. |
   | Agendamento | Selecione para enviar o relatório imediatamente ou em um intervalo diferente. |

1. Clique **[!UICONTROL Advanced Delivery Options]** para especificar um agendamento de delivery.

| Opção | Descrição |
|--- |--- |
| Nome do arquivo de relatório | Especifica o nome do relatório. O formato padrão é `<report name> for <suite> - <report date range>`. Para especificar um nome personalizado, selecione [!UICONTROL Custom]. |
| Formato do relatório | Permite que você especifique formatos PDF, CSV, Excel, HTML, Word ou Móvel para o delivery. Se você selecionar CSV, também poderá especificar a codificação para CSV:<ul><li>Shift-JIS: codificação de caracteres japoneses.</li><li>EUC-JP: código Unix Extended, principalmente para japonês, coreano e chinês simplificado.</li></ul> |
| Conteúdos do relatório | <ul><li>Número de linhas na tabela: especifique o número de linhas que devem ficar visíveis na tabela do relatório que você está enviando.</li><li>Idioma para cabeçalho e rodapé: especifique o idioma para o cabeçalho e rodapé.</li><li>comentários: especifique o texto a ser exibido no começo do relatório.</li></ul> |
| Enviar arquivo de assinatura digital | Quando você solicita um relatório, como um relatório marcado ou solicitações do Data Warehouse, é possível solicitar uma assinatura de dados. A assinatura digital da Adobe não restringe quem tem acesso aos dados, mas a finalidade do Arquivo de assinatura digital (.sig) é verificar a validade do arquivo de relatório fornecido. Usando a assinatura digital, os recipient de relatório podem verificar se o arquivo veio da Adobe e não foi alterado. |
| Destino do Relatório | <ul><li>Email: permite definir as configurações de endereço de email, o assunto e notas.</li><li>FTP: permite configurar as definições de FTP, incluindo o host, porta, diretório, nome de usuário e senha.</li></ul> |

1. Clique em **[!UICONTROL Scheduling Options]**.

| Opção | Descrição |
|--- |--- |
| Enviar relatório agora | Envia o relatório imediatamente. |
| Agendamento para mais tarde | Exibe opções para especificar um período e opções de delivery. |
| Intervalo de tempo dos relatórios | **Fixo**: impede que a data avance com o passar do tempo. **Rolagem**: Permite que a data avance com o passar do tempo. Algumas considerações:<ul><li>Se você selecionar Em andamento para as datas de início e fim, e selecionar um relatório diário para o dia anterior, você receberá um email diariamente com um relatório do dia anterior.</li><li>Se você selecionar Fixo como data de início e Em andamento como data de término, você receberá no primeiro dia um relatório do dia anterior. O segundo dia você receberá um relatório dos dois dias anteriores, no terceiro dia você receberá um relatório dos últimos três dias, e assim por diante.</li><li>Se você selecionar Fixo como datas de início e término, cada dia você receberá um relatório idêntico dos dias especificados.</li><li>Você não pode selecionar uma data de início em andamento e uma data de término fixa.</li></ul> |
| Frequência de entrega | <ul><li>**Por hora**: Fornece o e-mail a cada hora, a cada duas horas, ou qualquer outro intervalo de horas.</li><li>**Diariamente**: Envia o email todos os dias, em dias alternados, a cada três dias, ou qualquer outro intervalo de dias. Você também pode enviá-lo todos os dias da semana.</li><li>**Semanalmente**: Envia o email todas as semanas, outras semanas, a cada três semanas ou qualquer outro intervalo de semanas. Você também pode especificar qual dia da semana será enviado.</li><li>**Mensalmente**: Especifica o intervalo em números de meses e você também pode selecionar o dia do mês em que ele é enviado, ou o dia da semana em uma semana específica do mês.</li><li>**Anualmente**: Especifica o dia do ano em que o relatório é enviado ou você pode enviar em um dia específico da semana em qualquer semana do ano.</li><li>**Hora do dia**: Aplica-se ao fuso horário anexado ao conjunto de relatórios selecionado.</li></ul> |
| Opções de Finalização de Entrega | <ul><li>**Nunca terminar**: Especifica sem fim.</li><li>**Terminar após`value`ocorrências**: especifica o número de ocorrências antes de terminar a entrega.</li><li>**Finalizar em**: permite especificar uma data específica. Se você quiser processar os dados na mesma data dos dados do relatório, o relatório conterá somente os dados que foram inseridos no banco de dados no momento em que o relatório é enviado. Como o processamento completo de um dia pode levar até 24 horas, os dados completos podem não estar disponíveis no momento em que o relatório é enviado. Para dados completos, sempre defina o tempo de processamento por 24 horas após o término do período do relatórios.</li></ul> |

## Imprimir um relatório {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Etapas que descrevem como imprimir um relatório.

1. Executar um relatório.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Print]**.  ![](assets/print.png)

## Baixar um relatório com as opções básicas {#task_43660107A1C9485D92981CD75B562577}

Baixe informações detalhadas sobre um relatório específico nos formatos PDF, CSV, Excel ou Exportação de dados brutos.

1. Em **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** , selecione um relatório para visualização.
1. Clique em **[!UICONTROL Download]**.

   ![](assets/download_basic.png)

1. Selecionar o formato desejado para o relatório:

   * **[!UICONTROL PDF]**: especifica que o relatório será baixado no formato Adobe PDF e permite compartilhar o relatório com outras pessoas, independentemente do sistema de computador usado.
   * **[!UICONTROL CSV]**: especifica que o relatório será baixado em [!DNL .csv] (formato de valores separados por vírgula).
   * **[!UICONTROL Excel]**: Especifica que o relatório será baixado no formato do Microsoft Excel, que permite que você compartilhe o relatório com outras pessoas que podem abrí-lo em um programa de planilha.
   * **[!UICONTROL Word]**: Especifica que o relatório será baixado no formato do Microsoft Word.
   >[!NOTE]
   >
   >Se você usar um dos formatos de exportação básicos para baixar um relatório e o nome da página estiver em branco, o Adobe Analytics não terá tempo suficiente para processar os dados. Baixe o relatório posteriormente.

## Gerenciar relatórios programados {#task_C17677C543454FF2B06D10EA5652DFBC}

Informações sobre como gerenciar relatórios agendados.

No [!UICONTROL Schedule Reports Manager], é possível editar e excluir delivery de relatório recorrentes. Você pode criar programações de delivery que enviam seus relatórios por email ou FTP para um endereço especificado. Você pode configurar esses agendamentos para enviar automaticamente os relatórios em intervalos especificados por uma duração de tempo ou indefinidamente, ou interromper o delivery de um relatório periódico.

The [!UICONTROL Schedule Report Manager] shows the items that a specific user has created. Se a conta de usuário estiver desabilitada no aplicativo, todas as entregas programadas são interrompidas.

1. Para acessar o gerente, clique em **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**.

## Compartilhar um link de relatório {#task_9711DDE9E140451B8C914EC5513E21EC}

Etapas que descrevem como compartilhar um relatório gerando um link de relatório (URL) para enviar a outro usuário.

Quando o recipient clica no link, o sistema solicita credenciais de logon (nome da empresa, nome de usuário e senha). Depois de fazer logon, o recipient recebe o relatório gerado pelo usuário original. As restrições de permissão padrão se aplicam.

**Para compartilhar um link de relatório**

1. Executar um relatório.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Link to This Report]**.

## Cancelar inscrição nos relatórios agendados {#concept_6B48360F935740B6851BA85D32DEF637}

Você pode cancelar a inscrição de relatórios agendados. Você não receberá mais o relatório mesmo se o seu nome de usuário for adicionado novamente ao relatório agendado.

>[!IMPORTANT]
>
>Para que você possa receber o relatório novamente, é necessário criar um novo agendamento.

Para cancelar a assinatura de um relatório agendado:

1. Abra o email com o link para o relatório do qual você deseja cancelar a inscrição.

   ![](assets/unsubscribe-email.png)

1. Clique no **[!UICONTROL click here]** link ao lado de **[!UICONTROL To cancel automatic delivery of this report]**.

1. Confirme se você deseja cancelar o delivery do relatório.

   >[!NOTE]
   >
   >Esse fluxo de trabalho é o mesmo tanto para o agendador do relatório quanto para o destinatário do relatório.

Cancelar a inscrição no relatório não cancela o relatório agendado.

Para cancelar um relatório agendado, navegue até o Gerenciador de agendamentos e clique no X vermelho ao lado do nome do relatório. [Mais...](/help/analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
