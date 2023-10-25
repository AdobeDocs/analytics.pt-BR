---
description: O Gerenciador de solicitações permite que você visualize, duplique e priorize novamente as solicitações.
title: Gerenciar solicitações do Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: 195750917731602ffd3a32f5216db8fe1b174cc0
workflow-type: tm+mt
source-wordcount: '1293'
ht-degree: 13%

---

# Gerenciar solicitações do Data Warehouse

{{release-limited-testing}}

>[!NOTE]
>
>Se sua organização ainda não tiver a nova experiência do Data Warehouse, que estará disponível em breve para todos os clientes, use as informações em [Gerenciar solicitações de Data Warehouse (experiência antiga)](#manage-data-warehouse-requests-old-experience) na parte inferior desta página.


Você pode exibir e gerenciar solicitações de Data Warehouse feitas. Somente administradores podem visualizar e gerenciar solicitações feitas por outros usuários em suas organizações.

As seções a seguir descrevem as atividades que você pode executar ao gerenciar solicitações.

## Exibir solicitações

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

   A página Data Warehouse exibe todas as solicitações que você fez. <!-- just those you have made? -->Os dados são mostrados em cada coluna. Você pode [configurar quais colunas](#configure-columns) são visíveis.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Opcional) Clique no nome da solicitação para exibir uma caixa de diálogo que exibe as seguintes informações: <!-- Check this -->

   * Quando uma solicitação iniciou o processamento

   * Taxa limitada: sua organização tem muitas solicitações de Data Warehouse em execução. A solicitação é pausada até que outras solicitações de dados sejam concluídas.

## Editar solicitações

Considere o seguinte ao editar solicitações:

* Somente as solicitações configuradas para serem executadas de acordo com um agendamento podem ser editadas.

* Nem todos os campos associados à solicitação podem ser editados. Os campos que não podem ser editados estão esmaecidos.

* Os administradores que editam a solicitação de outro usuário precisam escolher uma nova conta e um local que possam acessar.

Para editar uma solicitação programada:

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação que deseja editar.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecione [!UICONTROL **Editar**].

1. Edite a solicitação conforme desejado. As opções de configuração esmaecidas não podem ser editadas.

   Para obter informações sobre cada opção de configuração, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Selecionar [!UICONTROL **Salvar alterações**].

## Visualizar o histórico de uma solicitação

Você pode exibir o histórico de qualquer solicitação de Data Warehouse feita.

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação cujo histórico você deseja exibir.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecionar [!UICONTROL **Exibir histórico**].

   A variável [!UICONTROL **Exibir solicitação de Data Warehouse**] A página exibe uma lista de deliveries de relatório individuais associados à solicitação.

   Selecione o **Configurar coluna** ícone ![Ícone Configurar coluna](assets/configure-column-icon.png) para ocultar colunas ou mostrar colunas que não são exibidas por padrão.

   ![Página Histórico de solicitações](assets/dw-request-history.png)

   As seguintes colunas estão disponíveis:

   | Coluna | Descrição |
   |---------|----------|
   | [!UICONTROL **Data de criação**] | A data e a hora em que o relatório foi criado.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Data de início**] | A data e a hora em que o relatório foi iniciado.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Data de conclusão**] | A data e a hora em que o relatório foi concluído.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Data de atualização**] | A data e a hora em que o relatório foi atualizado pela última vez.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Status**] | O status da entrega do relatório. Os status possíveis são:<ul><li>[!UICONTROL **Criado em**]: o relatório foi criado, mas ainda não foi processado.</li><li>[!UICONTROL **Pending**]: o relatório está aguardando para ser processado.</li><li>[!UICONTROL **Processando**]: O relatório está sendo processado no momento.</li><li>[!UICONTROL **Concluído**]: o relatório foi concluído e agora está disponível.</li><li>[!UICONTROL **Agendado**]: O relatório está agendado, mas ainda não foi iniciado.</li><li>[!UICONTROL **Cancelado**]: o relatório foi cancelado pelo usuário.</li><li>[!UICONTROL **Erro - Processamento**:] O relatório encontrou um erro e não pôde ser processado.</li><li>[!UICONTROL **Erro - Falha Ao Enviar**]: o relatório foi gerado com sucesso, mas não pôde ser entregue. Verifique a [configuração do seu destino](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), em seguida, reenvie o relatório.</li></ul>. |
   | [!UICONTROL **De**] | A data de início do período geral incluído no relatório.<p>Exibido no fuso horário do conjunto de relatórios.</p> |
   | [!UICONTROL **Para**] | A data final do período geral incluído no relatório. <p>Exibido no fuso horário do conjunto de relatórios.</p> |
   | [!UICONTROL **ID da solicitação herdada**] | A ID usada para identificar um relatório na interface herdada do Data Warehouse. Essa ID pode ser necessária ao entrar em contato com o Atendimento ao cliente do Adobe. |
   | [!UICONTROL **ID do relatório**] | A ID usada para identificar um relatório na interface de Data Warehouse atual. Essa ID pode ser necessária ao entrar em contato com o Atendimento ao cliente do Adobe. |


