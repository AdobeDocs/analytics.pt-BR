---
title: Uso de dados XDM com o Analytics
description: 'Visão geral do uso de dados XDM da plataforma Experience no Adobe Analytics '
translation-type: tm+mt
source-git-commit: 31efa43043120b68de90e817a7980addbe2ded39

---




# Uso de dados de borda da plataforma Adobe Experience com o Analytics

>[!IMPORTANT]
>
>O SDK da Web do Adobe Experience Edge não é lançado e está disponível somente para testes beta entre clientes convidados. Esta documentação destina-se apenas a usuários beta e não representa a funcionalidade completa do recurso. Se você estiver interessado em se tornar um usuário beta para esse recurso, entre em contato com o [Atendimento ao cliente](https://helpx.adobe.com/br/contact/enterprise-support.ec.html) da Adobe.


Você pode usar o SDK [da Web da plataforma](https://docs.adobe.com/content/help/pt-BR/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience (AEP) para enviar dados ao Adobe Analytics. Isso funciona traduzindo o Modelo de dados de [experiência (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) em um formato usado pelo Analytics.

O Analytics coleta dados XDM por meio de dois métodos:

* Mapeamento automático de schemas XDM

* Mapeamento manual para dados de contexto

## Mapeamento automático

O mapeamento automático depende de um [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) padrão no XDM que preenche automaticamente os objetos JSON incluídos na coleta de dados típica do Analytics. As variáveis do [Analytics que são mapeadas automaticamente do XDM](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) para seus conjuntos de relatórios configurados não exigem suporte para desenvolvedores a serem incorporados.

## Mapeamento manual

O mapeamento manual de dados XDM para o Analytics depende das variáveis de dados [de contexto do](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) Analytics. Essas variáveis são colocadas em objetos JSON que correspondem aos schemas aplicáveis. Normalmente, sua equipe de desenvolvimento adiciona dados de contexto após a implementação e, em seguida, os administradores definem regras [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) processamento para aplicar esses dados a conjuntos de relatórios especificados.


## Configuração

Para configurar o Analytics para receber dados XDM:

1. Instale e [configure](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) o SDK [da Web da plataforma](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience.

2. Verifique se os conjuntos de relatórios aplicáveis estão mapeados para os dados desejados. Os dados XDM fluem automaticamente para o conjunto de relatórios da plataforma Adobe Experience.

