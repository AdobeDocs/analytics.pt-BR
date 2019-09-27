---
description: No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.
seo-description: No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.
seo-title: Opções do Report Builder
solution: Analytics
title: Opções do Report Builder
topic: Construtor de relatórios
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Opções do Report Builder

No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL Data de início] |  |
| Definir com a data atual | Você pode especificar ou redefinir a [!UICONTROL Data de início], de forma que o Construtor de relatórios use a data atual ou solicite a data a ser usada na atualização. |
| Solicitar a definição ao atualizar | Permite definir a [!UICONTROL Data de início] ao atualizar uma solicitação. |
| [!UICONTROL Recenticidade dos dados] |  |
| [!UICONTROL Incluir os dados atuais] | Permite ver a latência de dados (também conhecida como [!UICONTROL Recenticidade dos dados]) até o minuto no relatório, por vezes até mesmo antes dos dados serem processados pelo Adobe Analytics.<br>Quando você não usa essa opção, o modo finalizado (processado) é usado, que geralmente é mais [latente](https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html).<br>Essa configuração se aplica a todas as solicitações na pasta de trabalho de dados atuais compatíveis. Se a solicitação não for compatível, o modo finalizado é aplicado.<br>Observe as seguintes situações para usar o modo [!UICONTROL Incluir dados] atuais:Opções<br>**** de formato: Você pode especificar se deseja exibir essas informações (Idade[!UICONTROL dos]dados) ao [formatar cabeçalhos](../../analyze/report-builder/layout/t-format-display-headers.md)de exibição.<br>**Divisões**: Não suportado. Se o modo [!UICONTROL Recenticidade dos dados] estiver definido para os Dados atuais e uma das solicitações tiver um elemento de divisão, essa solicitação será revertida para o modo de dados não atuais. Contudo, as demais solicitações continuam usando o modo de Dados atuais.<br>**Gerenciador de solicitação**: Você pode visualizar uma coluna de Dados atuais no Gerenciador de solicitação para conseguir ver se a configuração foi aplicada a uma solicitação programada.<br>**Pastas de trabalho programadas**: Esse modo é armazenado durante o processo de programação no nível da pasta de trabalho. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Permissões**: Essa opção fica omitida para usuários que não tenham acesso aos dados atuais.  Ao ativar essa opção, se uma ou mais solicitações não puderem ser aplicadas, um aviso será emitido. |
| Desativar avisos de solicitação de dados atuais incompatível | Exibe avisos se o modo [!UICONTROL Incluir os dados atuais] estiver selecionado, mas o modo de dados não puder ser aplicado à solicitação editada.  Por exemplo, se você definir [!UICONTROL Incluir os dados atuais] e, em seguida, editar uma solicitação que possua um segmento selecionado, um aviso será emitido. |
| Registrar solicitações do Construtor de relatórios no arquivo local (para resolução de problemas) | Permite registrar solicitações em um arquivo local. Use esse arquivo de log para resolução de problemas. |
|  Interpretar o valor digitado... | Interprete o valor digitado no controle de filtro como um local de célula antes de considerá-lo uma expressão de filtro.<br>Por exemplo, se você criar uma solicitação Top 10 Page, usando um filtro de sapatos, a solicitação exibiria uma célula contendo algo semelhante a:   Filtro: 1 a 10 páginas principais, Página contém Sapatos |
| Atualizar quando uma nova versão estiver disponível | Faz o sistema informar se uma nova versão estiver disponível para instalação. |
