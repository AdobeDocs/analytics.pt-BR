---
title: Links de não participação
description: Saiba como criar e implementar links de opção de não participação para visitantes do site.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Implementar links de opção

> [!IMPORTANT] A Adobe recomenda usar o serviço de aceitação, especialmente para organizações que se preocupam com as regulamentações do RGPD. See [Opt-in service overview](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) in the Experience Cloud Identity Service user guide.

Alguns visitantes de seu site preferem não ter suas informações de navegação incluídas em seu conjunto de dados. A Adobe oferece a capacidade de fornecer aos visitantes do seu site uma forma de recusar a coleta de suas informações. Todos os tipos de implementação são acomodados; sua organização é responsável por sua própria política de privacidade e por manter-se em conformidade com seus termos assinados.

Quando um visitante atinge um URL de opção, ele é solicitado a instalar um cookie de opção de não participação. Se um usuário optar por não ser rastreado e um cookie de opção de não participação for definido, seu arquivo JavaScript continuará enviando dados para os servidores da Adobe. No entanto, esses dados não são processados ou incluídos nos relatórios.

> [!TIP] A Adobe também oferece configurações de privacidade por conjunto de relatórios. Consulte Configurações [de](../../admin/admin/privacy-settings.md) privacidade no Guia do usuário administrativo.

## URL de recusa

A página de opção para sua organização depende do valor da [`trackingServer`](../vars/config-vars/trackingserver.md) variável na implementação.

* No Adobe Experience Platform Launch:
   1. Faça logon em [launch.adobe.com](https://launch.adobe.com) e clique na propriedade desejada.
   2. Click the [!UICONTROL Extensions] tab, then click [!UICONTROL Configure] under Adobe Analytics.
   3. Clique no acordeão [!UICONTROL Geral] e observe o valor do Servidor [!UICONTROL de] rastreamento.

* Em uma implementação do JavaScript:
   1. No servidor da Web, abra o arquivo AppMeasurement.js usado no site em um editor de código ou texto.
   2. Observe o valor da `trackingServer` variável.

* Using the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html):
   1. Navegue até seu site usando o navegador Chrome.
   2. Abra o depurador da Experience Cloud e vá para a guia [!UICONTROL Rede].
   3. Observe o valor URL de [!UICONTROL solicitação - Nome do host] .

Depois de encontrar o `trackingServer` domínio da implementação, anexe o caminho `/optout.html` ao final. Por exemplo:

* Cookies de terceiros: `https://example.sc.omtrdc.net/optout.html`
* Cookies próprios: `https://stats.example.com/optout.html`

## Parâmetros da string de consulta de opção

Existem configurações que você pode carregar automaticamente nesta página usando sequências de caracteres de consulta.

### Localidade

Alterne automaticamente o idioma da página de opção, incluindo o parâmetro da string de `locale` consulta. Atribua um dos seguintes valores a esse parâmetro da string de consulta:

* en_US (inglês, padrão)
* bg_BG (Búlgaro)
* zh_CN (Chinês simplificado)
* zh_TW (Chinês tradicional)
* cs_CZ (Tcheco)
* da_NK (dinamarquês)
* nl_NL (Holandês)
* et_EE (Estoniano)
* fi_FI (Finlandês)
* fr_FR (francês)
* de_DE (alemão)
* el_GR (Grego)
* it_IT (Italiano)
* jp_JP (japonês)
* ko_KR (Coreano)
* lv_LV (letão)
* lt_LT (lituano)
* nb_NO (Norueguês)
* pl_PL (Polonês)
* pt_BR (Português)
* sk_SK (Eslovaco)
* es_ES (Espanhol)

Por exemplo, `https://example.sc.omtrdc.net/optout.html?locale=ko_KR` carrega a página de opção em coreano.

> [!TIP] O valor da string de `en_US` consulta não é necessário, pois a página é carregada em inglês por padrão.

### Pop-up

Adiciona um botão &quot;Fechar janela&quot; à página, permitindo que a página de opção seja convertida em uma janela pop-up. Use o parâmetro da string de `popup` consulta e atribua a ele um valor de `1`.

Por exemplo, `https://example.sc.omtrdc.net/optout.html?popup=1` carrega a página de opção de não participação com um botão &#39;Fechar janela&#39;.

> [!NOTE] Historicamente, esse parâmetro da string de consulta forçou uma janela pop-up. Entretanto, a maioria dos navegadores modernos fornece controle sobre pop-ups para o usuário final.

### Cancelamento de clique único

Permite que o usuário desative imediatamente o rastreamento. Adicione os dois parâmetros da string de consulta `opt_out` e `confirm_change`, dando a cada um um um valor de `1`.

Por exemplo, instala `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` imediatamente o cookie de não participação na página do visitante.

### Aceitação de clique único

Permite que o usuário recue imediatamente no rastreamento ao excluir o cookie de opção. Adicione os dois parâmetros da string de consulta `opt_in` e `confirm_change`, dando a cada um um um valor de `1`.

Por exemplo, exclui `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` imediatamente o cookie de não participação do visitante.
