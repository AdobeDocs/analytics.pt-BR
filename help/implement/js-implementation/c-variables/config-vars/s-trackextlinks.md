---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackExternalLinks

Se for 'true',  e serão usados para determinar se qualquer link clicado é um link de saída.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | N/D | Verdadeiro |

A variável *`trackExternalLinks`* só deve ser definida como 'false' se não houver links no site ou se você não fizer questão de rastrear o número de cliques nos links de saída. Um link de saída é qualquer link que leva um visitante para fora do site. Se  *`trackExternalLinks`* é 'true', portanto, quando você clicar no link de saída, o rastreamento de dados será enviado imediatamente. Os dados enviados com um link de saída incluem o URL do link, o nome do link e os dados do mapa de cliques para esse link. Se  *`trackExternalLinks`* é 'false', portanto, o mapa de cliques do visitante para links de saída provavelmente serão reportados incorretamente.

## Sintaxe e valores possíveis

A variável *`trackExternalLinks`* pode ser 'true' ou 'false'.

```
js
s.trackExternalLinks=true|false
```

## Exemplos

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* Quando *`trackExternalLinks`* é 'false', os links que afastam as pessoas do site provavelmente serão reportados incorretamente no mapa de cliques do visitante.

* Quando *`trackExternalLinks`* é 'true', os dados são enviados sempre que um visitante clicar em um link de saída (antes do carregamento do público alvo de saída).

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