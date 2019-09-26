---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.charSet

A propriedade charSet, que normalmente é definida no arquivo JavaScript, é usada pelo Analytics para converter os dados recebidos em UTF-8 para armazenamento e relatório pelo Analytics.

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

## Parâmetros

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | CE | N/A | "" |

## Sintaxe e valores possíveis

```js
s.charSet="character_set"
```

## Exemplos

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```
