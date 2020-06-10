---
title: Uso de dados XDM com o Analytics
description: 'Visão geral do uso de dados XDM da plataforma Experience no Adobe Analytics '
translation-type: tm+mt
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 4%

---


# Uso de dados de borda da plataforma Adobe Experience com o Analytics

Você pode usar o SDK [da Web da plataforma](https://docs.adobe.com/content/help/pt-BR/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience (AEP) para enviar dados ao Adobe Analytics. Isso funciona traduzindo o Modelo de dados de [experiência (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) em um formato usado pelo Analytics.

O Analytics coleta dados XDM por meio de dois métodos:

* Mapeamento automático de schemas XDM
* Mapeamento manual para dados de contexto

## Mapeamento automático

[O mapeamento](xdm-manual.md) automático depende de um [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) padrão no XDM que preenche automaticamente os objetos JSON incluídos na coleta de dados típica do Analytics. As variáveis do Analytics que são mapeadas automaticamente do XDM para seus conjuntos de relatórios configurados não exigem suporte para o desenvolvedor a ser incorporado.

## Mapeamento manual

O mapeamento manual de dados XDM para o Analytics depende das variáveis de dados [de contexto do](../vars/page-vars/contextdata.md) Analytics. Essas variáveis são colocadas em objetos JSON que correspondem aos schemas aplicáveis. Normalmente, sua equipe de desenvolvimento adiciona dados de contexto após a implementação e, em seguida, os administradores definem regras [de](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) processamento para aplicar esses dados a conjuntos de relatórios especificados.

## Configuração

Para configurar o Analytics para receber dados XDM:

1. Instale e [configure](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) o SDK [da Web da plataforma](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience.

2. Verifique se os conjuntos de relatórios aplicáveis estão mapeados para os dados desejados. Os dados XDM fluem automaticamente para o conjunto de relatórios da plataforma Adobe Experience.
