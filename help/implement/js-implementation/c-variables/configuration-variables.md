---
description: Variáveis de configuração definidas em AppMeasurement.js.
keywords: Implementação do Analytics
seo-description: Configuration variables set in AppMeasurement.js for Adobe Analytics
seo-title: Variáveis de configuração
solution: Analytics
subtopic: Variáveis
title: Variáveis de configuração
topic: Desenvolvedor e implementação
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 755909e0d3c3be60f911fe80acad7baaff248c13

---


# Variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. As variáveis de configuração mais comuns que normalmente são definidas no AppMeasurement.js global principal do JavaScript. Essas variáveis podem ser definidas no código de nível de página do Analytics e nos links, quando apropriado.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Algumas dessas variáveis de configuração podem não se aplicar às necessidades de implementação do seu site.

Alguns dos objetivos ao usar essas variáveis de configuração são:

* Rastrear vários sites ou domínios.
* Fazer compras com qualquer moeda do mundo.
* Capturar dados em vários idiomas.
* Rastreamento de sites (número de arquivos baixados, links para arquivos externos.
* Rastrear links personalizados por razões particulares.

>[!NOTE]
>
>[!DNL AppMeasurement] requer que todas as variáveis de configuração sejam definidas antes da chamada inicial para a função de rastreamento, `t()`. If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.


## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

A variável permite a seleção dinâmica de conjunto de relatórios com base no URL de cada página.

>[!NOTE]
>
>`dynamicAccountSelection` não funciona com o rastreamento personalizado de link.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Falso. |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

**Sintaxe e valores possíveis** {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Somente 'true' ' e ' 'false' são permitidos como valores de *`dynamicAccountSelection`*.

**Exemplos** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**Configurações** {#section_F052FA38144B4F84B015A263A8E711CF}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_62F0B0895BC84A05840AEEED0643DE60}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Sempre use o [!DNL DigitalPulse Debugger] para determinar qual conjunto de relatórios está recebendo dados de cada página.

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

[!DNL AppMeasurement]O para JavaScript pode selecionar dinamicamente um conjunto de relatórios para o qual enviar dados. A variável contém as regras usadas para determinar o conjunto de relatórios de destino.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | "" |

Essa variável é usada juntamente com as variáveis *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. The rules in  are applied if  is set to 'true,' and they apply to the section of the URL specified in .*`dynamicAccountList`**`dynamicAccountSelection`**`dynamicAccountMatch`*

If none of the rules in  matches the URL of the page, the report suite identified in  is used. *`dynamicAccountList`*`s_account` As regras listadas nesta variável são aplicadas em uma ordem da esquerda para a direita. Se a URL da página corresponder a mais de uma regra, a regra mais à esquerda será usada para determinar o conjunto de relatórios. Como resultado, suas regras mais genéricas deverão ser movidas para a direita na lista.

In the following examples, the page URL is  and  is set to true and  is set to `www.mycompany.com/path1/?prod_id=12345``dynamicAccountSelection`**`s_account``mysuitecom.`

| Valor DynamicAccountList | Valor DynamicAccountMatch | Conjunto de relatórios para receber dados |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**Sintaxe e valores possíveis** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

The `dynamicAccountList` variable is a semicolon-separated list of name=value pairs (rules). Cada parte da lista deve conter os seguintes itens:

* uma ou mias ID do conjunto de relatórios (separadas por vírgulas)
* um sinal de igual
* um ou mais filtros de URL (separados por vírgulas)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

Somente caracteres ASCII padrão devem ser usados na string (sem espaços).

**Exemplos** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**Configurações** {#section_9F99CD741BC7449B8CCC108094B2EB85}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_3E10534FCC05457AB67147BB480C8BB3}

* Dynamic account selection is not supported by AppMeasurement for JavaScript.[](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)
* Se a URL da página corresponder a várias regras, a regra mais à esquerda será usada.
* Se nenhuma regra for correspondente, o conjunto de relatórios padrão será usado.
* Se a página for salva no disco rígido de uma pessoa ou traduzida por um mecanismo de tradução baseado na Web (como as páginas traduzidas do Google), a seleção de conta dinâmica provavelmente não funcionará. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável `s_account`.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update  every time you obtain a new domain.*`dynamicAccountList`*
* Use o [!DNL DigitalPulse Debugger] quando tentar identificar o conjunto de relatórios de destino. The `dynamicAccountSelection` variable always overrides the value of `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

A variável usa o objeto do DOM com a finalidade de recuperar a seção do URL a qual todas as regras em se aplicam.

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Como o valor padrão é [!DNL window.location.host], essa variável não é necessária para que a [!UICONTROL Seleção de Conta Dinâmica] funcione. For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in  are applied to the value of . `dynamicAccountList``dynamicAccountMatch` If  only contains  (default), the rules in  apply only to the domain of the page.`dynamicAccountMatch`[!DNL window.location.host]`dynamicAccountList`

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | window.location.host |

**Sintaxe e valores possíveis** {#section_95CD81972C22419B80A921CA137D3841}

The `dynamicAccountMatch` variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. Entretanto, os valores listados abaixo podem ser aplicados a qualquer momento.

```js
s.dynamicAccountMatch=[DOM object]
```

| Descrição | Valor |
|---|---|
| Domínio (padrão) | window.location.host |
| Caminho | window.location.pathname |
| String de consulta | (window.location.search?window.location.search:"?") |
| Domínio e caminho | window.location.host+window.location.pathname |
| Caminho e string de consulta | window.location.pathname+(window.location.search?window.location.search:"?") |
| URL completo | window.location.href |

**Exemplos** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**Configurações** {#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* Dynamic account selection is not supported by AppMeasurement for JavaScript.[](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)
* Quando as páginas são salvas em um disco rígido, [!DNL window.location.host] fica em branco, fazendo com que as exibições de página sejam enviadas para o conjunto de relatórios padrão (em `s_account`).

* Quando a página é traduzida por um mecanismo de tradução baseado na Web, como o Google, a [!UICONTROL Seleção de Conta Dinâmica] não funciona conforme projetado. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável [!UICONTROL s_account].

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

A variável permite a implantação de variáveis de sinalização que devem ser preenchidas dinamicamente.

Os cookies, cabeçalhos de solicitação e parâmetros da string de consulta da imagem estão disponíveis para preenchimento dinâmico.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | D= | Qualquer | D= |

**Sintaxe e valores possíveis** {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

OU USE SINALIZAÇÃO PERSONALIZADA PARA VARIÁVEIS DINÂMICAS

```js
s.dynamicVariablePrefix=".."
```

**Exemplos** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

OU USE SINALIZAÇÃO PERSONALIZADA PARA VARIÁVEIS DINÂMICAS

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**Armadilhas, dúvidas e dicas** {#section_6889908FBD78488D955F67DDB17617B1}

* As variáveis dinâmicas podem ser usadas para reduzir significativamente o tamanho total do URL, copiando valores em outras variáveis.
* As variáveis dinâmicas podem ser usadas para coletar dados de cabeçalhos e cookies não disponíveis de outra forma na coleta de dados.

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

The charSet property, which is normally set in the JavaScript file, is used by Analytics to convert incoming data into UTF-8 for storage and reporting by Analytics.

>[!N] Observação: A propriedade charSet é necessária ao enviar dados para um conjunto de relatórios multibyte e nunca deve ser usada com um conjunto de relatórios padrão. A definição de uma propriedade charSet em um report suite padrão ISO pode resultar em truncamento variável ou em conversão inesperada de caracteres.

O valor da propriedade charSet deve corresponder à codificação da página da web na tag META ou no cabeçalho http, mesmo que a sintaxe seja ligeiramente diferente. Embora a tag META possa usar um alias para a codificação, o valor do charSet deve usar o nome preferencial (ou oficial) da codificação.

Algumas das codificações mais comuns com seu nome preferencial e aliases estão apresentadas na tabela a seguir.

| Nome preferencial | Aliases |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cirílico |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Como existem várias codificações e aliases, entre em contato com seu Consultor de Implementação ou com o Atendimento ao cliente da Adobe para confirmar o valor correto do charSet se ele não aparecer na tabela acima.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Qualquer valor não vazio do parâmetro charSet fará com que os dados sejam convertidos em UTF-8 para o armazenamento. Todos os caracteres no intervalo de 128-255 serão convertidos para a sequência UTF-8 de dois bytes correta e armazenados. Esses caracteres não serão exibidos corretamente em um report suite padrão. Portanto, a propriedade charSet nunca deve ser usada com um report suite padrão.

Da mesma forma, um valor em branco do parâmetro charSet ignorará o processo de conversão de dados, e todos os caracteres no intervalo de 128-255 serão armazenados como um único byte. Esses caracteres não serão exibidos corretamente em um report suite multibyte visto que os códigos de byte único para esses caracteres não são UTF-8 válidos. Portanto, o parâmetro charSet deve ser sempre usado com um report suite multibyte. Além disso, o valor correto deve ser usado com relação à codificação da página web.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the  variable must be populated.*`charSet`*

**Parâmetros**

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | CE | N/A | "" |

**Sintaxe e valores possíveis** {#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**Exemplos** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

A variável determina a taxa de conversão a ser aplicada na receita.

Todos os valores monetários são armazenados em uma moeda de sua escolha. Se essa moeda for a mesma que a especificada em *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | cc | Conversão &gt; Compras &gt; Receita Todos os relatórios de conversão mostrando valores monetários ou Receita | "USD" |

Se seu site permite que visitantes comprem em várias moedas, você deverá usar a variável *`currencyCode`* para garantir que a receita seja armazenada na moeda apropriada. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. Assim que a coleta de dados receber os dados, usará a taxa de conversão atual para converter os 40 euros no valor equivalente em dólares americanos.

Se você vende em várias moedas, é recomendável preencher a variável *`currencyCode`* na página HTML, em vez de no arquivo JavaScript. Se você quiser usar suas próprias taxas de conversão em vez das taxas de conversão usadas pela Adobe, defina a moeda *`currencyCode`* para igualar a moeda base do conjunto de relatórios. Em seguida, converta toda a receita antes de enviá-la para o [!DNL Analytics].

A conversão de moeda se aplica a receita e a qualquer evento de moeda. Esses são eventos usados para somar valores semelhantes à receita, como impostos e remessa. Os eventos de receita e moeda são especificados na string dos produtos. Para obter informações sobre produtos, consulte [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE).

**Sintaxe e valores possíveis** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

**Exemplos** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**Configurações** {#section_D05E29F545A04958B1C0A82248BCA1B0}

O Adobe [!DNL Customer Care] pode alterar a configuração padrão de moeda de seu conjunto de relatórios. Quando você altera a moeda de base de um conjunto de relatórios, a receita existente no sistema não é convertida. Todos os novos valores de receita serão convertidos apropriadamente.

**Armadilhas, dúvidas e dicas** {#section_08A80A87B54A4861905953A6FA61FF8F}

* Se você notar valores surpreendentemente grandes de receita em relatórios, verifique se a *`currencyCode`* variável e a moeda base do conjunto de relatórios estão definidas corretamente.
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* Os eventos de moeda não devem ser usados para fins não relacionados a moeda. Se você precisar contar valores arbitrários ou dinâmicos que não são moeda, use o tipo de evento [!UICONTROL numérico].
* Quando a variável *`currencyCode`* estiver em branco, nenhuma conversão será aplicada.

Para obter mais informações, consulte Códigos [de moeda](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html).

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. Por exemplo, você pode definir cookies no nome da página totalmente qualificado usando:

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in.

O valor padrão para *`cookieDomainPeriods`* é "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. Por exemplo, usando o domínio `www.mysite.com`, *`cookieDomainPeriods`* deve ser "2". Para `www.mysite.co.jp`, *`cookieDomainPeriods`* deve ser "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

Por exemplo, se estiver configurando *`cookieDomainPeriods`* para "2" no domínio `www.mysite.co.jp`, os cookies `s_cc` e `s_sq` serão criados no domínio `co.jp`. Como `co.jp` é um domínio inválido, quase todos os navegadores rejeitam esses cookies. Como consequência, os dados do mapa de cliques do visitante são perdidos e o relatório [!UICONTROL Perfil do visitante] &gt; [!UICONTROL Tecnologia] &gt; [!UICONTROL Cookies] indica que quase 100% dos visitantes rejeitam cookies.

Se *`cookieDomainPeriods`* for definido como "3", mas o domínio contiver somente dois pontos, o arquivo JavaScript definirá os cookies no subdomínio do site. Por exemplo, se estiver configurando *`cookieDomainPeriods`* para "3" no domínio `www2.mysite.com`, os cookies `s_cc` e `s_sq` serão criados no domínio `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. Por exemplo, `store.toys.mysite.com` ainda teria *`cookieDomainPeriods`* definido para "2". Essa definição de variável define os cookies no domínio raiz, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

Consulte também [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | CDP | Afeta vários relatórios, pois controla como a ID do visitante é armazenada e manipulada. | "2" |

>[!NOTE]
>
>Some cloud computing services are considered Top-Level Domains, which do not allow cookies to be written. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) Se você implementar esses serviços, poderá ser afetado pela configuração de privacidade do Analytics, que remove os usuários que bloquearam todos os cookies caso você não tenha seu próprio domínio configurado (por exemplo, se estiver testando sua implementação). Nesse caso, qualquer hit em que o sistema determinou que os cookies estão desativados, não funcionais ou inacessíveis é cancelado e, portanto, excluído dos relatórios.

**Exemplos** {#section_4218BE29FA5E49F58975A2094329B268}

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

**Armadilhas, dúvidas e dicas** {#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. Isso pode causar perda de dados quando os visitantes alternarem entre subdomínios.
* A variável *`cookieDomainPeriods`* foi usada em implementações obsoletas antes de *`trackingServer`* definir o cookie da ID de visitante. Embora esteja presente apenas em códigos desatualizados, a falha na definição correta *`cookieDomainPeriods`* nessas circunstâncias coloca sua implementação em risco de perda de dados.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

A variável é para cookies definidos pelo JavaScript (s_sq, s_cc, plug-ins) que são inerentemente cookies primários, mesmo se a implementação do usar os domínios 2o7.net ou omtrdc.net de terceiros.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . Se você usar *`cookieDomainPeriods`*, é uma boa prática especificar um valor para *`fpCookieDomainPeriods`* também. *`fpCookieDomainPeriods`* herda o *`cookieDomainPeriods`* valor. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") no domínio quando este começa com www. For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

O arquivo [!DNL AppMeasurement] para JavaScript usa a *`fpCookieDomainPeriods`* variável para determinar o domínio com o qual definir cookies primários diferentes do cookie da ID [!UICONTROL do] visitante (s_vi). Há pelo menos dois cookies afetados por essa variável, incluindo s_sq e s_cc (usado para a verificação do mapa de cliques e verificação de cookie, respectivamente). Os cookies usados pelos plug-ins como [!UICONTROL getValOnce] também são afetados.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | cookieDomainPeriods |

**Exemplo de código para definir variáveis de domínio do cookie** {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**Sintaxe e valores possíveis** {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

**Exemplos** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**Configurações** {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

Nenhum

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

A variável é usada pelo JavaScript e servidores de coleta de dados na determinação do tempo de vida de um cookie.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | cl | Tráfego &gt; Tecnologia &gt; Cookies Todos os relatórios relacionados ao visitante | "" |

Se *`cookieLifetime`* for definido, substituirá todas as outras expirações de cookie para JavaScript e servidores de coleta de dados, com uma exceção, descrita abaixo. The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookies
* Cookies
* Configurações e plug-ins de JavaScript

**Sintaxe e valores possíveis** {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

Os valores possíveis são listados como a seguir:

* ""
* "NONE"
* "SESSION"
* Um inteiro representando o número de segundos até a expiração

**Exemplos** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**Configurações** {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* afeta o [!DNL Analytics] rastreamento. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Tenha cuidado ao definir *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

A variável é uma referência à função e permite que a função seja chamada no local apropriado no arquivo JavaScript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* A *`t()`* função é chamada
* A *`tl()`* função é chamada
* Ocorre um clique em uma saída ou link para download.
* Ocorre um clique em um elemento de página sendo acompanhado pelo mapa de cliques do visitante

A variável *`doPlugins`*&#x200B;é usada para executar rotinas e reunir ou alterar dados. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. Por exemplo, se o nome do objeto for s_mc, a *`s_doPlugins`* função deverá ser chamada de s_mc_doPlugins.

**Sintaxe e valores possíveis** {#section_5CFB94598521455E80947964A306EA89}

A *`s_doPlugins`* função não deve estar entre aspas e *`doPlugins`* deve ser sempre atribuída ao nome exato da *`s_doPlugins`* função (se essa função for renomeada).

```js
s.doPlugins=s_doPlugins;
```

**Exemplos** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**Configurações** {#section_641F0EC55E3349E5A3F8671446797074}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* O único motivo para alterar o nome do objeto (como de s para s_mc) é se você compartilhar conteúdo ou receber conteúdo de outros clientes. A renomeação da função *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* Se você começar a extrair conteúdo de outro cliente Adobe inesperadamente e sua *`s_doPlugins`* função estiver sendo substituída, será possível simplesmente renomear a *`s_doPlugins`* função sem alterar o nome do objeto. Embora a melhor solução seja usar um nome de objeto diferente de outros arquivos JavaScript na mesma página, isso não é obrigatório.

## s.registerPreTrackCallback e s.registerPostTrackCallback

Essas funções têm como parâmetros: a chamada de retorno (como função) e os parâmetros para esta função. Por exemplo:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

A chamada de retorno é disparada quando o `requestUrl` e qualquer parâmetro passado quando a chamada de retorno é registrada. Isso ocorre antes ou depois da chamada de rastreamento, dependendo de qual método é usado para registrar a chamada de retorno.

A ordem a qual essas chamadas de retorno são feitas não é garantida. As chamadas de retorno registradas na pré-função são disparadas após a criação do URL de rastreamento final. As chamadas de retorno posteriores são feitas após uma chamada de rastreamento bem-sucedida (se a chamada de rastreamento falhar, essas funções não são usadas). Qualquer chamada de retorno registrada com o `registerPreTrackCallback` não afeta a chamada de rastreamento. Além disso, o uso dos métodos de rastreamento em qualquer chamada de retorno registrada não é recomendado e pode gerar uma repetição infinita.

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

Defina como 'true' se você deseja rastrear links para arquivos do site que podem ser obtidos por download.

Se *`trackDownloadLinks`* for 'true', *`linkDownloadFileTypes`* será usado para determinar quais links são arquivos baixáveis.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

The *`trackDownloadLinks`* variable should only be set to 'false' if there are no links to downloadable files on your site, or you don't care to track the number of clicks on downloadable files. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. Os dados enviados com um link de download incluem a URL de download do link e os dados do mapa de cliques do visitante para esse link. Se *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

**Sintaxe e valores possíveis** {#section_828492CC2A144BC68D18C30CF397EEFC}

A variável *`trackDownloadLinks`pode ser 'true' ou 'false'.*

**Exemplos** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

**Configurações** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

Se for 'true' e forem usados para determinar se qualquer link clicado é um link de saída.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

The *`trackExternalLinks`* variable should only be set to 'false' if there are no exit links on your site, or if you don't care to track the number of clicks on those exit links. Um link de saída é qualquer link que leva um visitante para fora do site. Se *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. Os dados enviados com um link de saída incluem o URL do link, o nome do link e os dados do mapa de cliques para esse link. Se *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

**Sintaxe e valores possíveis** {#section_267748949A7544658E1D838AAEF964B2}

A variável *`trackExternalLinks`pode ser 'true' ou 'false'.*

```
js
s.trackExternalLinks=true|false
```

**Exemplos** {#section_EF18DB05884240F5B5062631E68E10A7}

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

**Configurações** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

A variável determina se os dados ClickMap são coletados.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | ClickMap | Falso. |

**Sintaxe e valores possíveis** {#section_46B2C1DD0D104A01A9C239929420CD90}

```
js
s.trackInlineStats=true|false
```

A variável *`trackInlineStats`pode ser 'true' ou 'false'.*

**Exemplos** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**Configurações** {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

Nenhum

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

A variável é uma lista separada por vírgula de extensões de arquivo.

Se o site contém links para arquivos com qualquer uma dessas extensões, as URLs desses links aparecem no relatório de [!UICONTROL Downloads de arquivo].

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | N/A | Tráfego &gt; Tráfego do site &gt; Downloads de arquivos | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

A variável *`linkDownloadFileTypes`* só é relevante quando *`trackDownloadLinks`* está definida como "Verdadeiro".

Somente os cliques feitos com o botão esquerdo do mouse no relatório [!UICONTROL Downloads de arquivo] são contados. Os downloads de arquivos que começam automaticamente quando uma página é carregada ou que só são realizados depois de um redirecionamento não são contados no relatório [!UICONTROL Downloads de arquivo]. Quando você clicar com o botão direito do mouse em um arquivo e selecionar a opção "Salvar alvo como...", ele não será contado no relatório [!UICONTROL Downloads de arquivo].

A variável *`linkDownloadFileTypes`* pode ser utilizada para rastrear links para os feeds de RSS. Se você tiver links para feeds RSS com uma extensão .xml ou outra extensão, anexar ",xml" à *`linkDownloadFileTypes`* lista permite que você veja com que frequência cada link RSS é clicado.

**Sintaxe e valores possíveis** {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

Incluir apenas extensões de arquivos (sem espaços).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Qualquer extensão de arquivo pode ser incluída na lista. Tenha cuidado para não incluir uma extensão de arquivo comum, como htm ou aspx, em *`linkDownloadFileTypes`*. Isso resulta em solicitações de imagem extras enviadas para cada clique, que é cobrado como uma chamada de servidor primária.

**Exemplos** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**Configurações** {#section_CE24D5852E4D441A958A4EDDB82382A7}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_786CF22D5553429EB6524B13774793BC}

* Somente cliques com o botão direito farão com que a URL apareça no relatório [!UICONTROL  Downloads de arquivo].
* A inclusão de uma extensão de arquivo comum em *`linkDownloadFileTypes`* pode aumentar significativamente o total de chamadas do servidor enviadas para os servidores da Adobe.
* Os links para redirecionamentos do lado do servidor ou de páginas HTML que começam a baixar automaticamente um arquivo não são contados a não ser que a extensão de arquivo esteja em *`linkDownloadFileTypes`*.
* Links que usam JavaScript (ou seja, javascript:openLink( )) não são contados em downloads de arquivos.

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

A variável é usada para determinar quais links de seu site são de saída.

Trata-se de uma lista de filtros separada por vírgulas que representa os links que são parte do site.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Caminhos &gt; Entradas e saídas &gt; Links de saída |  |

>[!NOTE]
>
>Anteriormente, sugerimos definir linkInternalFilters como javascript:. No entanto, isso fez com que todos os domínios fossem considerados externos, incluindo o domínio atual no qual a tag reside. Se você quiser que vários domínios sejam considerados internos, poderá adicioná-los, conforme mostrado nos exemplos abaixo.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída só são acompanhados se *`trackExternalLinks`* está definida como `"true"`. (Consulte [Rastreamento de links](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) na documentação do Dynamic Tag Management para obter informações sobre como o DTM processa os links de saída.) Os filtros não *`linkInternalFilters`* fazem distinção entre maiúsculas e minúsculas.

A lista de filtros em *`linkInternalFilters`* se aplica ao domínio e ao caminho de qualquer link por padrão. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como o valor href.

Tenha cuidado para que todos os domínios de seu site (e quaisquer parceiros que estejam usando seu arquivo JavaScript) estejam incluídos na *`linkInternalFilters`*. Se nem todos os domínios foram incluídos na lista, todos os links de e para esses domínios serão considerados como links de saída, aumentando as chamadas para servidor enviadas. If you would like multiple domains or companies to use a single  for JavaScript file, you may consider populating  on the page, overriding the value specified in the JavaScript file. [!DNL AppMeasurement]*`linkInternalFilters`* Se você tiver domínios vanity que redirecionam imediatamente para o seu domínio principal, esses domínios vanity não precisam ser incluídos na lista.

O exemplo a seguir ilustra como essa variável é usada. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**Sintaxe e valores possíveis** {#section_810966F09912415B96EA9C2EDAE0CEA0}

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. Não são permitidos espaços.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**Exemplos** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**Configurações** {#section_546AC1FACB664ABFBCF312990097C987}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Verifique periodicamente o relatório [!UICONTROL Caminhos] &gt; [!UICONTROL Entradas e saídas] &gt; [!UICONTROL Saída] para verificar se nenhuma das entradas desse relatório está incorreta.

* Periodicamente, examine os contratos de parceiros para determinar se eles contêm restrições ao rastreamento de links. Por exemplo, você pode ser proibido de rastrear links exibidos nos anúncios de exibição do parceiro. Filtre os links do parceiro adicionando seu domínio a *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

Por padrão, as sequências de consulta são excluídas de todos os relatórios.

Para alguns links de saída e links de download, a parte importante do URL pode estar na string de consulta, como mostrado na seguinte URL de exemplo.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

O nome do arquivo de download pode ser definido na string de consulta e, consequentemente, a string de consulta será necessária para tornar o relatório [!UICONTROL Downloads de arquivos] mais preciso.

A variável *`linkLeaveQueryString`* determina se a string de consulta deve ou não ser incluída nos relatórios de [!UICONTROL Links de saída ]e [!UICONTROL Downloads de arquivo].

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | N/A | Downloads de arquivos de links de saída | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

**Sintaxe** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**Exemplos** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**Valores possíveis** {#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**Configurações** {#section_835FD74D3CA9425A9D091CACF88A6F1F}

Nenhuma configuração é necessária para essa variável.

**Armadilhas, dúvidas e dicas** {#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

A variável é uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating  and  in the onClick event of a link that is used for link tracking.*`linkTrackVars`**`linkTrackEvents`*

Todas as variáveis que devem ser enviadas com os dados do link (personalizado, de saída e download) devem ser listadas em *`linkTrackVars`*. Se *`linkTrackEvents`* for usado, *`linkTrackVars`* deverá conter "events".

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Qualquer | "Nenhuma" |

No preenchimento de *`linkTrackVars`*, não use o prefixo 's.' para variáveis. Por exemplo, em vez de preencher *`linkTrackVars`* com "s.prop1", você deve preenchê-lo com "prop1". The following example illustrates how  should be used.*`linkTrackVars`*

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

Como o link para o google.com é um link de saída (a menos que você seja a Google), event1 e eVar1 são enviados com os dados de link de saída, aumentando as instâncias associadas com eVar1 e o número de vezes que event1 é acionada. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

**Sintaxe e valores possíveis** {#section_DCC239F5CFE74959856764DAB1862BA7}

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Use 'eVar1' em vez de 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

A variável  variable may contain only variables that are sent to , namely: , , , , eVar1-75, prop1-75, hier1-5, , , , , and .*`linkTrackVars`*[!DNL Analytics]*`events`**`campaign`**`purchaseID`**`products`**`channel`**`server`**`state`**`zip`**`pageType`*

**Exemplos** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**Configurações** {#section_E387604B8A434A7F89A82A886649A89D}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If  is used,  must contain "events."*`linkTrackEvents`**`linkTrackVars`*

* Não use o prefixo "s." ou "s_objectname". para variáveis.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

No primeiro link para [!DNL help.php], observe que a variável de eventos retém o valor definido antes do clique no link, Isso permite que event1 seja enviado com o link personalizado. No segundo exemplo, o link para [!DNL test.php], event2 não é registrado porque não está listado em *`linkTrackEvents`*.

To avoid confusion and potential problems, Adobe recommends populating  and  in the onClick event of a link that is used for link tracking.*`linkTrackVars`**`linkTrackEvents`*

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. This variable is only considered if  contains "events."*`linkTrackVars`*

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Conversão | "Nenhuma" |

**Sintaxe e valores possíveis** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

The *`linkTrackEvents`* variable is a comma-separated list of events (no spaces).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Somente os nomes de eventos são permitidos em *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Se um espaço for exibido antes ou depois do nome do evento, o evento não poderá ser enviado com nenhuma solicitação de imagem de link.

**Exemplos** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**Configurações** {#section_D938A47346D94A0C9E98FB327F2EF349}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_DBB68BECC9D44380816113DB2566C38C}

* The JavaScript file only uses  if  contains the "events" variable. *`linkTrackEvents`**`linkTrackVars`* "events" should be included in  only when  is defined.*`linkTrackVars`**`linkTrackEvents`*

* Tenha em mente que se um evento for acionado em uma página e listado em *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

Se seu site contiver muitos links para sites externos e você não quiser rastrear todos os links de saída, use o para criar relatórios sobre um subconjunto específico de links de saída.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Caminhos &gt; Entradas e saídas &gt; Links de saída | "" |

A variável  variable is an optional variable used in conjunction with  to determine whether a link is an exit link. *`linkExternalFilters`**`linkInternalFilters`* Um link de saída é definido como qualquer link que leva um visitante para fora do site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída são rastreados somente se *`trackExternalLinks`* is set to 'true.' The filters in  and  are case insensitive.*`linkExternalFilters`**`linkInternalFilters`*

>[!NOTE]
>
>If you don't want to use , delete it or set it to "".*`linkExternalFilters`*

The filters list in  and  apply to the domain and path of any link by default. *`linkExternalFilters`**`linkInternalFilters`* If  is set to 'true,' the filters apply to the entire URL (domain, path, and query string). *`linkLeaveQueryString`* Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como valor href.

A maioria das empresas descobre que *`linkInternalFilters`* oferece a elas controle suficiente sobre links de saída de que elas não precisam *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

O exemplo a seguir ilustra como essa variável é usada. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**Sintaxe e valores possíveis** {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. Não são permitidos espaços.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Qualquer parte de uma URL pode ser incluída em *`linkExternalFilters`*, separados por vírgulas.

**Exemplos** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**Configurações** {#section_2D0CA911855B4B3698145FC18D5021C3}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Não use essa variável no lugar de *`linkInternalFilters`* para forçar links internos a se tornarem links de saída.

* Se *`linkExternalFilters`* deve ser aplicado à string de consulta de um link, verifique se *`linkLeaveQueryString`* está definido como 'true'. See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

When usePlugins is 'true,' the  function is called prior to each image request.*`s_doPlugins`*

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

**Sintaxe e valores possíveis** {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

A variável [!UICONTROL usePlugins] pode ser 'true' ou 'false'.

**Exemplos** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

A variável [!UICONTROL usePlugins] só deve ser falsa (ou não declarada) se a *`s_doPlugins`* função não for declarada no arquivo JavaScript.

**Configurações** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

