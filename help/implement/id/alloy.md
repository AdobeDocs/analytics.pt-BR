---
title: Identificação do visitante usando a biblioteca JavaScript do Web SDK
description: Identifique corretamente os visitantes ao implementar a biblioteca JavaScript do Web SDK.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Identificação do visitante usando a biblioteca JavaScript do Web SDK

A biblioteca JavaScript da Adobe Experience Platform Web SDK (`alloy.js`) oferece uma abordagem unificada e moderna para a coleta de dados de todos os aplicativos da Adobe Experience Cloud, incluindo o Adobe Analytics. Embora a maioria dos clientes normalmente implemente a [extensão de tag do Web SDK](web-sdk-extension.md), você pode usar a biblioteca JavaScript do Web SDK por conta própria ou em um sistema de gerenciamento de tags de terceiros. Consulte [Alloy](https://github.com/adobe/alloy) no GitHub para baixar a versão mais recente da biblioteca.

Os dados de identidade podem ser estendidos para oferecer suporte a IDs personalizadas e vários namespaces usando o `identityMap` do XDM. A Adobe recomenda usar o Serviço da Adobe Experience Cloud ID como o identificador principal do Analytics, usando outras opções de gerenciamento de identidade para cenários avançados.

Se sua organização usar a biblioteca JavaScript do Web SDK para enviar dados para a Adobe Analytics, será necessária uma configuração mínima para a identificação do visitante. O Serviço de ID de visitante é enviado nativamente para a biblioteca, exigindo apenas que você defina o **[!UICONTROL Domínio do Edge]** no comando `configure`. Se esse campo estiver definido com o valor desejado, a identificação do visitante funcionará sem nenhuma configuração adicional.
