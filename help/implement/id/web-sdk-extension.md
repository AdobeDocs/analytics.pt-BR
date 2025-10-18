---
title: Identificação do visitante usando a extensão de tag do Web SDK
description: Identifique corretamente os visitantes ao implementar a extensão de tag do Web SDK.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Identificação do visitante usando a extensão de tag do Web SDK

A extensão de tag do Web SDK na Coleção de dados da Adobe Experience Platform permite que as organizações implementem o Web SDK usando uma interface de gerenciamento de tags. Cenários avançados, como compartilhamento de ID entre domínios e migração de perfil de visitante, são facilmente configurados por meio de regras e ações de extensão. O uso do Web SDK garante a implementação futura e oferece suporte a atualizações ininterruptas do Customer Journey Analytics.

Como o Serviço de ID de visitante é criado nativamente na extensão de tag, ele requer apenas que você defina o **[!UICONTROL Domínio do Edge]** com o valor desejado. Se esse campo estiver definido corretamente, a identificação do visitante funcionará sem nenhuma configuração adicional.

>[!NOTE]
>
>Não inclua a extensão de tag do Serviço de ID de visitante se usar a extensão de tag da Web SDK. A extensão de tag do Serviço de ID de Visitante só será necessária se você usar a [extensão do Adobe Analytics](analytics-extension.md).
