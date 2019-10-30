---
description: Teste regras não publicadas do console caso utilize a hospedagem do Akamai.
keywords: Dynamic Tag Management, regra, plug-in switcher, akamai, testar akamai, regras não publicadas, testar regras não publicadas, depurar regra
seo-description: Teste regras não publicadas do console caso utilize a hospedagem do Akamai.
seo-title: Testar regras não publicadas para hospedagem do Akamai
solution: Experience Cloud, Analytics, Target, Dynamic Tag Management
title: Testar regras não publicadas para hospedagem do Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Testar regras não publicadas para hospedagem do Akamai

Teste regras não publicadas do console caso utilize a hospedagem do Akamai.

O plug-in Switcher frequentemente é o meio mais fácil para fazer testes. Consulte [Plug-ins Discovery](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) da documentação do produto do Dynamic Tag Management para obter mais informações.

As etapas a seguir mostram como criar, aplicar e fazer referência a um plug-in Switcher:

1. Acesse seu console da Web no site e digite `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Pressione **[!UICONTROL Enter]**.
1. Digite `_satellite.setDebug(true)` e pressione **[!UICONTROL Enter]**.
1. Atualize a página.

   Essa ação carrega a biblioteca de preparo e define o depurador para que você possa visualizar detalhes de todas as regras (publicadas / não publicadas) disponíveis que são acionadas na página.
1. Quando terminar, execute `localStorage.setItem('sdsat_stagingLibrary', false)` e pressione **[!UICONTROL Enter]**.

   Resultado da etapa