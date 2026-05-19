---
title: Identificação do visitante usando a biblioteca JavaScript do Web SDK
description: Identifique corretamente os visitantes ao implementar a biblioteca JavaScript do Web SDK.
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: https://experienceleague.adobe.com/R6O--qqR7SzlArrIDFCWunUEAduzmAS2Skm6BKyREnw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 2%

---

# Identificação do visitante usando a biblioteca JavaScript do Web SDK

A biblioteca Adobe Experience Platform Web SDK JavaScript (`alloy.js`) oferece uma abordagem unificada e moderna para a coleta de dados de todos os aplicativos corporativos do Adobe CX, incluindo o Adobe Analytics. Embora a maioria dos clientes normalmente implemente a [extensão de tag do Web SDK](web-sdk-extension.md), você pode usar a biblioteca JavaScript do Web SDK por conta própria ou em um sistema de gerenciamento de tags de terceiros. Consulte [Alloy](https://github.com/adobe/alloy) no GitHub para baixar a versão mais recente da biblioteca.

Os dados de identidade podem ser estendidos para oferecer suporte a IDs personalizadas e vários namespaces usando o `identityMap` do XDM. A Adobe recomenda usar o Serviço da Adobe Experience Cloud ID como o identificador principal do Analytics, usando outras opções de gerenciamento de identidade para cenários avançados.

Se sua organização usar a biblioteca JavaScript do Web SDK para enviar dados para a Adobe Analytics, será necessária uma configuração mínima para a identificação do visitante. O Serviço de ID de visitante é enviado nativamente para a biblioteca, exigindo apenas que você defina o **[!UICONTROL Domínio do Edge]** no comando `configure`. Se esse campo estiver definido com o valor desejado, a identificação do visitante funcionará sem nenhuma configuração adicional.
