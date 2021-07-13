---
description: No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.
title: Opções do Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 100%

---

# Opções do Report Builder

No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.

1. Na barra de ferramentas de Suplementos, clique em **[!UICONTROL Opções]** ![](assets/options_icon.png)

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL Data de início] |  |
| Definir com a data atual | Você pode especificar ou redefinir a [!UICONTROL Data de início], de forma que o Report Builder use a data atual ou solicite a data a ser usada na atualização. |
| Solicitar a definição ao atualizar | Permite definir a [!UICONTROL Data de início] ao atualizar uma solicitação. |
| [!UICONTROL Recenticidade dos dados] |  |
| [!UICONTROL Incluir os dados atuais] | Permite ver a latência de dados (também conhecida como [!UICONTROL Recenticidade dos dados]) até o minuto no relatório, por vezes até mesmo antes dos dados serem processados pelo Adobe Analytics.<br>Quando você não usa essa opção, o modo finalizado (processado) é usado, o que geralmente é mais [latente](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=pt-BR).<br>Essa configuração se aplica a todas as solicitações na pasta de trabalho de dados atuais compatíveis. Se a solicitação não for compatível, o modo finalizado é aplicado.<br>Observe as seguintes situações para usar o [!UICONTROL modo Incluir dados] atuais:<br>**Opções de formato**: Você pode especificar se essa informação deverá ser exibida ([!UICONTROL Recenticidade de dados]) ao [formatar cabeçalhos de exibição](/help/analyze/report-builder/layout/t-format-display-headers.md).<br>**Divisões**: Não suportado. Se o modo [!UICONTROL Recenticidade dos dados] estiver definido para os Dados atuais e uma das solicitações tiver um elemento de divisão, essa solicitação será revertida para o modo de dados não atuais. Contudo, as demais solicitações continuam usando o modo de Dados atuais.<br>**Gerenciador de solicitação**: Você pode visualizar uma coluna de Dados atuais no Gerenciador de solicitação para conseguir ver se a configuração foi aplicada a uma solicitação programada.<br>**Pastas de trabalho programadas**: Esse modo é armazenado durante o processo de programação no nível da pasta de trabalho. Se você abrir uma pasta de trabalho programada que estiver usando dados finalizados e aplicar [!UICONTROL Incluir dados atuais], o modo atual será usado a partir de então.<br>**Permissões**: Essa opção fica omitida para usuários que não tenham acesso aos dados atuais.  Ao ativar essa opção, se uma ou mais solicitações não puderem ser aplicadas, um aviso será emitido. |
| Desativar avisos de solicitação de dados atuais incompatível | Exibe avisos se o modo [!UICONTROL Incluir os dados atuais] estiver selecionado, mas o modo de dados não puder ser aplicado à solicitação editada.  Por exemplo, se você definir [!UICONTROL Incluir os dados atuais] e, em seguida, editar uma solicitação que possua um segmento selecionado, um aviso será emitido. |
| Registrar solicitações do Report Builder no arquivo local (para resolução de problemas) | Permite registrar solicitações em um arquivo local. Use esse arquivo de log para resolução de problemas. |
| Interpretar o valor digitado... | Interprete o valor digitado no controle de filtro como um local de célula antes de considerá-lo uma expressão de filtro.<br>Por exemplo, se você criar uma solicitação As 10 páginas principais, usando um filtro Sapatos, a solicitação exibiria uma célula contendo algo semelhante a:   Filtro: 1 a 10 páginas principais, Página contém Sapatos |
| Atualizar quando uma nova versão estiver disponível | Faz o sistema informar se uma nova versão estiver disponível para instalação. |
