---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomainPeriods

A variável determina o domínio em que os [!DNL Analytics] cookies `s_cc` e `s_sq` são definidos, estabelecendo o número de períodos no domínio do URL da página. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in.

O valor padrão para *`cookieDomainPeriods`* é "2". Este é o valor usado se *`cookieDomainPeriods`* for omitido. Por exemplo, ao usar o domínio `www.mysite.com`, *`cookieDomainPeriods`* deve ser "2". Para `www.mysite.co.jp`, *`cookieDomainPeriods`* deve ser "3".

Se *`cookieDomainPeriods`* for definido como "2", mas o domínio contiver três períodos, o arquivo JavaScript tentará definir os cookies no sufixo do domínio.

Por exemplo, se estiver configurando *`cookieDomainPeriods`* para "2" no domínio `www.mysite.co.jp`, os cookies `s_cc` e `s_sq` serão criados no domínio `co.jp`. Como `co.jp` é um domínio inválido, quase todos os navegadores rejeitam esses cookies. Como consequência, os dados do mapa de cliques do visitante são perdidos e o relatório [!UICONTROL Perfil do visitante] &gt; [!UICONTROL Tecnologia] &gt; [!UICONTROL Cookies] indica que quase 100% dos visitantes rejeitam cookies.

Se  *`cookieDomainPeriods`* for definido como "3", mas o domínio contiver somente dois pontos, o arquivo JavaScript definirá os cookies no subdomínio do site. Por exemplo, se estiver configurando *`cookieDomainPeriods`* para "3" no domínio `www2.mysite.com`, os cookies `s_cc` e `s_sq` serão criados no domínio `www2.mysite.com`. Quando um visitante vai para outro subdomínio de seu site (como `www4.mysite.com`), nenhum dos cookies definidos com `www2.mysite.com` poderá ser lido.

> [!NOTE] Não inclua subdomínios adicionais como parte de *`cookieDomainPeriods`*. Por exemplo, `store.toys.mysite.com` ainda teria *`cookieDomainPeriods`* definido como "2". Essa definição de variável define os cookies no domínio raiz, [!DNL mysite.com]. Definir *`cookieDomainPeriods`* como "3" neste exemplo estabelece os cookies no domínio [!DNL toys.mysite.com], o que tem as mesmas implicações que o exemplo anterior.

Consulte também [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | CDP | Afeta vários relatórios, pois controla como a ID do visitante é armazenada e manipulada. | "2" |

>[!NOTE]
>
>Alguns serviços de computação em nuvem são considerados domínios de nível superior, que não permitem a gravação de cookies. (Por exemplo, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com` e assim por diante.) Se você implementar esses serviços, poderá ser afetado pela configuração de privacidade do Analytics, que remove os usuários que bloquearam todos os cookies caso você não tenha seu próprio domínio configurado (por exemplo, se estiver testando sua implementação). Nesse caso, qualquer hit em que o sistema determinou que os cookies estão desativados, não funcionais ou inacessíveis é cancelado e, portanto, excluído dos relatórios.

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

* Se você notar que os dados do mapa de cliques do visitante estão ausentes ou que o relatório [!UICONTROL Tráfego] &gt; [!UICONTROL Tecnologia] &gt; [!UICONTROL Cookies] mostra uma grande porcentagem de visitantes que rejeitam cookies, verifique se o valor de *`cookieDomainPeriods`* está correto.

* Se *`cookieDomainPeriods`* for maior do que o número de seções no domínio, os cookies estão definidos com o domínio completo. Isso pode causar perda de dados quando os visitantes alternarem entre subdomínios.
* A variável  A variável *`cookieDomainPeriods`* foi usada em implementações obsoletas antes de *`trackingServer`* para definir o cookie da ID de visitante. Embora esteja presente apenas em códigos desatualizados, a falha na definição correta de *`cookieDomainPeriods`* nessas circunstâncias coloca a implementação em risco de perda de dados.
