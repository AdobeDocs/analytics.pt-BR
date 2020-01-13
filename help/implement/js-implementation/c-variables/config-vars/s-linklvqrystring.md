---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkLeaveQueryString

Por padrão, as sequências de consulta são excluídas de todos os relatórios.

Para alguns links de saída e links de download, a parte importante do URL pode estar na string de consulta, como mostrado na seguinte URL de exemplo.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

O nome do arquivo de download pode ser definido na string de consulta e, consequentemente, a string de consulta será necessária para tornar o relatório [!UICONTROL Downloads de arquivos] mais preciso.

A variável  *`linkLeaveQueryString`* determina se a string de consulta deve ou não ser incluída nos relatórios de [!UICONTROL Links de saída ]e [!UICONTROL Downloads de arquivo].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/D | N/D | Downloads de arquivos de links de saída | false |

*Observação: configurar`linkLeaveQueryString=true`inclui todos os parâmetros de cadeia de consulta para todos os Links de Saída e Links de Download.*

## Sintaxe

```js
s.linkLeaveQueryString=[false/true]
```

## Exemplos

```js
s.linkLeaveQueryString=false
```

## Valores possíveis

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Configurações

Nenhuma configuração é necessária para essa variável.

## Armadilhas, dúvidas e dicas

* Configurar `s.linkLeaveQueryString=true` = inclui todos os parâmetros de string de consulta para todos os Links de Saída e Links de Download.
* A variável `linkLeaveQueryString` não afeta os URLs da página gravada, o mapa de cliques do visitante ou os relatórios de [!UICONTROL Caminho].

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

Parâmetro `linkLeaveQueryString` modifica a lógica usada para determinar os links de saída. Quando `linkLeaveQueryString`=false, os links de saída são determinados utilizando somente o domínio, o caminho e parte do arquivo do URL do link. Quando `linkLeaveQueryString`=true, a parte da cadeia de consulta do URL do link também é usada para determinar um link de saída.

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