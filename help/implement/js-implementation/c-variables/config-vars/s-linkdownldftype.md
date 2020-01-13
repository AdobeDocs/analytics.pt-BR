---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

A variável é uma lista separada por vírgula de extensões de arquivo.

Se o site contém links para arquivos com qualquer uma dessas extensões, as URLs desses links aparecem no relatório de [!UICONTROL Downloads de arquivo].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/D | N/D | Tráfego &gt; Tráfego do site &gt; Downloads de arquivos | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

A variável  A variável *`linkDownloadFileTypes`* só é relevante quando *`trackDownloadLinks`* está definida como 'True'.

Somente os cliques feitos com o botão esquerdo do mouse no relatório [!UICONTROL Downloads de arquivo] são contados. Os downloads de arquivos que começam automaticamente quando uma página é carregada ou que só são realizados depois de um redirecionamento não são contados no relatório [!UICONTROL Downloads de arquivo]. Quando você clicar com o botão direito do mouse em um arquivo e selecionar a opção "Salvar alvo como...", ele não será contado no relatório [!UICONTROL Downloads de arquivo].

A variável  *`linkDownloadFileTypes`* pode ser utilizada para rastrear links para os feeds de RSS. Se você tiver links para feeds RSS com uma extensão .xml ou outra extensão, anexar ",xml" à lista *`linkDownloadFileTypes`* permite que você veja com que frequência cada link RSS é clicado.

## Sintaxe e valores possíveis

Incluir apenas extensões de arquivos (sem espaços).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Qualquer extensão de arquivo pode ser incluída na lista. Tenha cuidado para não incluir uma extensão de arquivo comum, como htm ou aspx, em  *`linkDownloadFileTypes`*. Isso resulta em solicitações de imagem extras enviadas para cada clique, que é cobrado como uma chamada de servidor primária.

## Exemplos

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## Configurações*

Nenhum

## Armadilhas, dúvidas e dicas

* Somente cliques com o botão direito farão com que a URL apareça no relatório [!UICONTROL Downloads de arquivo].
* A inclusão de uma extensão de arquivo comum em  *`linkDownloadFileTypes`* pode aumentar significativamente o total de chamadas do servidor enviadas para os servidores da Adobe.
* Os links para redirecionamentos do lado do servidor ou de páginas HTML que começam a baixar automaticamente um arquivo não são contados a não ser que a extensão de arquivo esteja em *`linkDownloadFileTypes`*.
* Links que usam JavaScript (ou seja, javascript:openLink( )) não são contados em downloads de arquivos.

## Acompanhamento automático de links de saída e downloads de arquivos

O arquivo JavaScript pode ser configurado para monitorar automaticamente os downloads de arquivos e links de saída com base nos parâmetros que definem os tipos de arquivo de download de arquivos e links de saída.

Os parâmetros que controlam o rastreamento automático são desta forma:

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

Os parâmetros  `trackDownloadLinks` e `trackExternalLinks` determinam se o rastreamento automático de download de arquivo e link de saída está habilitado. Quando habilitado, qualquer link com um tipo de arquivo correspondente a um dos valores em `linkDownloadFileTypes` é automaticamente rastreado como um download de arquivo. Qualquer link com um URL que não contenha um dos valores em `linkInternalFilters` é automaticamente rastreado como um link de saída.

No JavaScript H.25.4 (lançado em fevereiro de 2013), o rastreamento automático do link de saída sempre foi atualizado para ignorar links com atributos `HREF` que começam com `#`, `about:` ou `javascript:`.

### Exemplo 1

Os tipos de arquivos `.jpg` e `.aspx` não estão incluídos no `linkDownloadFileTypes` acima, portanto, nenhum clique neles é rastreado automaticamente e reportado como downloads de arquivos.

O parâmetro `linkLeaveQueryString` modifica a lógica usada para determinar os links de saída. Quando `linkLeaveQueryString`=false, os links de saída são determinados utilizando somente o domínio, o caminho e parte do arquivo do URL do link. Quando `linkLeaveQueryString`=true, a parte da cadeia de consulta do URL do link também é usada para determinar um link de saída.

### Exemplo 2

Com as configurações a seguir, o exemplo abaixo será computado como um link de saída:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### Exemplo 3

Com as configurações a seguir, o link abaixo não será computado como um link de saída:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*Observação: um único link só pode ser acompanhado como um download de arquivo ou link de saída, com prioridade para o download de arquivo. Se um link for um link de saída e um download de arquivo com base nos parâmetros`linkDownloadFileTypes`e`linkInternalFilters`, ele será rastreado e reportado como um download de arquivo, não como um link de saída.*