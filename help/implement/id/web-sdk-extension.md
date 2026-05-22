---
title: Identificação do visitante usando a extensão de tag do Web SDK
description: Identifique corretamente os visitantes ao implementar a extensão de tag do Web SDK.
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: 'https://experienceleague.adobe.com/4PVDioBDa-1VXg9Fpy0wA8-RZZYSXzVijj-b2kdEALQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 0%

---

# Identificação do visitante usando a extensão de tag do Web SDK

A extensão de tag do Web SDK na Coleção de dados da Adobe Experience Platform permite que as organizações implementem o Web SDK usando uma interface de gerenciamento de tags. Cenários avançados, como compartilhamento de ID entre domínios e migração de perfil de visitante, são facilmente configurados por meio de regras e ações de extensão. O uso do Web SDK prova o futuro da sua implementação e oferece suporte a uma atualização contínua do Customer Journey Analytics.

Os dados de identidade podem ser estendidos para oferecer suporte a IDs personalizadas e vários namespaces usando o `identityMap` do XDM. A Adobe recomenda usar o Serviço da Adobe Experience Cloud ID como o identificador principal do Analytics, usando outras opções de gerenciamento de identidade para cenários avançados.

Como o Serviço de ID de visitante é criado nativamente na extensão de tag, ele requer apenas que você defina o **[!UICONTROL Domínio do Edge]** com o valor desejado. Se esse campo estiver definido corretamente, a identificação do visitante funcionará sem nenhuma configuração adicional.

>[!NOTE]
>
>Não inclua a extensão de tag do Serviço de ID de visitante se usar a extensão de tag da Web SDK. A extensão de tag do Serviço de ID de Visitante só será necessária se você usar a [extensão do Adobe Analytics](analytics-extension.md).
