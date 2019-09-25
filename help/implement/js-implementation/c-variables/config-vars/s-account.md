---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 4a6bac589d1d6d6caaf34dc5363c60bbfbb952d5

---


# s.account

A variável determina o conjunto de relatórios em que os dados são armazenados e reportados.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. A ID do conjunto de relatórios é determinada pela Adobe.

## Parâmetros

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| 40 bytes | No caminho do URL | N/A | N/A |

Cada ID de conjunto de relatórios deve corresponder ao valor criado no [!DNL Admin Console]. Cada ID de conjunto de relatórios ID deve ter mais de 40 bytes ou menos, mas a soma de todos os conjunto de relatórios (a lista completa separada por vírgulas) não tem limites.

O conjunto de relatórios é o nível mais fundamental da segmentação nos relatórios. É possível definir tantos conjunto de relatórios conto seu contrato permitir. Cada conjunto de relatórios se refere ao conjunto de tabelas dedicadas que são preenchidos nos servidores de coleção da Adobe. Um conjunto de relatórios é identificado pela variável `s_account` em seu código JavaScript.

No [!DNL Analytics], a caixa suspensa do site na parte superior esquerda dos relatórios exibe o conjunto de relatórios atual. Cada conjunto de relatórios tem um identificador exclusivo chamado de ID do conjunto de relatórios. A variável `s_account`contém um ou mais IDs de conjunto de relatórios para os quais os dados são enviados. O valor da ID do conjunto de relatórios, que é invisível para usuários do [!DNL Analytics], deve ser fornecido ou aprovado pela Adobe antes de você usá-lo. Toda ID do conjunto de relatórios tem um "nome amigável" associado que pode ser alterado na seção conjuntos de relatórios do [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). Você pode declarar a `s_account` variável na página HTML, que é uma prática comum quando o valor de `s_account` pode mudar de página para página. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. Em alguns casos, o valor de `s_account` também aparece no domínio, antes de 112.2o7.net. O valor no caminho é o único valor que determina o conjunto de relatórios de destino. O texto em negrito abaixo mostra os conjuntos de relatórios para os quais os dados são enviados, como será exibidos no depurador. Consulte [Depurador DigitalPulse](/help/implement/impl-testing/debugger.md).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Sintaxe e valores possíveis

A ID de conjunto de relatórios é uma sequência de caracteres ASCII alfanumérica, com não mais do que 40 bytes. O único caractere não alfanumérico permitido é um hífen. Não são permitidos espaços, pontos, vírgulas e outros tipos de pontuação. A variável `s_account` pode conter vários conjuntos de relatórios, sendo que todos receberão dados dessa página.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

Todos os valores de `s_account` devem ser fornecidos ou aprovados pela Adobe.

## Exemplos

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## Configuração de variável no Analytics

O nome amigável associado a cada ID de conjunto de relatórios pode ser alterado pelo Adobe [!DNL Customer Care]. O nome amigável pode ser visto no [!DNL Analytics] na caixa suspensa do site na parte superior esquerda da tela.

## Armadilhas, dúvidas e dicas

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Use o [!DNL DigitalPulse Debugger] para determinar o(s) conjunto de relatórios(s) de destino.

* Em alguns casos, é possível usar o [!DNL VISTA] para alterar o conjunto de relatórios de destino. É recomendado usar o [!DNL VISTA] para rotear novamente ou copiar os dados para outro conjunto de relatórios usando cookies primários ou se o site tiver mais de 20 conjuntos de relatórios ativos.

* Always declare `s_account` inside the JS file or just before it is included.
