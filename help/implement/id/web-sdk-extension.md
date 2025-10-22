---
title: Identificação do visitante usando a extensão de tag do Web SDK
description: Identifique corretamente os visitantes ao implementar a extensão de tag do Web SDK.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Identificação do visitante usando a extensão de tag do Web SDK

A extensão de tag do Web SDK na Coleção de dados da Adobe Experience Platform permite que as organizações implementem o Web SDK usando uma interface de gerenciamento de tags. Cenários avançados, como compartilhamento de ID entre domínios e migração de perfil de visitante, são facilmente configurados por meio de regras e ações de extensão. O uso do Web SDK prova o futuro da sua implementação e oferece suporte a uma atualização contínua do Customer Journey Analytics.

Os dados de identidade podem ser estendidos para oferecer suporte a IDs personalizadas e vários namespaces usando o `identityMap` do XDM. A Adobe recomenda usar o Serviço da Adobe Experience Cloud ID como o identificador principal do Analytics, usando outras opções de gerenciamento de identidade para cenários avançados.

Como o Serviço de ID de visitante é criado nativamente na extensão de tag, ele requer apenas que você defina o **[!UICONTROL Domínio do Edge]** com o valor desejado. Se esse campo estiver definido corretamente, a identificação do visitante funcionará sem nenhuma configuração adicional.

>[!NOTE]
>
>Não inclua a extensão de tag do Serviço de ID de visitante se usar a extensão de tag da Web SDK. A extensão de tag do Serviço de ID de Visitante só será necessária se você usar a [extensão do Adobe Analytics](analytics-extension.md).
