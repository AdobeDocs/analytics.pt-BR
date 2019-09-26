---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkDownloadFileTypes

A variável é uma lista separada por vírgula de extensões de arquivo.

Se o site contém links para arquivos com qualquer uma dessas extensões, as URLs desses links aparecem no relatório de [!UICONTROL Downloads de arquivo].

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | N/A | Tráfego &gt; Tráfego do site &gt; Downloads de arquivos | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

A variável  variable is only relevant when  is set to 'True.'*`linkDownloadFileTypes`**`trackDownloadLinks`*

Somente os cliques feitos com o botão esquerdo do mouse no relatório [!UICONTROL Downloads de arquivo] são contados. Os downloads de arquivos que começam automaticamente quando uma página é carregada ou que só são realizados depois de um redirecionamento não são contados no relatório [!UICONTROL Downloads de arquivo]. Quando você clicar com o botão direito do mouse em um arquivo e selecionar a opção "Salvar alvo como...", ele não será contado no relatório [!UICONTROL Downloads de arquivo].

A variável *`linkDownloadFileTypes`* pode ser utilizada para rastrear links para os feeds de RSS. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the  list allows you to see how often each RSS link is clicked.*`linkDownloadFileTypes`*

## Sintaxe e valores possíveis

Incluir apenas extensões de arquivos (sem espaços).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Qualquer extensão de arquivo pode ser incluída na lista. Tenha cuidado para não incluir uma extensão de arquivo comum, como htm ou aspx, em *`linkDownloadFileTypes`*. Isso resulta em solicitações de imagem extras enviadas para cada clique, que é cobrado como uma chamada de servidor primária.

## Exemplos

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## Configurações*

Nenhuma

## Armadilhas, dúvidas e dicas

* Somente cliques com o botão direito farão com que a URL apareça no relatório [!UICONTROL  Downloads de arquivo].
* A inclusão de uma extensão de arquivo comum em *`linkDownloadFileTypes`* pode aumentar significativamente o total de chamadas do servidor enviadas para os servidores da Adobe.
* Os links para redirecionamentos do lado do servidor ou de páginas HTML que começam a baixar automaticamente um arquivo não são contados a não ser que a extensão de arquivo esteja em *`linkDownloadFileTypes`*.
* Links que usam JavaScript (ou seja, javascript:openLink( )) não são contados em downloads de arquivos.