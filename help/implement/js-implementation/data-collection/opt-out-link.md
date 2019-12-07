---
description: Especifique um link para opção de não participação e personalize a marca para ele. Os visitantes do site podem optar por não ter a atividade rastreada nos produtos de análise da Adobe visitando a página de opção de não participação do domínio de coleta de dados.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Adicionar um link para opção de não participação
topic: Developer and implementation
uuid: c12092be-3be7-4621-b838-d6b78d074f84
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Adicionar um link para opção de não participação

Especifique um link para opção de não participação e personalize a marca para ele. Os visitantes do site podem optar por não ter a atividade rastreada nos produtos de análise da Adobe visitando a página de opção de não participação do domínio de coleta de dados.

Se um usuário optar por não ser rastreado e um cookie de opção for enviado, seu arquivo JavaScript continuará a enviar dados para os servidores da Adobe, mas esses dados não serão processados ou relatados.

A seção collection_domain da estrutura do URL é o trackingServer usado no seu arquivo JavaScript. O domínio de coleta usado para sua implementação do Adobe Analytics pode ser visto no depurador DigitalPulse na primeira linha da tabela do Adobe Analytics, que é identificada como "Cookies primários" ou "Cookies de terceiros", dependendo da implementação. O domínio de coleta para seu site pode conter 2o7.net, omtrdc.net ou o domínio do site, como metrics.example.com.

Os visitantes optam ao clicar no link na página de opção. Como resultado, o cookie é definido no navegador. Com o cookie `omniture_optout` do domínio de rastreamento aplicável, as atividades do usuário não serão relatadas pelo Adobe Analytics. Você pode fornecer seu próprio link para o cookie de opção, ou seguir as etapas abaixo para configurar o cookie de opção.

A Adobe oferece opções para todos os tipos de implementação. Você é responsável pela sua própria política de privacidade e por seguir os termos assinados. Observe que o link para a página de opção muda com base no tipo de implementação, como definido aqui.

Se você implementar produtos e serviços do Adobe Analytics com cookies definidos em domínios da Adobe (ou seja, 207.net ou omtrdc.net), você pode direcionar os visitantes do seu site para o mecanismo de opção fornecido no [Centro de privacidade da Adobe](https://www.adobe.com/privacy/opt-out.html) para todos os sites que usam cookies da Adobe para produtos e serviços do Adobe Analytics. O link direto para o mecanismo de opção da Adobe é `https:// *collection_domain* /optout.html`.

More information about Adobe Analytics privacy practices can be found at [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [Estrutura do URL da página de cancelamento](/help/implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [Exemplo de URLs de cancelamento](/help/implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [Adição de uma marca ao URL de cancelamento](/help/implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## Estrutura do URL da página de cancelamento {#section_E0462428D2E440E7863E24D2F6DBF748}

Sua página de opção está no seguinte URL:

```
https://collection_domain/optout.html[?optional_parameters]
```

Os `optional_parameters` incluem:

`locale=[code]`: oferece uma versão traduzida da página de opção. As seguintes localidades são suportadas:

* en_US (padrão)
* de_DE
* es_ES
* fr_FR
* jp_JP
* ko_KR
* zh_CN
* zh_TW

`popup=1`: Trata a página como se fosse um pop-up e oferece um botão "Fechar janela".

## Exemplo de URLs de cancelamento {#section_258DE5226AA0483CA790D2C9C5318B2E}

Uma página da Web em inglês, em uma janela de tela inteira, com um link que, quando clicado, impede o visitante de ser rastreado em metrics.example.com:

```
https://metrics.example.com/optout.html
```

Uma página da Web em francês, em uma tela inteira, com um link que, quando clicado, impede que o visitante seja rastreado em example.d3.sc.omtrdc.net:

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

Uma página da Web em alemão, em uma tela inteira, com um link que, quando clicado, impede que o visitante seja rastreado em example.112.2o7.net:

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## Adição de uma marca ao URL de cancelamento {#section_674AB62E810B414AB8F1615C0E3061F8}

É possível fornecer um link em algum lugar do seu site, tal como:

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

Em que *`stats.adobe.com`* é substituída por qualquer que seja variável *`s.trackingServer`* definida.

Além disso, caso queria fornecer um link de participação, use o mesmo URL, mas substitua `?optout=1` por `?optin=1` e mantenha `confirm_change=1`.
