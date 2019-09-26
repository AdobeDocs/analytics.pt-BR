---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountList

[!DNL AppMeasurement]O para JavaScript pode selecionar dinamicamente um conjunto de relatórios para o qual enviar dados. A variável contém as regras usadas para determinar o conjunto de relatórios de destino.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | "" |

Essa variável é usada juntamente com as variáveis *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. As regras em *`dynamicAccountList`* são aplicadas se *`dynamicAccountSelection`* estiverem definidas como 'true' e se aplicam à seção do URL especificada em *`dynamicAccountMatch`*.

Se nenhuma das regras em *`dynamicAccountList`* corresponder ao URL da página, o conjunto de relatórios identificado em `s_account` será usado. As regras listadas nesta variável são aplicadas em uma ordem da esquerda para a direita. Se a URL da página corresponder a mais de uma regra, a regra mais à esquerda será usada para determinar o conjunto de relatórios. Como resultado, suas regras mais genéricas deverão ser movidas para a direita na lista.

In the following examples, the page URL is  and  is set to true and  is set to `www.mycompany.com/path1/?prod_id=12345``dynamicAccountSelection`**`s_account``mysuitecom.`

| Valor DynamicAccountList | Valor DynamicAccountMatch | Conjunto de relatórios para receber dados |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

## Sintaxe e valores possíveis

A sintaxe de variável `dynamicAccountList` é uma lista separada por pontos-e-vírgulas de pares nome=valor (regras). Cada parte da lista deve conter os seguintes itens:

* uma ou mias ID do conjunto de relatórios (separadas por vírgulas)
* um sinal de igual
* um ou mais filtros de URL (separados por vírgulas)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

Somente caracteres ASCII padrão devem ser usados na string (sem espaços).

## Exemplos

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## Configurações

Nenhuma

## Armadilhas, dúvidas e dicas

* A seleção de conta dinâmica não é suportada pelo [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Se a URL da página corresponder a várias regras, a regra mais à esquerda será usada.
* Se nenhuma regra for correspondente, o conjunto de relatórios padrão será usado.
* Se a página for salva no disco rígido de uma pessoa ou traduzida por um mecanismo de tradução baseado na Web (como as páginas traduzidas do Google), a seleção de conta dinâmica provavelmente não funcionará. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável `s_account`.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* Ao usar a seleção de conta dinâmica, atualize sempre que *`dynamicAccountList`* você obter um novo domínio.
* Use o [!DNL DigitalPulse Debugger] quando tentar identificar o conjunto de relatórios de destino. The `dynamicAccountSelection` variable always overrides the value of `s_account`.
