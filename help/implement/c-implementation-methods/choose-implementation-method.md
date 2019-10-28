---
description: Há várias maneiras de implementar o Adobe Analytics.
keywords: Implementação do Analytics, método de implementação, Dynamic Tag Management, dtm, javascript
seo-description: Há várias maneiras de implementar o Adobe Analytics.
seo-title: Escolha um método de implementação
solution: Analytics
title: Escolha um método de implementação
topic: Desenvolvedor e implementação
uuid: 20d3317f-7c63-4421-93e0-fff60dbd9f87
translation-type: ht
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# Escolha um método de implementação

Há várias maneiras de implementar o Adobe Analytics.

* [!UICONTROL Adobe Experience Platform Launch] (Recomendado)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

O [!UICONTROL Experience Platform Launch] é a próxima geração de recursos de Tag Management de site e de SDKs móveis da Adobe. O [!UICONTROL Experience Platform Launch] oferece uma forma simples de implantar e gerenciar todas as integrações de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes.

O [!UICONTROL Experience Platform Launch] capacita qualquer um a criar e a manter suas próprias integrações com o [!DNL Experience Platform Launch], chamadas de Extensões. Essas extensões estão disponíveis para os clientes da Web e de dispositivos móveis do [!UICONTROL Experience Platform Launch] em uma experiência da loja de aplicativos, portanto, os clientes podem instalar, configurar e implantar suas integrações com rapidez.

Para obter mais informações, consulte [Introdução ao Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

O [!UICONTROL Dynamic Tag Management] automatiza grande parte do trabalho detalhado necessário para implementar o [!DNL Analytics]. Insira as informações necessárias em uma interface baseada em formulário e o [!DNL Dynamic Tag Management] gera o código que deve ser adicionado às páginas.
É útil conhecer o JavaScript e compreender a terminologia básica do Analytics, como

* O que é um [eVar](https://marketing.adobe.com/resources/help/pt_BR/reference/conversion_var_admin.html) e como ele funciona
* Quando usar um [evento personalizado](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

Para obter informações sobre como obter acesso, iniciar e executar o Dynamic Tag Management, consulte [Introdução](https://marketing.adobe.com/resources/help/pt_BR/dtm/get_started.html) na Documentação do produto Dynamic Tag Management.

Para obter mais informações, consulte [Implementação do Analytics com Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md).

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

O método de implementação JavaScript exige a configuração manual dos códigos JavaScript nas páginas. Grande parte desses esforços pode ser simplificada se você usar o Experience Platform Launch ou os métodos de implementação do Dynamic Tag Management. No entanto, alguns usuários podem exigir o método JavaScript.

Esta implementação exige:

* Grandes habilidades em JavaScript
* Entendimento sólido sobre os conceitos e terminologias do Analytics

Para obter mais informações, consulte [Implementação do Analytics usando JavaScript](../../implement/js-implementation/javascript-implementation-overview.md).
