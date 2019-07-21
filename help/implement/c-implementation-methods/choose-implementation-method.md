---
description: Há várias maneiras de implementar o Adobe Analytics.
keywords: Implementação do Analytics; método de implementação; gerenciamento dinâmico de tags; dtm; javascript
seo-description: Há várias maneiras de implementar o Adobe Analytics.
seo-title: Escolha um método de implementação
solution: Analytics
title: Escolha um método de implementação
topic: Desenvolvedor e implementação
uuid: 20 d 3317 f -7 c 63-4421-93 e 0-fff 60 dbd 9 f 87
translation-type: tm+mt
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# Escolha um método de implementação

Há várias maneiras de implementar o Adobe Analytics.

* [!UICONTROL Lançamento da Adobe Experience Platform] (recomendado)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Lançamento da Adobe Experience Platform]{#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL O Launch Platform Launch] é a próxima geração de recursos de gerenciamento de SDK e gerenciamento de SDK móvel da Adobe. [!UICONTROL A Experience Platform Launch] oferece uma maneira simples de implantar e gerenciar todas as integrações de análises, marketing e publicidade necessárias para potencializar experiências relevantes do cliente.

[!UICONTROL A Experience Platform Launch] permite capacitar qualquer pessoa a criar e manter suas próprias integrações com [!DNL Experience Platform Launch], chamadas Extensões. These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL O Gerenciamento dinâmico de tags] automatiza a maioria dos detalhes necessários para implementação [!DNL Analytics]. Insira as informações necessárias em uma interface baseada em formulário e o [!DNL Dynamic Tag Management] gera o código que deve ser adicionado às páginas.
É útil familiarizar-se com javascript e compreender a terminologia básica do Analytics, como

* O que é e como funciona uma [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html)
* Quando usar um [evento personalizado](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

Para obter informações sobre como obter acesso ao Dynamic Tag Management e começar a usá-lo, consulte [Introdução](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) na documentação do produto do Dynamic Tag Management.

Para obter mais informações, consulte [Implementação do Analytics com o Gerenciamento dinâmico de tags](../../implement/c-implement-with-dtm/dtm-implementation-overview.md).

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

O método de implementação JavaScript exige a configuração manual dos códigos JavaScript nas páginas. Muito desse esforço pode ser simplificado se você usar o Launch Eience Platform Launch ou os métodos de implementação do Gerenciamento dinâmico de tags. No entanto, alguns usuários podem exigir o método JavaScript.

Esta implementação exige:

* Grandes habilidades em JavaScript
* Entendimento sólido sobre os conceitos e terminologias do Analytics

Para obter mais informações, consulte [Implementação do Analytics usando javascript](../../implement/js-implementation/javascript-implementation-overview.md).
