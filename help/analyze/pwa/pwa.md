---
title: PWAs para o Analytics
description: Aplicativos da Web progressivos para o Adobe Analytics
translation-type: tm+mt
source-git-commit: b36505c9fd7bf1d2da4d076d6b49298f01ad1cfc

---


# PWAs para o Analytics

Esta página descreve como usar o Adobe Analytics com aplicativos da Web progressivos (PWAs).

## Introdução

Os PWAs podem fornecer uma experiência de aplicativo nativa, bem como recursos offline, para um site. Geralmente, os PWAs incluem um empregado de serviço, disposições de cache e um arquivo manifest, que podem ajudar com tempos de carregamento mais rápidos, navegação mais fácil e comportamento responsivo.

O Adobe Analytics funciona de forma tão perfeita com os PWAs quanto com os sites tradicionais. Embora os PWAs tenham mais alguns requisitos para se comportarem progressivamente em si mesmos, eles não criam barreiras ou limitações sobre como o Analytics coleta ou informa dados deles de forma diferente dos sites tradicionais. Na verdade, como o Analytics já inclui recursos de rastreamento offline, os PWAs podem ajudá-lo a aproveitar esse recurso integrado mais facilmente do que com sites tradicionais.

## Obter os dados do PWA Analytics

Para coletar e analisar os dados do PWA com o Analytics, não é necessário fazer alterações na configuração. O Analytics fornece automaticamente todos os recursos e funcionalidades iguais aos de um site tradicional.

## Adicionar rastreamento offline para aumentar a eficácia do PWA

Você pode aumentar a eficácia do seu PWA usando os recursos [de rastreamento](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) offline do Analytics com ele. Por padrão, esse recurso está desativado, mas é possível adicionar a seguinte propriedade ao arquivo AppMeasurement.js para ativá-lo: `s.trackOffline=true;`.

Por exemplo, no arquivo AppMeasurement.js a seguir, a propriedade é adicionada ao final do `CONFIG SECTION`:

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
*** 
```

Para obter mais informações sobre como editar o arquivo AppMeasurement.js, consulte [Inserir código no arquivo AppMeasurement.js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

Para obter exemplos de configurações no arquivo AppMeasurement.js, consulte [Configuração do arquivo](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)AppMeasurement.js.

Para obter mais informações sobre as características do arquivo AppMeasurement.js, consulte a visão geral [da implementação do](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)Javascript.
