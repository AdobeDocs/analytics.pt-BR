---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.useForcedLinkTracking


A variável determina o conjunto de relatórios em que os dados são armazenados e reportados.

Se estiver enviado para vários conjuntos de relatórios (marcação de vários conjuntos), `s.account` pode ser uma lista de valores separados por vírgulas. A ID do conjunto de relatórios é determinada pela Adobe.

## Parâmetros

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| 40 bytes | No caminho do URL | N/D | N/D |

Cada ID de conjunto de relatórios deve corresponder ao valor criado no [!DNL Admin Console]. Cada ID de conjunto de relatórios ID deve ter mais de 40 bytes ou menos, mas a soma de todos os conjunto de relatórios (a lista completa separada por vírgulas) não tem limites.

O conjunto de relatórios é o nível mais fundamental da segmentação nos relatórios. É possível definir tantos conjunto de relatórios conto seu contrato permitir. Cada conjunto de relatórios se refere ao conjunto de tabelas dedicadas que são preenchidos nos servidores de coleção da Adobe. Um conjunto de relatórios é identificado pela variável  `s_account` em seu código JavaScript.

No [!DNL Analytics], a caixa suspensa do site na parte superior esquerda dos relatórios exibe o conjunto de relatórios atual. Cada conjunto de relatórios tem um identificador exclusivo chamado de ID do conjunto de relatórios. A variável  `s_account`contém um ou mais IDs de conjunto de relatórios para os quais os dados são enviados. O valor da ID do conjunto de relatórios, que é invisível para usuários do [!DNL Analytics], deve ser fornecido ou aprovado pela Adobe antes de você usá-lo. Toda ID do conjunto de relatórios tem um "nome amigável" associado que pode ser alterado na seção conjuntos de relatórios do [!DNL Admin Console].

Normalmente, a variável `s_account` é declarada no arquivo JavaScript (s_code.js). Você pode declarar a variável `s_account` na página HTML, que é uma prática comum quando o valor de `s_account` pode mudar de uma página para outra. Como a variável `s_account` tem um escopo global, ela deve ser declarada imediatamente antes da inclusão do arquivo JavaScript da Adobe. Se `s_account` não tiver um valor quando o arquivo JavaScript for carregado, os dados não serão enviados para [!DNL Analytics].

O [!DNL DigitalPulse Debugger] da Adobe exibe o valor de `s_account` no caminho do URL, que aparece logo abaixo da palavra "Image" e logo depois de /b/ss/. Em alguns casos, o valor de `s_account` também aparece no domínio, antes de 112.2o7.net. O valor no caminho é o único valor que determina o conjunto de relatórios de destino. O texto em negrito abaixo mostra os conjuntos de relatórios para os quais os dados são enviados, como será exibidos no depurador. Consulte  [Depurador DigitalPulse](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Sintaxe e valores possíveis

A ID de conjunto de relatórios é uma sequência de caracteres ASCII alfanumérica, com não mais do que 40 bytes. O único caractere não alfanumérico permitido é um hífen. Não são permitidos espaços, pontos, vírgulas e outros tipos de pontuação. A variável  `s_account` pode conter vários conjuntos de relatórios, sendo que todos receberão dados dessa página.

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

* Se `s_account` estiver vazio, não for declarado ou contiver um valor inesperado, os dados não serão coletados.
* Quando a variável `s_account` é uma lista separada por vírgulas (marcação de vários relatórios), não coloque espaços entre as IDs do conjunto de relatórios.
* Se [!UICONTROL s.dynamicAccountSelection] for definido como *True*, o URL será usado para determinar o conjunto de relatórios de destino. Use o [!DNL DigitalPulse Debugger] para determinar o(s) conjunto de relatórios(s) de destino.

* Em alguns casos, é possível usar o [!DNL VISTA] para alterar o conjunto de relatórios de destino. É recomendado usar o [!DNL VISTA] para rotear novamente ou copiar os dados para outro conjunto de relatórios usando cookies primários ou se o site tiver mais de 20 conjuntos de relatórios ativos.

* Sempre declare `s_account` no arquivo JS ou antes da inclusão do arquivo JS.
