---
title: Uso de dados XDM com o Analytics
description: Visão geral do uso de dados XDM da Experience Platform no Adobe Analytics
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: 3def20b348713b580429e342ad3319963cae6549
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 88%

---

# Uso de dados da borda da Adobe Experience Platform com o Analytics

Você pode usar o [SDK da Web da Adobe Experience Platform (AEP)](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) para enviar dados ao Adobe Analytics. Funciona traduzindo o [Modelo de dados de experiência (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) em um formato usado pelo Analytics.

O Analytics coleta dados XDM por meio de dois métodos:

* Mapeamento automático de esquemas XDM
* Mapeamento manual para dados de contexto

## Mapeamento automático

O mapeamento automático depende de um [esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=pt-BR) padrão no XDM que preenche automaticamente os objetos JSON incluídos na coleta de dados típica do Analytics. As variáveis do Analytics que são mapeadas automaticamente do XDM para seus conjuntos de relatórios configurados não exigem suporte de desenvolvedor para serem incorporadas. Consulte [Variáveis mapeadas automaticamente no Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/automatically-mapped-vars.html) no guia do usuário do SDK da Web da plataforma.

## Mapeamento manual

[O mapeamento manual de dados XDM para o Analytics](xdm-manual.md) depende das variáveis de [dados de contexto do Analytics](../vars/page-vars/contextdata.md). Essas variáveis são colocadas em objetos JSON que correspondem aos esquemas aplicáveis. Normalmente, sua equipe de desenvolvimento adiciona dados de contexto após a implementação e, em seguida, os administradores definem [regras de processamento](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) para aplicar esses dados a conjuntos de relatórios especificados.

## Configuração

Para configurar o Analytics para receber dados XDM:

1. Instale e [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR).

2. Verifique se os conjuntos de relatórios aplicáveis estão mapeados para os dados desejados. Os dados XDM fluem automaticamente para o conjunto de relatórios da Adobe Experience Platform.
