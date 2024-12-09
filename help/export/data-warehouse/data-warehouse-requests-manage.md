---
description: Saiba como visualizar, duplicar e priorizar novamente as solicitações do Data Warehouse.
title: Gerenciar solicitações do Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 3%

---

# Gerenciar solicitações do Data Warehouse

Você pode exibir e gerenciar solicitações de Data Warehouse feitas. Somente administradores podem visualizar e gerenciar solicitações feitas por outros usuários em suas organizações.

As seções a seguir descrevem as atividades que você pode executar ao gerenciar solicitações.

## Exibir solicitações

Por padrão, você pode exibir somente as solicitações que criar, a menos que os usuários tenham optado por tornar suas solicitações visíveis para outras pessoas na organização (conforme descrito em [configurações gerais da solicitação do Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md)). Os administradores do sistema podem exibir todas as solicitações.

Para exibir solicitações de Data Warehouse:

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

   A página Data Warehouse exibe todas as solicitações que você fez. Os dados são mostrados em cada coluna. Você pode [configurar quais colunas](#configure-columns) estão visíveis.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Opcional) Clique no nome da solicitação para exibir uma caixa de diálogo que exibe as seguintes informações: <!-- Check this -->

   * Quando uma solicitação iniciou o processamento

   * Taxa limitada: sua organização tem muitas solicitações de Data Warehouse em execução. A solicitação é pausada até que outras solicitações de dados sejam concluídas.

## Editar solicitações

Considere o seguinte ao editar solicitações:

* Somente as solicitações configuradas para serem executadas de acordo com um agendamento podem ser editadas.

* Nem todos os campos associados à solicitação podem ser editados. Os campos que não podem ser editados estão esmaecidos.

* Os administradores que editam a solicitação de outro usuário devem escolher uma nova conta e um novo local que possam acessar.

Para editar uma solicitação programada:

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação que deseja editar.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecione [!UICONTROL **Editar**].

1. Edite a solicitação conforme desejado. As opções de configuração esmaecidas não podem ser editadas.

   Para obter informações sobre cada opção de configuração, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Selecione [!UICONTROL **Salvar alterações**].

## Visualizar o histórico de uma solicitação

Você pode exibir o histórico de qualquer solicitação de Data Warehouse feita.

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação cujo histórico você deseja exibir.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecione [!UICONTROL **Exibir histórico**].

   A página [!UICONTROL **Exibir solicitação de Data Warehouse**] exibe uma lista de entregas de relatórios individuais associadas à solicitação.

   Selecione o ícone **Configurar coluna** ![Configurar ícone de coluna](assets/configure-column-icon.png) para ocultar colunas ou mostrar colunas que não são exibidas por padrão.

   ![Solicitar página de histórico](assets/dw-request-history.png)

   As seguintes colunas estão disponíveis:

   | Coluna | Descrição |
   |---------|----------|
   | [!UICONTROL **Data de criação**] | A data e a hora em que o relatório foi criado.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Data de início**] | A data e a hora em que o relatório foi iniciado.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Data de conclusão**] | A data e a hora em que o relatório foi concluído.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Data de atualização**] | A data e a hora em que o relatório foi atualizado pela última vez.<p>Exibido no fuso horário do usuário que iniciou a solicitação.</p> |
   | [!UICONTROL **Status**] | O status da entrega do relatório. Os status possíveis são:<ul><li>[!UICONTROL **Criado**]: o relatório foi criado mas ainda não foi processado.</li><li>[!UICONTROL **Pendente**]: o relatório está aguardando para ser processado.</li><li>[!UICONTROL **Processando**]: o relatório está sendo processado no momento.</li><li>[!UICONTROL **Concluído**]: o relatório foi concluído e está disponível agora.</li><li>[!UICONTROL **Agendado**]: o relatório está agendado, mas ainda não foi iniciado.</li><li>[!UICONTROL **Cancelado**]: O relatório foi cancelado pelo usuário.</li><li>[!UICONTROL **Erro - Processando**:] O relatório encontrou um erro e não pôde ser processado.</li><li>[!UICONTROL **Erro - Falha ao Enviar**]: o relatório foi gerado com êxito, mas não pôde ser entregue. Verifique a [configuração do seu destino](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) e reenvie o relatório.</li></ul>. |
   | [!UICONTROL **De**] | A data de início do período geral incluído no relatório.<p>Exibido no fuso horário do conjunto de relatórios.</p> |
   | [!UICONTROL **Para**] | A data final do período geral incluído no relatório. <p>Exibido no fuso horário do conjunto de relatórios.</p> |
   | [!UICONTROL **ID da solicitação herdada**] | A ID usada para identificar um relatório na interface herdada do Data Warehouse. Essa ID pode ser necessária ao entrar em contato com o Atendimento ao cliente do Adobe. |
   | [!UICONTROL **ID do Relatório**] | A ID usada para identificar um relatório na interface de Data Warehouse atual. Essa ID pode ser necessária ao entrar em contato com o Atendimento ao cliente do Adobe. |