1. Selecione um delivery de relatório e, em seguida, selecione qualquer uma das seguintes opções:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Detalhes do destino**] | Mostra os detalhes da conta e do local associados à solicitação. Esta é a conta e o local configurados anteriormente, conforme descrito em [Configurar um destino de relatório para uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Cancelar relatório**] | Cancela o relatório. Não é possível cancelar relatórios com status de [!UICONTROL **Concluído**] ou [!UICONTROL **Cancelado**]. |
   | [!UICONTROL **Executar relatório novamente**] | Executa o relatório novamente com os dados como estavam quando foi originalmente enviado. Você pode executar novamente um relatório que tenha qualquer um dos seguintes status: [!UICONTROL **Cancelado**], [!UICONTROL **Concluído**], [!UICONTROL **Erro - Processamento**] ou [!UICONTROL **Erro - Falha Ao Enviar**]. |
   | [!UICONTROL **Reenviar relatório**] | Reenvia o arquivo de relatório gerado anteriormente. Você pode reenviar um relatório que tenha qualquer um dos seguintes status: [!UICONTROL **Concluído**] ou [!UICONTROL **Erro - Falha Ao Enviar**]. |

## Copiar solicitações

Ao copiar uma solicitação, todas as opções de configuração são copiadas da solicitação original.

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação que deseja copiar.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecionar [!UICONTROL **Copiar**].

   A página Copiar solicitação de Data Warehouse é exibida. Todas as opções de configuração são copiadas da solicitação original.

1. Atualize todas as opções de configuração associadas à solicitação.

   Para obter informações sobre cada opção de configuração, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Selecionar [!UICONTROL **Salvar alterações**].

## Cancelar solicitações

Somente solicitações configuradas para serem executadas de acordo com um agendamento podem ser canceladas.

Para cancelar uma solicitação programada:

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação que deseja editar.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecionar [!UICONTROL **Cancelar**].

   A solicitação não será mais executada no horário agendado.

## Configurar colunas

Você pode configurar quais informações serão exibidas para cada solicitação adicionando ou removendo colunas.

1. Selecione o **Configurar colunas** no canto superior direito da página do Data Warehouse.

   ![Configurar colunas](assets/dw-configure-columns.png)

   As seguintes colunas estão disponíveis:

   | Coluna disponível | Descrição |
   |---------|----------|
   | Nome da solicitação | O nome da pessoa que criou a solicitação. |
   | Conjunto de relatórios | O conjunto de relatórios associado à solicitação. |
   | Solicitado por | O usuário que criou a solicitação. |
   | Data da solicitação | A data em que a solicitação foi feita. |
   | Status | Os seguintes status estão disponíveis:<ul><li><p>**Concluído**: A solicitação foi executada com sucesso.</p></li><li><p>**Cancelado**: a solicitação foi cancelada pelo usuário.</p></li><li><p>**Agendado**: a solicitação é configurada para ser executada de acordo com um agendamento.</p></li><!-- Are there other statuses? Failed? --> |

   {style="table-layout:auto"}

1. Certifique-se de que todas as colunas que deseja exibir estejam selecionadas. As colunas selecionadas são exibidas na página Data Warehouse e exibem as informações relevantes.

## Filtrar e classificar solicitações

1. Selecione o **Filtro** no painel esquerdo da página de Data Warehouse.

   ![Filtrar solicitações](assets/dw-filter.png)

1. Expanda a [!UICONTROL **Conjuntos de relatórios**], [!UICONTROL **Proprietário**] ou [!UICONTROL **Status**] seções e, em seguida, selecione como deseja filtrar as solicitações.

## Pesquisar solicitações

1. No campo de pesquisa na parte superior da página Data Warehouse, especifique o nome da solicitação que deseja exibir.

   As solicitações são filtradas à medida que você digita.

## Gerenciar solicitações de Data Warehouse (experiência antiga)

>[!NOTE]
>
>As informações a seguir se aplicam somente se sua organização ainda não tiver a nova experiência do Data Warehouse, que estará disponível em breve para todos os clientes do Analytics.


O Gerenciador de solicitações permite que você visualize, duplique e priorize novamente as solicitações.

No Data Warehouse, selecione a guia **[!UICONTROL Gerenciador de solicitações]**.

Esta tabela permite

* Visualizar solicitações de relatório recentes por nome de relatório, segmento aplicado, solicitador, data e status de solicitação.
* Duplicar solicitações. Clique em **[!UICONTROL Duplicar]** ao lado da solicitação.

  >[!NOTE]
  >
  >Esta ação duplica somente a solicitação, não o agendamento ou os detalhes de disponibilização.

* Pesquise por relatórios pelo nome ou o logon do solicitador.
* Priorize novamente os relatórios; basta arrastá-los e soltá-los em um novo local na fila.
* Para ver quando um uma solicitação começou a ser processada, clique em uma ID de solicitação agendada e verifique o pop-up aberto.

Clique em uma tarefa para ver as solicitações individuais dessa tarefa.

* Taxa limitada: sua organização tem muitas solicitações de Data Warehouse em execução. A solicitação é pausada até que outras solicitações de dados sejam concluídas.