---
description: Teste regras não publicadas do console caso utilize a hospedagem do Akamai.
keywords: Dynamic Tag Management;rule;switcher plug-in;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Testar regras não publicadas para hospedagem do Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Testar regras não publicadas para hospedagem do Akamai

Teste regras não publicadas do console caso utilize a hospedagem do Akamai.

O plug-in Switcher geralmente é o meio mais fácil para fazer testes. Consulte [Pesquisar plug-ins do Discovery](https://marketing.adobe.com/resources/help/pt_BR/dtm/search_discovery_plugins.html) na documentação de produto do Dynamic Tag Management para obter mais informações.

As etapas a seguir mostram como testar sem usar um plug-in Switcher:

1. Acesse seu console da Web no site e digite `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Pressione **[!UICONTROL Enter]**.
1. Digite `_satellite.setDebug(true)` e pressione **[!UICONTROL Enter]**.
1. Atualize a página.

   Essa ação carrega a biblioteca de preparo e define o depurador para que você possa visualizar detalhes de todas as regras (publicadas / não publicadas) disponíveis que são acionadas na página.
1. Quando terminar, execute `localStorage.setItem('sdsat_stagingLibrary', false)` e pressione **[!UICONTROL Enter]**.

   Resultado da etapa
