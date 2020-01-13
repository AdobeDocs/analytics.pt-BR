---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---



# s.linkInternalFilters

A variável é usada para determinar quais links de seu site são de saída.

Trata-se de uma lista de filtros separada por vírgulas que representa os links que são parte do site.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | Caminhos &gt; Entradas e saídas &gt; Links de saída |  |

> [!NOTE]Anteriormente, sugerimos configurar o linkInternalFilters para javascript: No entanto, isso fez com que todos os domínios fossem considerados externos, incluindo o domínio atual no qual a tag reside. Se você quiser que vários domínios sejam considerados internos, poderá adicioná-los, conforme mostrado nos exemplos abaixo.

A variável *`linkInternalFilters`* é usada para determinar se um link é um link de saída, que é definido como qualquer link que afaste o visitante do site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída só são acompanhados se  *`trackExternalLinks`* está definida como `"true"`. (Consulte [Rastreamento de links](https://marketing.adobe.com/resources/help/pt_BR/dtm/link_tracking.html) na documentação do Dynamic Tag Management para obter informações sobre como o DTM processa os links de saída.) Os filtros em *`linkInternalFilters`* não fazem distinção entre maiúsculas e minúsculas.

A lista de filtros em *`linkInternalFilters`* se aplica ao domínio e ao caminho de qualquer link por padrão. Se *`linkLeaveQueryString`* for definido como `"true"`, os filtros serão aplicados a todo o URL (domínio, caminho e sequência de consulta). Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como o valor href.

Tenha cuidado para que todos os domínios de seu site (e quaisquer parceiros que estejam usando seu arquivo JavaScript) estejam incluídos na  *`linkInternalFilters`*. Se nem todos os domínios foram incluídos na lista, todos os links de e para esses domínios serão considerados como links de saída, aumentando as chamadas para servidor enviadas. Se desejar que vários domínios ou empresas usem um único [!DNL AppMeasurement] para o arquivo JavaScript, você pode considerar preencher *`linkInternalFilters`* na página, substituindo o valor especificado no arquivo JavaScript. Se você tiver domínios vanity que redirecionam imediatamente para o seu domínio principal, esses domínios vanity não precisam ser incluídos na lista.

O exemplo a seguir ilustra como essa variável é usada. Neste exemplo, o URL da página é `https://www.mysite.com/index.html`.

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

## Sintaxe e valores possíveis

*`linkInternalFilters`*&#x200B;é uma lista de caracteres ASCII separada por vírgulas. Não são permitidos espaços.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Exemplos

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* Inclua todos os domínios nos quais o arquivo [!DNL AppMeasurement] para JavaScript possa ser exibido na lista de filtros.
* Verifique periodicamente o relatório [!UICONTROL Caminhos] &gt; [!UICONTROL Entradas e saídas] &gt; [!UICONTROL Saída] para verificar se nenhuma das entradas desse relatório está incorreta.

* Periodicamente, examine os contratos de parceiros para determinar se eles contêm restrições ao rastreamento de links. Por exemplo, você pode ser proibido de rastrear links exibidos nos anúncios de exibição do parceiro. Filtre os links do parceiro adicionando seu domínio a  *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

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
