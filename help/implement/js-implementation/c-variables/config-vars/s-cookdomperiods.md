---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in.

O valor padrão para *`cookieDomainPeriods`* é "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. Por exemplo, usando o domínio `www.mysite.com`, *`cookieDomainPeriods`* deve ser "2". Para `www.mysite.co.jp`, *`cookieDomainPeriods`* deve ser "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

Por exemplo, se estiver configurando *`cookieDomainPeriods`* para "2" no domínio `www.mysite.co.jp`, os cookies `s_cc` e `s_sq` serão criados no domínio `co.jp`. Como `co.jp` é um domínio inválido, quase todos os navegadores rejeitam esses cookies. Como consequência, os dados do mapa de cliques do visitante são perdidos e o relatório [!UICONTROL Perfil do visitante] &gt; [!UICONTROL Tecnologia] &gt; [!UICONTROL Cookies] indica que quase 100% dos visitantes rejeitam cookies.

Se *`cookieDomainPeriods`* for definido como "3", mas o domínio contiver somente dois pontos, o arquivo JavaScript definirá os cookies no subdomínio do site. Por exemplo, se estiver configurando *`cookieDomainPeriods`* para "3" no domínio `www2.mysite.com`, os cookies `s_cc` e `s_sq` serão criados no domínio `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. Por exemplo, `store.toys.mysite.com` ainda teria *`cookieDomainPeriods`* definido para "2". Essa definição de variável define os cookies no domínio raiz, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

Consulte também [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | CDP | Afeta vários relatórios, pois controla como a ID do visitante é armazenada e manipulada. | "2" |

>[!NOTE]
>
>Alguns serviços de computação em nuvem são considerados Domínios de nível superior, que não permitem a gravação de cookies. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) Se você implementar esses serviços, poderá ser afetado pela configuração de privacidade do Analytics, que remove os usuários que bloquearam todos os cookies caso você não tenha seu próprio domínio configurado (por exemplo, se estiver testando sua implementação). Nesse caso, qualquer hit em que o sistema determinou que os cookies estão desativados, não funcionais ou inacessíveis é cancelado e, portanto, excluído dos relatórios.

## Exemplos

Configuração manual da variável:

```js
s.cookieDomainPeriods = "3";
```

Vários exemplos para definir dinamicamente a variável, se seu arquivo JavaScript principal hospedar ambos os tipos:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## Armadilhas, dúvidas e dicas

* Se você notar a ausência dos dados do mapa de cliques do visitante ou que [!UICONTROL Tráfego] &gt; [!UICONTROL Tecnologia] &gt; [!UICONTROL Relatório de cookies] mostra um percentual grande de visitantes que rejeitam cookies, verifique se o valor de *`cookieDomainPeriods`* está correto.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. Isso pode causar perda de dados quando os visitantes alternarem entre subdomínios.
* A variável *`cookieDomainPeriods`* foi usada em implementações obsoletas antes de *`trackingServer`* definir o cookie da ID de visitante. Embora esteja presente apenas em códigos desatualizados, a falha na definição correta *`cookieDomainPeriods`* nessas circunstâncias coloca sua implementação em risco de perda de dados.