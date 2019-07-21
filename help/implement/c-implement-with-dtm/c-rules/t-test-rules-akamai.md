---
description: Teste regras não publicadas do console caso utilize a hospedagem do Akamai.
keywords: Gerenciamento dinâmico de tags; regra; plug-plugin alternador; akamai; test akamai; regras não publicadas; testar regras não publicadas; regra de depuração
seo-description: Teste regras não publicadas do console caso utilize a hospedagem do Akamai.
seo-title: Testar regras não publicadas para hospedagem do Akamai
solution: Marketing Cloud, Analytics, Target, Gerenciamento dinâmico de tags
title: Testar regras não publicadas para hospedagem do Akamai
uuid: 979 e 3 d 74-8 d 96-47 d 0-b 581-cf 5371248434
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Testar regras não publicadas para hospedagem do Akamai

Teste regras não publicadas do console caso utilize a hospedagem do Akamai.

O plug-in Switcher frequentemente é o meio mais fácil para fazer testes. Consulte [Plug-ins Discovery](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) da documentação do produto do Dynamic Tag Management para obter mais informações.

As etapas a seguir mostram como criar, aplicar e fazer referência a um plug-in Switcher:

1. Acesse seu console da Web no site e digite `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. Type `_satellite.setDebug(true)`, then press **[!UICONTROL Enter]**.
1. Atualize a página.

   Essa ação carrega a biblioteca de preparo e define o depurador para que você possa visualizar detalhes de todas as regras (publicadas / não publicadas) disponíveis que são acionadas na página.
1. When finished, run `localStorage.setItem('sdsat_stagingLibrary', false)`, then press **[!UICONTROL Enter]**.

   Resultado da etapa