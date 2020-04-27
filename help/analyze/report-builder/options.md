---
description: No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.
title: Opções do Report Builder
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Opções do Report Builder

No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Definir com a data atual | Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh. |
| Solicitar a definição ao atualizar | Permite definir o [!UICONTROL As Of Date] ao atualizar uma solicitação. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>Quando você não usa essa opção, o modo finalizado (processado) é usado, o que geralmente é mais [latente](https://marketing.adobe.com/resources/help/pt_BR/reference/data_latency.html).<br>Essa configuração se aplica a todas as solicitações na pasta de trabalho de dados atuais compatíveis. Se a solicitação não for compatível, o modo finalizado é aplicado.<br>Observe as seguintes situações para usar o [!UICONTROL Include Current Data] modo:Opções<br>****de formato: Você pode especificar se deseja exibir essas informações ([!UICONTROL Data Recency]) ao[formatar cabeçalhos](/help/analyze/report-builder/layout/t-format-display-headers.md)de exibição.<br>**Divisões**: Não suportado. If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. Contudo, as demais solicitações continuam usando o modo de Dados atuais.<br>**Gerenciador de solicitação **: Você pode visualizar uma coluna de Dados atuais no Gerenciador de solicitação para conseguir ver se a configuração foi aplicada a uma solicitação programada.<br>**Pastas de trabalho programadas**: Esse modo é armazenado durante o processo de programação no nível da pasta de trabalho. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Permissões **: Essa opção fica omitida para usuários que não tenham acesso aos dados atuais.  Ao ativar essa opção, se uma ou mais solicitações não puderem ser aplicadas, um aviso será emitido. |
| Desativar avisos de solicitação de dados atuais incompatível | Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued. |
| Registrar solicitações do Report Builder no arquivo local (para resolução de problemas) | Permite registrar solicitações em um arquivo local. Use esse arquivo de log para resolução de problemas. |
| Interpretar o valor digitado... | Interprete o valor digitado no controle de filtro como um local de célula antes de considerá-lo uma expressão de filtro.<br>Por exemplo, se você criar uma solicitação As 10 páginas principais, usando um filtro Sapatos, a solicitação exibiria uma célula contendo algo semelhante a:   Filtro: 1 a 10 páginas principais, Página contém Sapatos |
| Atualizar quando uma nova versão estiver disponível | Faz o sistema informar se uma nova versão estiver disponível para instalação. |
