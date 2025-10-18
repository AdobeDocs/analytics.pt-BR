---
title: Identificação do visitante usando a biblioteca JavaScript do Web SDK
description: Identifique corretamente os visitantes ao implementar a biblioteca JavaScript do Web SDK.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# Identificação do visitante usando a biblioteca JavaScript do Web SDK

O Adobe Experience Platform Web SDK (`alloy.js`) oferece uma abordagem unificada e moderna para a coleta de dados de todos os aplicativos da Adobe Experience Cloud, incluindo o Analytics. Os dados de identidade podem ser estendidos para oferecer suporte a IDs personalizadas e vários namespaces usando o `identityMap` do XDM. A Adobe recomenda usar o Serviço da Adobe Experience Cloud ID como o identificador principal do Analytics, usando outras opções de gerenciamento de identidade para cenários avançados.

Se sua organização usar a biblioteca JavaScript do Web SDK para enviar dados para a Adobe Analytics, será necessária uma configuração mínima para a identificação do visitante. O Serviço de ID de visitante é enviado nativamente para a biblioteca, exigindo apenas que você defina o **[!UICONTROL Domínio do Edge]** no comando `configure`. Se esse campo estiver definido com o valor desejado, a identificação do visitante funcionará sem nenhuma configuração adicional.