1. Selecione um delivery de relatório e, em seguida, selecione qualquer uma das seguintes opções:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Detalhes do destino**] | Mostra os detalhes da conta e do local associados à solicitação. Esta é a conta e o local configurados anteriormente, conforme descrito em [Configurar um destino de relatório para uma solicitação de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Cancelar relatório**] | Cancela o relatório. Você não pode cancelar relatórios com status de [!UICONTROL **Concluído**] ou [!UICONTROL **Cancelado**]. |
   | [!UICONTROL **Executar relatório novamente**] | Executa o relatório novamente com os dados como estavam quando foi originalmente enviado. Você pode executar novamente um relatório que tenha qualquer um dos seguintes status: [!UICONTROL **Cancelado**], [!UICONTROL **Concluído**], [!UICONTROL **Erro - Processando**] ou [!UICONTROL **Erro - Falha ao Enviar**]. |
   | [!UICONTROL **Reenviar relatório**] | Reenvia o arquivo de relatório gerado anteriormente. Você pode reenviar um relatório que tenha qualquer um dos seguintes status: [!UICONTROL **Concluído**] ou [!UICONTROL **Erro - Falha ao Enviar**]. |

## Copiar solicitações

Ao copiar uma solicitação, todas as opções de configuração são copiadas da solicitação original.

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação que deseja copiar.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecione [!UICONTROL **Copiar**].

   A página Copiar solicitação de Data Warehouse é exibida. Todas as opções de configuração são copiadas da solicitação original.

1. Atualize todas as opções de configuração associadas à solicitação.

   Para obter informações sobre cada opção de configuração, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Selecione [!UICONTROL **Salvar alterações**].

## Cancelar solicitações

Somente solicitações configuradas para serem executadas de acordo com um agendamento podem ser canceladas.

Para cancelar uma solicitação programada:

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página Data Warehouse, selecione a solicitação que deseja editar.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecione [!UICONTROL **Cancelar**].

   A solicitação não será mais executada no horário agendado.

## Configurar colunas

Você pode configurar quais informações serão exibidas para cada solicitação adicionando ou removendo colunas.

1. Selecione o ícone **Configurar colunas** no canto superior direito da página de Data Warehouse.

   ![Configurar colunas](assets/dw-configure-columns.png)

   As seguintes colunas estão disponíveis:

   | Coluna disponível | Descrição |
   |---------|----------|
   | Nome da solicitação | O nome da pessoa que criou a solicitação. |
   | Conjunto de relatórios | O conjunto de relatórios associado à solicitação. |
   | Solicitado por | O usuário que criou a solicitação. |
   | Data da solicitação | A data em que a solicitação foi feita. |
   | Status | Os seguintes status estão disponíveis:<ul><li><p>**Concluída**: a solicitação foi executada com êxito.</p></li><li><p>**Cancelada**: a solicitação foi cancelada pelo usuário.</p></li><li><p>**Agendada**: a solicitação está configurada para ser executada de acordo com um agendamento.</p></li><li><p>**Falha**: falha ao concluir a solicitação. Se a solicitação continuar a falhar, entre em contato com o Suporte ao cliente.</p></li></ul> |

   {style="table-layout:auto"}

1. Certifique-se de que todas as colunas que deseja exibir estejam selecionadas. As colunas selecionadas são exibidas na página Data Warehouse e exibem as informações relevantes.

## Filtrar e classificar solicitações

1. Selecione o ícone **Filtro** no painel esquerdo da página de Data Warehouse.

   ![Filtrar solicitações](assets/dw-filter.png)

1. Expanda as seções [!UICONTROL **Conjuntos de relatórios**], [!UICONTROL **Proprietário**] ou [!UICONTROL **Status**] e selecione como deseja filtrar as solicitações.

## Pesquisar solicitações

1. No campo de pesquisa na parte superior da página Data Warehouse, especifique o nome da solicitação que deseja exibir.

   As solicitações são filtradas à medida que você digita.