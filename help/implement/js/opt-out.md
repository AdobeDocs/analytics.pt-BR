---
title: Links para opção de não participação
description: Saiba como criar e implementar links para opção de não participação para visitantes do site.
translation-type: ht
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Implementar links para opção de não participação

> [!IMPORTANT] A Adobe recomenda usar o serviço de opção de participação, especialmente em organizações que se preocupam com as regulamentações do GDPR. Consulte [Visão geral do serviço de participação](https://docs.adobe.com/content/help/pt-BR/id-service/using/implementation/opt-in-service/optin-overview.html) no guia do usuário do Serviço de identidade da Experience Cloud.

Alguns visitantes do site preferem não ter suas informações de navegação incluídas no conjunto de dados. A Adobe oferece a capacidade de fornecer aos visitantes do site uma maneira de optar ou não pela coleta de suas informações. Todos os tipos de implementação são acomodados; sua organização é responsável pela própria política de privacidade e por manter-se em conformidade com os termos assinados.

Quando um visitante atinge um URL de opção de não participação, ele é solicitado a instalar um cookie de opção de não participação. Se um usuário optar por não ser monitorado e um cookie de opção de não participação for definido, o arquivo JavaScript continuará enviando dados para os servidores da Adobe. No entanto, esses dados não serão processados ou incluídos nos relatórios.

> [!TIP] A Adobe também oferece configurações de privacidade por conjunto de relatórios. Consulte [Configurações de privacidade](../../admin/admin/privacy-settings.md) no guia do usuário Administração.

## URL de não participação

A página de opção de não participação da organização depende do valor da variável [`trackingServer`](../vars/config-vars/trackingserver.md) na implementação.

* No Adobe Experience Platform Launch:
   1. Faça logon em [launch.adobe.com](https://launch.adobe.com) e clique na propriedade desejada.
   2. Clique na guia [!UICONTROL Extensões] e, em seguida, clique em [!UICONTROL Configurar] no Adobe Analytics.
   3. Clique na opção [!UICONTROL Geral] e observe o valor do [!UICONTROL Servidor de rastreamento].

* Em uma implementação do JavaScript:
   1. No servidor da Web, abra o arquivo AppMeasurement.js usado no site em um editor de código ou texto.
   2. Observe o valor da variável `trackingServer`.

* Usando o [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html):
   1. Navegue até seu site usando o navegador Chrome.
   2. Abra o Experience Cloud Debugger e acesse a guia [!UICONTROL Rede].
   3. Observe o valor [!UICONTROL URL de solicitação - Nome do host].

Depois de encontrar o domínio `trackingServer` da implementação, anexe o caminho `/optout.html` ao final. Por exemplo:

* Cookies de terceiros: `https://example.sc.omtrdc.net/optout.html`
* Cookies primários: `https://stats.example.com/optout.html`

## Parâmetros da cadeia de caracteres de consulta de não participação

Há configurações que você pode carregar automaticamente nesta página usando cadeias de caracteres de consulta.

### Localidade

Alterne automaticamente o idioma da página de opção, incluindo o parâmetro da cadeia de caracteres de consulta `locale`. Atribua um dos seguintes valores a esse parâmetro da cadeia de caracteres de consulta:

* en_US (inglês, padrão)
* bg_BG (Búlgaro)
* zh_CN (Chinês simplificado)
* zh_TW (Chinês tradicional)
* cs_CZ (Tcheco)
* da_NK (dinamarquês)
* nl_NL (Holandês)
* et_EE (Estoniano)
* fi_FI (Finlandês)
* fr_FR (Francês)
* de_DE (Alemão)
* el_GR (Grego)
* it_IT (Italiano)
* jp_JP (Japonês)
* ko_KR (Coreano)
* lv_LV (Letão)
* lt_LT (Lituano)
* nb_NO (Norueguês)
* pl_PL (Polonês)
* pt_BR (Português)
* sk_SK (Eslovaco)
* es_ES (Espanhol)

Por exemplo, `https://example.sc.omtrdc.net/optout.html?locale=ko_KR` carrega a página de não participação em coreano.

> [!TIP] O valor da cadeia de caracteres de consulta `en_US` não é necessário, pois a página é carregada em inglês por padrão.

### Pop-up

Adiciona um botão &quot;Fechar janela&quot; à página, permitindo que a página de opção de não participação seja convertida em uma janela pop-up. Use o parâmetro da cadeia de caracteres de consulta `popup` e atribua a ele um valor `1`.

Por exemplo, `https://example.sc.omtrdc.net/optout.html?popup=1` carrega a página de opção de não participação com um botão &#39;Fechar janela&#39;.

> [!NOTE] Historicamente, esse parâmetro da cadeia de caracteres de consulta forçou uma janela pop-up. Entretanto, a maioria dos navegadores modernos fornece controle sobre pop-ups para o usuário final.

### Cancelamento de clique único

Permite que o usuário desative imediatamente o monitoramento. Adicione os dois parâmetros da cadeia de caracteres de consulta `opt_out` e `confirm_change`, dando a cada um o valor de `1`.

Por exemplo, o `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` instala imediatamente o cookie de não participação na página do visitante.

### Aceitação de clique único

Permite que o usuário recue imediatamente no rastreamento ao excluir o cookie de opção. Adicione os dois parâmetros da cadeia de caracteres de consulta `opt_in` e `confirm_change`, dando a cada um o valor de `1`.

Por exemplo, o `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` exclui imediatamente o cookie de não participação do visitante.
