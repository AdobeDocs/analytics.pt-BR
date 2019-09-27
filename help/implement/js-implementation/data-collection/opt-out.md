---
description: 'null'
keywords: Implementação do Analytics
seo-description: 'null'
seo-title: Implementar opções de não participação da Adobe
solution: Analytics
title: Implementar opções de não participação da Adobe
topic: Desenvolvedor e implementação
uuid: fc3a411c-8476-409d-99de-05b34ace5019
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Implementar opções de não participação da Adobe

Alguns visitantes do seu site podem preferir não ter suas informações de navegação agregadas ou analisadas por produtos e serviços da Adobe Experience Cloud, ou usados para fornecer conteúdo e anúncios relevantes. A Adobe oferece a capacidade de fornecer aos visitantes do seu site uma maneira de optar ou não pela coleta de suas informações pelos seguintes produtos da Adobe:

* Adobe Analytics
* Adobe Target
* Adobe Audience Targeted Creative
* Adobe AudienceManager
* Adobe AdLens
* Adobe Experience Manager

## Recomendações de política de privacidade {#section_BBDEE21C259842F7881642E31FB3D9B7}

A Adobe recomenda que você forneça aos visitantes do site informações fáceis de encontrar e entender com relação à capacidade de optar pela coleta de informações de navegação por produtos e serviços da Adobe.

Os visitantes podem obter mais informações sobre como a Adobe usa as informações coletadas, além de fornecer nossos produtos e serviços para os clientes no [Adobe Privacy Center](https://www.adobe.com/privacy.html). No entanto, como o controle exclusiva do implementação de nossos serviços em seus sites é seu, você decide como descrever para seus visitantes as maneiras específicas com a qual podem usar nossos produtos e serviços. Você é responsável pela criação de sua própria política de privacidade, por seguir sua política de privacidade, por seguir o contrato de serviço com a Adobe e todas as leis aplicáveis.

## Opt-outs for Adobe Analytics (including Reports &amp; Analytics, Data Warehouse, Ad Hoc Analysis) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe offers three types of opt-outs for Adobe Analytics (including [!UICONTROL Reports &amp; Analytics], [!UICONTROL Data Warehouse], [!UICONTROL Ad Hoc Analysis]):

* Se você implementar produtos do Adobe Analytics com seu próprio cookie primário, precisará [desenvolver seu próprio link](../../../implement/js-implementation/data-collection/opt-out-link.md#concept_C2C4F19811A445EF9E9BEAC709B568A9) personalizado de opção de não participação para os visitantes do seu site.
* Seus clientes têm a opção de ativar o cancelamento usando as configurações de cookies do navegador. Consulte [Ativação das configurações de privacidade de cookies do navegador](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/browser_cookie_settings.html).

Independentemente do mecanismo de opção escolhido, a Adobe recomenda que você descreva claramente a disponibilidade do mecanismo de opção na sua política de privacidade ou, do contrário, como exigido por lei ou recomendado de acordo com as práticas recomendadas.
