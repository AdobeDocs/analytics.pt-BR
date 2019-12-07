---
description: Lista de motivos para as informações da definição de caminho não serem registradas e exibidas em relatório.
keywords: Analytics Implementation
title: Motivos para a definição de caminho não ser registrada
topic: Developer and implementation
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Motivos para a definição de caminho não ser registrada

Lista de motivos para as informações da definição de caminho não serem registradas e exibidas em relatório.

* A Definição de caminho não foi ativada para essa prop no conjunto de relatórios. Essa ativação é específica do conjunto de relatórios.
* Os dados não estão sendo transmitidos na prop correta.
* A definição de caminho foi ativada e os dados estão na prop, mas ela não foi mostrada nos relatórios. Embora os dados de [!UICONTROL sprop] possam ser exibidos em 10 minutos, os dados da definição de caminho não serão exibidos até que a sessão do visitante seja encerrada. Ela é encerrada depois de 30 minutos de inatividade. O Analytics leva mais 10 minutos para concluir o processamento dos dados de caminho para a apresentação final nos relatórios.

Caso tenha conferido tudo, mas ainda assim os dados não estão sendo exibidos, verifique outras depurações com o Atendimento ao cliente.
