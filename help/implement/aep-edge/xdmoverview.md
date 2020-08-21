---
title: Uso de dados XDM com o Analytics
description: 'Visão geral do uso de dados XDM da Experience Platform no Adobe Analytics '
translation-type: ht
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

---


# Uso de dados da borda da Adobe Experience Platform com o Analytics

Você pode usar o [SDK da Web da Adobe Experience Platform (AEP)](https://docs.adobe.com/content/help/pt-BR/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) para enviar dados ao Adobe Analytics. Funciona traduzindo o [Modelo de dados de experiência (XDM)](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/home.html) em um formato usado pelo Analytics.

O Analytics coleta dados XDM por meio de dois métodos:

* Mapeamento automático de esquemas XDM
* Mapeamento manual para dados de contexto

## Mapeamento automático

O [mapeamento automático](xdm-manual.md) depende de um [esquema](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/schema/composition.html) padrão no XDM que preenche automaticamente os objetos JSON incluídos na coleta de dados típica do Analytics. As variáveis do Analytics que são mapeadas automaticamente do XDM para seus conjuntos de relatórios configurados não exigem suporte de desenvolvedor para serem incorporadas.

## Mapeamento manual

O mapeamento manual de dados XDM para o Analytics depende das variáveis de [dados de contexto do Analytics](../vars/page-vars/contextdata.md). Essas variáveis são colocadas em objetos JSON que correspondem aos esquemas aplicáveis. Normalmente, sua equipe de desenvolvimento adiciona dados de contexto após a implementação e, em seguida, os administradores definem [regras de processamento](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) para aplicar esses dados a conjuntos de relatórios especificados.

## Configuração

Para configurar o Analytics para receber dados XDM:

1. Instale e [configure](https://docs.adobe.com/content/help/pt-BR/experience-platform/edge/fundamentals/configuring-the-sdk.html) o [SDK da Web da Adobe Experience Platform](https://docs.adobe.com/content/help/pt-BR/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Verifique se os conjuntos de relatórios aplicáveis estão mapeados para os dados desejados. Os dados XDM fluem automaticamente para o conjunto de relatórios da Adobe Experience Platform.
