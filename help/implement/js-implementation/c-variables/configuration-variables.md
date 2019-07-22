---
description: Variáveis de configuração definidas em appmeasurement. js.
keywords: Implementação do Analytics
seo-description: Variáveis de configuração definidas em appmeasurement. js para o Adobe Analytics
seo-title: Variáveis de configuração
solution: Analytics
subtopic: Variáveis
title: Variáveis de configuração
topic: Desenvolvedor e implementação
uuid: a 19484 b 6-e 350-4 c 12-b 4 d 6-a 31 c 79 a 42 db 0
translation-type: tm+mt
source-git-commit: 72f2b06f53c6a3c1cae965a1a9b030b0123bfca1

---


# Variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. As variáveis de configuração mais comuns que são definidas normalmente no javascript global appmeasurement. js principal. Essas variáveis podem ser definidas no código e links de nível de página do Analytics, quando apropriado.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Algumas dessas variáveis de configuração podem não se aplicar às necessidades de implementação do seu site.

Alguns dos objetivos ao usar essas variáveis de configuração são:

* Rastrear vários sites ou domínios.
* Fazer compras com qualquer moeda do mundo.
* Capturar dados em vários idiomas.
* Rastreamento de sites (número de arquivos baixados, links para arquivos externos.
* Rastrear links personalizados por razões particulares.

>[!NOTE]
>
>[!DNL AppMeasurement] requer que todas as variáveis de configuração sejam definidas antes da chamada inicial à função de rastreamento. `t()` If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

<!--
s_account.xml
-->

A variável determina o conjunto de relatórios em que os dados são armazenados e reportados.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. A ID do conjunto de relatórios é determinada pela Adobe.

**Parâmetros**

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| 40 bytes | No caminho do URL | N/A | N/A |

Cada ID de conjunto de relatórios deve corresponder ao valor criado no [!DNL Admin Console]. Cada ID de conjunto de relatórios ID deve ter mais de 40 bytes ou menos, mas a soma de todos os conjunto de relatórios (a lista completa separada por vírgulas) não tem limites.

O conjunto de relatórios é o nível mais fundamental da segmentação nos relatórios. É possível definir tantos conjunto de relatórios conto seu contrato permitir. Cada conjunto de relatórios se refere ao conjunto de tabelas dedicadas que são preenchidos nos servidores de coleção da Adobe. Um conjunto de relatórios é identificado pela variável `s_account` em seu código JavaScript.

No [!DNL Analytics], a caixa suspensa do site na parte superior esquerda dos relatórios exibe o conjunto de relatórios atual. Cada conjunto de relatórios tem um identificador exclusivo chamado de ID do conjunto de relatórios. A variável `s_account`contém um ou mais IDs de conjunto de relatórios para os quais os dados são enviados. O valor da ID do conjunto de relatórios, que é invisível para usuários do [!DNL Analytics], deve ser fornecido ou aprovado pela Adobe antes de você usá-lo. Toda ID do conjunto de relatórios tem um "nome amigável" associado que pode ser alterado na seção conjuntos de relatórios do [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. O valor no caminho é o único valor que determina o conjunto de relatórios de destino. O texto em negrito abaixo mostra os conjuntos de relatórios para os quais os dados são enviados, como será exibidos no depurador. Consulte [Depurador DigitalPulse](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**Sintaxe e valores possíveis** {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

A ID de conjunto de relatórios é uma sequência de caracteres ASCII alfanumérica, com não mais do que 40 bytes. O único caractere não alfanumérico permitido é um hífen. Não são permitidos espaços, pontos, vírgulas e outros tipos de pontuação. A variável `s_account` pode conter vários conjuntos de relatórios, sendo que todos receberão dados dessa página.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

**Exemplos** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**Configuração de variável no Analytics** {#section_7DFB2CCF02F045AFB1AD4F376638393B}

O nome amigável associado a cada ID de conjunto de relatórios pode ser alterado pelo Adobe [!DNL Customer Care]. O nome amigável pode ser visto no [!DNL Analytics] na caixa suspensa do site na parte superior esquerda da tela.

**Armadilhas, dúvidas e dicas** {#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Use o [!DNL DigitalPulse Debugger] para determinar o(s) conjunto de relatórios(s) de destino.

* Em alguns casos, é possível usar o [!DNL VISTA] para alterar o conjunto de relatórios de destino. É recomendado usar o [!DNL VISTA] para rotear novamente ou copiar os dados para outro conjunto de relatórios usando cookies primários ou se o site tiver mais de 20 conjuntos de relatórios ativos.

* Always declare `s_account` inside the JS file or just before it is included.

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

<!-- 
dynamicAccountList.xml
-->

[!DNL AppMeasurement]O para JavaScript pode selecionar dinamicamente um conjunto de relatórios para o qual enviar dados. A variável contém as regras usadas para determinar o conjunto de relatórios de destino.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | "" |

Essa variável é usada juntamente com as variáveis *`dynamicAccountSelection`* e *`dynamicAccountMatch`* variáveis. The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in `s_account` is used. As regras listadas nesta variável são aplicadas em uma ordem da esquerda para a direita. Se a URL da página corresponder a mais de uma regra, a regra mais à esquerda será usada para determinar o conjunto de relatórios. Como resultado, suas regras mais genéricas deverão ser movidas para a direita na lista.

In the following examples, the page URL is `www.mycompany.com/path1/?prod_id=12345` and `dynamicAccountSelection` is set to *true* and `s_account` is set to `mysuitecom.`

| Valor DynamicAccountList | Valor DynamicAccountMatch | Conjunto de relatórios para receber dados |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**Sintaxe e valores possíveis** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

`dynamicAccountList` A variável é uma lista separada por pontos-e-vírgulas de pares nome = valor (regras). Cada parte da lista deve conter os seguintes itens:

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

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Se a URL da página corresponder a várias regras, a regra mais à esquerda será usada.
* Se nenhuma regra for correspondente, o conjunto de relatórios padrão será usado.
* Se a página for salva no disco rígido de uma pessoa ou traduzida por um mecanismo de tradução baseado na Web (como as páginas traduzidas do Google), a seleção de conta dinâmica provavelmente não funcionará. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável `s_account`.
* `dynamicAccountSelection` As regras se aplicam somente à seção do URL especificado `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain.
* Use o [!DNL DigitalPulse Debugger] quando tentar identificar o conjunto de relatórios de destino. `dynamicAccountSelection` A variável sempre substitui o valor de `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

<!-- 
dynamicAccountMatch.xml
-->

A variável usa o objeto do DOM com a finalidade de recuperar a seção do URL a qual todas as regras em se aplicam.

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Como o valor padrão é [!DNL window.location.host], essa variável não é necessária para que a [!UICONTROL Seleção de Conta Dinâmica] funcione. For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in `dynamicAccountList` are applied to the value of `dynamicAccountMatch`. If `dynamicAccountMatch` only contains [!DNL window.location.host] (default), the rules in `dynamicAccountList` apply only to the domain of the page.

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

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Quando as páginas são salvas em um disco rígido, [!DNL window.location.host] fica em branco, fazendo com que as exibições de página sejam enviadas para o conjunto de relatórios padrão (em `s_account`).

* Quando a página é traduzida por um mecanismo de tradução baseado na Web, como o Google, a [!UICONTROL Seleção de Conta Dinâmica] não funciona conforme projetado. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável [!UICONTROL s_account].

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

<!-- 
dynamicVariablePrefix.xml
-->

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

<!-- 
charset.xml
-->

A propriedade charset, que é normalmente definida no arquivo javascript, é usada pelo Analytics para converter dados recebidos em UTF -8 para armazenamento e relatórios pelo Analytics.

>[!Note:] A propriedade charset é necessária ao enviar dados para um conjunto de relatórios multibyte e nunca deve ser usado com um conjunto de relatórios padrão. A definição de uma propriedade charSet em um report suite padrão ISO pode resultar em truncamento variável ou em conversão inesperada de caracteres.

O valor da propriedade charSet deve corresponder à codificação da página da web na tag META ou no cabeçalho http, mesmo que a sintaxe seja ligeiramente diferente. Embora a tag META possa usar um alias para a codificação, o valor do charSet deve usar o nome preferencial (ou oficial) da codificação.

Algumas das codificações mais comuns com seu nome preferencial e aliases estão apresentadas na tabela a seguir.

| Nome preferencial | Aliases |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cirílico |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Como existem várias codificações e aliases, entre em contato com seu Consultor de implementação ou com o Atendimento ao cliente da Adobe para confirmar o valor correto de charset caso ele não conste na tabela acima.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Qualquer valor não vazio do parâmetro charSet fará com que os dados sejam convertidos em UTF-8 para o armazenamento. Todos os caracteres no intervalo de 128-255 serão convertidos para a sequência UTF-8 de dois bytes correta e armazenados. Esses caracteres não serão exibidos corretamente em um report suite padrão. Portanto, a propriedade charSet nunca deve ser usada com um report suite padrão.

Da mesma forma, um valor em branco do parâmetro charSet ignorará o processo de conversão de dados, e todos os caracteres no intervalo de 128-255 serão armazenados como um único byte. Esses caracteres não serão exibidos corretamente em um report suite multibyte visto que os códigos de byte único para esses caracteres não são UTF-8 válidos. Portanto, o parâmetro charSet deve ser sempre usado com um report suite multibyte. Além disso, o valor correto deve ser usado com relação à codificação da página web.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

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

<!-- 
currencycode.xml
-->

A variável determina a taxa de conversão a ser aplicada na receita.

Todos os valores monetários são armazenados em uma moeda de sua escolha. Se essa moeda for a mesma que a especificada em *`currencyCode`* ou *`currencyCode`* estiver vazio, nenhuma conversão será aplicada.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | cc | Conversão &gt; Compras &gt; Receita Todos os relatórios de conversão mostrando valores monetários ou Receita | "USD" |

Se seu site permite que visitantes comprem em várias moedas, você deverá usar a variável *`currencyCode`* para garantir que a receita seja armazenada na moeda apropriada. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. Assim que a coleta de dados receber os dados, usará a taxa de conversão atual para converter os 40 euros no valor equivalente em dólares americanos.

Se você vende em várias moedas, é recomendável preencher a variável *`currencyCode`* na página HTML, em vez de no arquivo JavaScript. If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. Em seguida, converta toda a receita antes de enviá-la para o [!DNL Analytics].

A conversão de moeda se aplica a receita e a qualquer evento de moeda. Esses são eventos usados para somar valores semelhantes à receita, como impostos e remessa. Os eventos de receita e moeda são especificados na string dos produtos. Para obter informações sobre produtos, consulte [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Para obter mais detalhes sobre como gerenciar moedas, consulte [Suporte a várias moedas](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/).

**Sintaxe e valores possíveis** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

Somente os códigos de moeda listados no [Suporte a várias moedas](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/) são permitidos.

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

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly.
* *`currencyCode`* A variável não é persistente, o que significa que a variável deve ser passada na mesma solicitação de imagem como qualquer receita ou outras métricas relacionadas a moeda.
* Os eventos de moeda não devem ser usados para fins não relacionados a moeda. Se você precisar contar valores arbitrários ou dinâmicos que não são moeda, use o tipo de evento [!UICONTROL numérico].
* Quando a variável *`currencyCode`* estiver em branco, nenhuma conversão será aplicada.

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

<!-- 
cookiedomain.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. Por exemplo, você pode definir cookies no nome da página totalmente qualificado usando:

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

<!-- 
cookiedomainperiods.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in.

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain `www.mysite.com`, *`cookieDomainPeriods`* should be "2". For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. Como `co.jp` é um domínio inválido, quase todos os navegadores rejeitam esses cookies. Como consequência, os dados do mapa de cliques do visitante são perdidos e o relatório [!UICONTROL Perfil do visitante] &gt; [!UICONTROL Tecnologia] &gt; [!UICONTROL Cookies] indica que quase 100% dos visitantes rejeitam cookies.

Se *`cookieDomainPeriods`* for definido como "3", mas o domínio contiver somente dois pontos, o arquivo JavaScript definirá os cookies no subdomínio do site. For example, if setting *`cookieDomainPeriods`* to "3" on the domain `www2.mysite.com`, the `s_cc` and `s_sq` cookies are created on the domain `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". Essa definição de variável define os cookies no domínio raiz, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | CDP | Afeta vários relatórios, pois controla como a ID do visitante é armazenada e manipulada. | "2" |

>[!NOTE]
>
>Alguns serviços de computação em nuvem são considerados Domínios de nível superior, o que não permite que cookies sejam gravados. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) Se você implementar esses serviços, poderá ser afetado pela configuração de privacidade do Analytics, que remove os usuários que bloquearam todos os cookies caso você não tenha seu próprio domínio configurado (por exemplo, se estiver testando sua implementação). Nesse caso, qualquer hit em que o sistema determinou que os cookies estão desativados, não funcionais ou inacessíveis é cancelado e, portanto, excluído dos relatórios.

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
* A variável *`cookieDomainPeriods`* foi usada nas implementações obsoletas antes de definir *`trackingServer`* o cookie da ID do visitante. Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

<!-- 
fpCookieDomainPeriods.xml
-->

A variável é para cookies definidos pelo JavaScript (s_sq, s_cc, plug-ins) que são inerentemente cookies primários, mesmo se a implementação do usar os domínios 2o7.net ou omtrdc.net de terceiros.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* herda o *`cookieDomainPeriods`* valor. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") no domínio quando este começa com www. For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

The [!DNL AppMeasurement] for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. Há pelo menos dois cookies afetados por essa variável, incluindo s_sq e s_cc (usado para a verificação do mapa de cliques e verificação de cookie, respectivamente). Os cookies usados pelos plug-ins como [!UICONTROL getValOnce] também são afetados.

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

<!-- 
cookielifetime.xml
-->

A variável é usada pelo JavaScript e servidores de coleta de dados na determinação do tempo de vida de um cookie.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | cl | Tráfego &gt; Tecnologia &gt; Cookies Todos os relatórios relacionados ao visitante | "" |

Se *`cookieLifetime`* for definido, substituirá todas as outras expirações de cookie para JavaScript e servidores de coleta de dados, com uma exceção, descrita abaixo. *`cookieLifetime`* A variável pode ter um dos três valores:

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

*`cookieLifetime`* afeta [!DNL Analytics] o rastreamento. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Tenha cuidado ao definir *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

<!-- 
doPlugins.xml
-->

A variável é uma referência à função e permite que a função seja chamada no local apropriado dentro do arquivo javascript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* The *`t()`* function is called
* The *`tl()`* function is called
* Ocorre um clique em uma saída ou link para download.
* Ocorre um clique em um elemento de página sendo acompanhado pelo mapa de cliques do visitante

A variável *`doPlugins`*&#x200B;é usada para executar rotinas e reunir ou alterar dados. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

**Sintaxe e valores possíveis** {#section_5CFB94598521455E80947964A306EA89}

*`s_doPlugins`* A função não deve estar entre aspas e *`doPlugins`* deve ser sempre atribuída ao nome exato da *`s_doPlugins`* função (se essa função for renomeada).

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

* O único motivo para alterar o nome do objeto (como de s para s_mc) é se você compartilhar conteúdo ou receber conteúdo de outros clientes. A renomeação da função *`s_doPlugins`* para [!UICONTROL s_ mc_ doplugins] garante que outro arquivo javascript do cliente não substitua sua *`doPlugins`* função.

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. Embora a melhor solução seja usar um nome de objeto diferente de outros arquivos JavaScript na mesma página, isso não é obrigatório.

## s. registerpretrackcallback e s. registerposttrackcallback

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

<!-- 
trackDownloadLinks.xml
-->

Defina como 'true' se você deseja rastrear links para arquivos do site que podem ser obtidos por download.

If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* is used to determine which links are downloadable files.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

*`trackDownloadLinks`* A variável deve ser definida apenas como "false" se não houver links para arquivos baixáveis no site, ou você não se importa de rastrear o número de cliques em arquivos baixáveis. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. Os dados enviados com um link de download incluem a URL de download do link e os dados do mapa de cliques do visitante para esse link. Se *`trackDownloadLinks`* for'false ', os dados do mapa de cliques do visitante para os links para arquivos baixáveis em seu site provavelmente serão relatados como reportados.

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

<!-- 
trackExternalLinks.xml
-->

Se for'true ', e for usado para determinar se qualquer link clicado é um link de saída.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

*`trackExternalLinks`* A variável deve ser definida somente como'false'se não houver links de saída no site ou se você não se importa de rastrear o número de cliques nesses links de saída. Um link de saída é qualquer link que leva um visitante para fora do site. Se *`trackExternalLinks`* for'true ', então quando você clicar em um link de saída, os dados de rastreamento serão enviados imediatamente. Os dados enviados com um link de saída incluem o URL do link, o nome do link e os dados do mapa de cliques para esse link. Se *`trackExternalLinks`* for'false ', então os dados do mapa de cliques do visitante para links de saída do site provavelmente serão relatados como reportados.

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

<!-- 
trackInlineStats.xml
-->

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

<!-- 
linkDownloadFileTypes.xml
-->

A variável é uma lista separada por vírgula de extensões de arquivo.

Se o site contém links para arquivos com qualquer uma dessas extensões, as URLs desses links aparecem no relatório de [!UICONTROL Downloads de arquivo].

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | N/A | Tráfego &gt; Tráfego do site &gt; Downloads de arquivos | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

A variável *`linkDownloadFileTypes`* só é relevante quando *`trackDownloadLinks`* está definida como "Verdadeiro".

Somente os cliques feitos com o botão esquerdo do mouse no relatório [!UICONTROL Downloads de arquivo] são contados. Os downloads de arquivos que começam automaticamente quando uma página é carregada ou que só são realizados depois de um redirecionamento não são contados no relatório [!UICONTROL Downloads de arquivo]. Quando você clicar com o botão direito do mouse em um arquivo e selecionar a opção "Salvar alvo como...", ele não será contado no relatório [!UICONTROL Downloads de arquivo].

A variável *`linkDownloadFileTypes`* pode ser utilizada para rastrear links para os feeds de RSS. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

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

<!-- 
linkInternalFilters.xml
-->

A variável é usada para determinar quais links de seu site são de saída.

Trata-se de uma lista de filtros separada por vírgulas que representa os links que são parte do site.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Caminhos &gt; Entradas e saídas &gt; Links de saída |  |

>[!NOTE]
>
>Anteriormente sugerimos configurar o linkinternalfilters como javascript:. No entanto, isso fez com que todos os domínios fossem considerados externos, incluindo o domínio atual no qual a tag reside. Se você quiser que vários domínios sejam considerados internos, poderá adicioná-los, conforme mostrado nos exemplos abaixo.

*`linkInternalFilters`* A variável é usada para determinar se um link é um link de saída, que é definido como qualquer link que leva um visitante para fora do site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída só são acompanhados se *`trackExternalLinks`* está definida como `"true"`. (Consulte [Rastreamento de links](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) na documentação do Dynamic Tag Management para obter informações sobre como o DTM processa os links de saída.) The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como o valor href.

Tenha cuidado para que todos os domínios de seu site (e quaisquer parceiros que estejam usando seu arquivo JavaScript) estejam incluídos na *`linkInternalFilters`*. Se nem todos os domínios foram incluídos na lista, todos os links de e para esses domínios serão considerados como links de saída, aumentando as chamadas para servidor enviadas. If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. Se você tiver domínios vanity que redirecionam imediatamente para o seu domínio principal, esses domínios vanity não precisam ser incluídos na lista.

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

*`linkInternalFilters`* A variável é uma lista separada por vírgulas de caracteres ASCII. Não são permitidos espaços.

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

<!-- 
linkLeaveQueryString.xml
-->

Por padrão, as sequências de consulta são excluídas de todos os relatórios.

Para alguns links de saída e links de download, a parte importante do URL pode estar na string de consulta, como mostrado na seguinte URL de exemplo.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

O nome do arquivo de download pode ser definido na string de consulta e, consequentemente, a string de consulta será necessária para tornar o relatório [!UICONTROL Downloads de arquivos] mais preciso.

A variável *`linkLeaveQueryString`* determina se a string de consulta deve ou não ser incluída nos relatórios de [!UICONTROL Links de saída ]e [!UICONTROL Downloads de arquivo].

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | N/A | Downloads de arquivo de links de saída | false |

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

<!-- 
linkTrackVars.xml
-->

A variável é uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

Todas as variáveis que devem ser enviadas com os dados do link (personalizado, de saída e download) devem ser listadas em *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events."

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Qualquer | "Nenhuma" |

No preenchimento de *`linkTrackVars`*, não use o prefixo 's.' para variáveis. For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

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

*`linkTrackVars`* A variável é uma lista de nomes de variáveis separada por vírgulas, sem o prefixo do nome do objeto. Use 'eVar1' em vez de 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

A variável *`linkTrackVars`* pode conter somente variáveis enviadas [!DNL Analytics], a saber: *`events`**`campaign`**`purchaseID`*, *`products`*[!UICONTROL Evar 1-75], [!UICONTROL prop 1-75], [!UICONTROL hier 1-5]*`channel`**`server`**`state`*, *`zip`* e *`pageType`*.

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
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events."

* Não use o prefixo "s." ou "s_objectname". para variáveis.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

<!-- 
linkTrackEvents.xml
-->

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

To avoid confusion and potential problems, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

*`linkTrackEvents`* A variável contém os eventos que devem ser enviados com links [!UICONTROL personalizados], [!UICONTROL de download]e [!UICONTROL de saída] . This variable is only considered if *`linkTrackVars`* contains "events."

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Conversão | "Nenhuma" |

**Sintaxe e valores possíveis** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

*`linkTrackEvents`* A variável é uma lista de eventos separada por vírgulas (sem espaços).

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

* The JavaScript file only uses *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in *`linkTrackVars`* only when *`linkTrackEvents`* is defined.

* Tenha em mente que se um evento for acionado em uma página e listado em *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

<!-- 
linkExternalFilters.xml
-->

Se seu site contiver muitos links para sites externos e você não quiser rastrear todos os links de saída, use o para criar relatórios sobre um subconjunto específico de links de saída.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Caminhos &gt; Entradas e saídas &gt; Links de saída | "" |

A variável *`linkExternalFilters`* é uma variável opcional usada em conjunto *`linkInternalFilters`* para determinar se um link é um link de saída. Um link de saída é definido como qualquer link que leva um visitante para fora do site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída são rastreados somente se *`trackExternalLinks`* está definido como'true '. The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como valor href.

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

*`linkExternalFilters`* A variável é uma lista separada por vírgulas de caracteres ASCII. Não são permitidos espaços.

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

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links.

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

<!-- 
s_usePlugins.xml
-->

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request.

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

The [!UICONTROL usePlugins] variable should only be false (or not declared) if the *`s_doPlugins`* function is not declared in your JavaScript file.

**Configurações** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

Nenhum