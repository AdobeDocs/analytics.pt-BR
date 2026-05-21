---
description: Saiba mais sobre as opções do Report Builder.
title: Sobre as opções do Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
TQID: https://experienceleague.adobe.com/56Wyy-f9kDXxFSanTNILr4rNQ0OB3YtbIFPcRT082sc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 50%

---

# Opções do Report Builder

{{legacy-arb}}

No painel Opções, é possível especificar as configurações de datas, as configurações de latência (Dados atuais), as informações de log, e configurar as atualizações.

1. Na barra de ferramentas de Suplementos, clique em **[!UICONTROL Opções]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg):

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL Data de início] |  |
| Definir com a data atual | Você pode especificar ou redefinir a [!UICONTROL Data de início] para que a Report Builder use a data atual ou solicite a data a ser usada na atualização. |
| Solicitar a definição ao atualizar | Permite definir a [!UICONTROL Data de início] ao atualizar uma solicitação. |
| [!UICONTROL Recenticidade dos dados] |  |
| [!UICONTROL Incluir os dados atuais] | Permite ver a latência de dados (também conhecida como [!UICONTROL Recenticidade dos Dados]) até o minuto no relatório, por vezes até mesmo antes dos dados serem processados pela Adobe Analytics.<br>Quando você não usa essa opção, o modo finalizado (processado) é usado, o que geralmente é mais latente.<br>Essa configuração se aplica a todas as solicitações na pasta de trabalho de dados atuais compatíveis. Se a solicitação não for compatível, o modo finalizado é aplicado.<br>Anote as seguintes situações para usar o [!UICONTROL modo Incluir Dados Atuais]:<br>**Opções de Formato**: Você pode especificar se essa informação deverá ser exibida ([!UICONTROL Recenticidade dos Dados]) quando [formatar cabeçalhos de exibição](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md).<br>**Detalhamentos**: sem suporte. Se o modo [!UICONTROL Recenticidade dos dados] estiver definido para os Dados atuais e uma das solicitações tiver um elemento de divisão, essa solicitação será revertida para o modo de dados não atuais. No entanto, outras solicitações continuam usando o modo Dados atuais.<br>**Gerenciador de solicitação**: Você pode visualizar uma coluna de Dados atuais no Gerenciador de solicitação para conseguir ver se a configuração foi aplicada a uma solicitação programada.<br>**Pastas de trabalho programadas**: Esse modo é armazenado durante o processo de programação no nível da pasta de trabalho. Se você abrir uma pasta de trabalho agendada que estiver usando dados finalizados e aplicar [!UICONTROL Incluir Dados Atuais], o modo atual será usado a partir de então.<br>**Permissões**: para usuários que não têm acesso aos dados atuais, essa opção ficará oculta.  Ao ativar essa opção, se uma ou mais solicitações não puderem ser aplicadas, um aviso será emitido. |
| Desabilitar avisos de solicitação incompatível com Dados Atuais | Exibe avisos se o modo [!UICONTROL Incluir os dados atuais] estiver selecionado, mas o modo de dados não puder ser aplicado à solicitação editada.  Por exemplo, se você definir [!UICONTROL Incluir os dados atuais] e, em seguida, editar uma solicitação que possua um segmento selecionado, um aviso será emitido. |
| Registrar solicitações do Report Builder no arquivo local (para solução de problemas) | Permite registrar solicitações em um arquivo local. Use este arquivo de log para solucionar problemas. |
| Interpretar o valor digitado... | Interpreta um valor digitado em um controle de filtro como um local de célula antes de considerá-lo uma expressão de filtro.<br>Por exemplo, se você criar uma solicitação As 10 páginas principais, usando um filtro Sapatos, a solicitação exibiria uma célula contendo algo semelhante a:   Filtro: 1 a 10 páginas principais, Página contém Sapatos |
| Atualizar quando uma nova versão estiver disponível | Instrui o sistema a notificá-lo se houver uma nova versão disponível para instalação. |
