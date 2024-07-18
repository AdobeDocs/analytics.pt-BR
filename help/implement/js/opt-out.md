---
title: Links para opção de não participação
description: Saiba como criar e implementar links para opção de não participação para visitantes do site.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
hidefromtoc: true
role: Developer
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 67%

---

# Implementar links para opção de não participação

>[!IMPORTANT]
>
> Este artigo fornece aos **clientes do Adobe Analytics que (estão planejando) implementar o Adobe Analytics** em seu site instruções sobre como fornecer links para opção de não participação aos usuários do site. <p><p>
> Se você está **visitando um site que implementou o Adobe Analytics** e deseja recusar, **<span style="color:red">este artigo NÃO é para você</span>**. Consulte [Opções de privacidade de Adobe](https://www.adobe.com/br/privacy/opt-out.html) para controlar como o Adobe usa suas informações.

Alguns visitantes do site preferem não ter suas informações de navegação incluídas no conjunto de dados. O Adobe oferece a capacidade de fornecer aos visitantes do seu site um meio de optar pela não participação em suas informações que estão sendo analisadas.

Os links para opção de não participação são uma maneira de permitir que os visitantes do site omitam seus dados nos relatórios do Analytics. Esses links são limitados às implementações do AppMeasurement; a Adobe recomenda usar o [serviço de Opt-in da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=pt-BR). O serviço de Opt-in é mais robusto e funciona em vários produtos da Adobe Experience Cloud, incluindo Adobe Analytics e AppMeasurement.

Quando um visitante atinge um URL de opção de não participação, ele é solicitado a instalar um cookie de opção de não participação. Se um usuário optar por não ser rastreado e um cookie de opção de não participação for definido, o AppMeasurement continuará enviando dados para o Adobe. No entanto, esses dados não serão processados ou incluídos nos relatórios.

>[!TIP]
>
>A Adobe também oferece configurações de privacidade por conjunto de relatórios. Consulte [Configurações de privacidade](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md) no guia do usuário Administração.

## URL de não participação

A página de opção de não participação da organização depende do valor da variável [`trackingServer`](../vars/config-vars/trackingserver.md) na implementação.

* Na extensão do Analytics:
   1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
   1. Clique na propriedade de tag desejada.
   1. Clique na guia [!UICONTROL Extensões] e, em seguida, clique em [!UICONTROL Configurar] no Adobe Analytics.
   1. Clique na opção [!UICONTROL Geral] e observe o valor do [!UICONTROL Servidor de rastreamento].

* Em uma implementação do JavaScript:
   1. No servidor da Web, abra o arquivo AppMeasurement.js usado no site em um editor de código ou texto.
   1. Observe o valor da variável `trackingServer`.

* Usando o [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Navegue até seu site usando o navegador Chrome.
   1. Abra o Experience Cloud Debugger e acesse a guia [!UICONTROL Rede].
   1. Observe o valor [!UICONTROL URL de solicitação - Nome do host].

Depois de encontrar o domínio `trackingServer` da implementação, anexe o caminho `/optout.html` ao final. Por exemplo:

* Cookies de terceiros: `https://example.data.adobedc.net/optout.html`
* Cookies primários: `https://stats.example.com/optout.html`

## Parâmetros da cadeia de caracteres de consulta de não participação

Há configurações que você pode carregar automaticamente nesta página usando cadeias de caracteres de consulta.

### Localidade

Alterne automaticamente o idioma da página de opção, incluindo o parâmetro da cadeia de caracteres de consulta `locale`. Atribua um dos seguintes valores a esse parâmetro da cadeia de caracteres de consulta:

* `en_US` (inglês, padrão)
* `bg_BG` (Búlgaro)
* `zh_CN` (Chinês simplificado)
* `zh_TW` (Chinês tradicional)
* `cs_CZ` (Tcheco)
* `da_NK` (Dinamarquês)
* `nl_NL` (Holandês)
* `et_EE` (Estoniano)
* `fi_FI` (Finlandês)
* `fr_FR` (Francês)
* `de_DE` (Alemão)
* `el_GR` (Grego)
* `it_IT` (Italiano)
* `jp_JP` (Japonês)
* `ko_KR` (Coreano)
* `lv_LV` (Letão)
* `lt_LT` (Lituano)
* `nb_NO` (Norueguês)
* `pl_PL` (Polonês)
* `pt_BR` (Português)
* `sk_SK` (Eslovaco)
* `es_ES` (Espanhol)

Por exemplo, `https://example.data.adobedc.net/optout.html?locale=ko_KR` carrega a página de não participação em coreano.

### Pop-up

Adiciona um botão &quot;Fechar janela&quot; à página, permitindo que a página de opção de não participação seja convertida em uma janela pop-up. Use o parâmetro da cadeia de caracteres de consulta `popup` e atribua a ele um valor `1`.

Por exemplo, `https://example.data.adobedc.net/optout.html?popup=1` carrega a página de opção de não participação com um botão &#39;Fechar janela&#39;.

>[!NOTE]
>
>Historicamente, esse parâmetro da cadeia de caracteres de consulta forçou uma janela pop-up. Entretanto, a maioria dos navegadores modernos fornece controle sobre pop-ups para o usuário final.

### Cancelamento de clique único

Permite que o usuário desative imediatamente o monitoramento. Adicione os dois parâmetros da cadeia de caracteres de consulta `opt_out` e `confirm_change`, dando a cada um o valor de `1`.

Por exemplo, o `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` instala imediatamente o cookie de não participação na página do visitante.

### Aceitação de clique único

Permite que o usuário recue imediatamente no rastreamento ao excluir o cookie de opção. Adicione os dois parâmetros da cadeia de caracteres de consulta `opt_in` e `confirm_change`, dando a cada um o valor de `1`.

Por exemplo, o `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` exclui imediatamente o cookie de não participação do visitante.
