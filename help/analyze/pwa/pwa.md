---
title: Pwas para Analytics
seo-title: Pwas para Analytics
description: Aplicativos da Web progressivos para o Adobe Analytics
seo-description: Usar pdid com o Analytics
translation-type: tm+mt
source-git-commit: f64e5d9977bebd0e9db4af0f7118e9e64978c1c7

---


# Pwas para Analytics

Este guia descreve como usar o Adobe Analytics com aplicativos da Web progressivos (pwas).

## Introdução

O pdid pode fornecer uma experiência de aplicativo nativa, bem como recursos offline para um site. Em geral, pwas inclui um worker de serviços, regras de armazenamento em cache e um arquivo manifest, que pode ajudar com tempos de carregamento mais rápidos, navegação mais fácil e comportamento responsivo.

O Adobe Analytics funciona de forma perfeita com o pdid, assim como com sites tradicionais. Embora o PPT tenha mais requisitos para se comportar progressivamente e de si mesmo, eles não criam barreiras ou limitações de como o Analytics reúne ou relata dados de forma diferente do que sites tradicionais. Na verdade, como o Analytics já inclui recursos de rastreamento offline, o pdid pode ajudá-lo a aproveitar esse recurso com mais facilidade do que com sites tradicionais.

## Obtenção dos dados do Analytics PWA

Para coletar e analisar seus dados PWA com o Analytics, não é necessário fazer alterações na configuração. O Analytics fornece automaticamente todas as mesmas funcionalidades e recursos que faria com um site tradicional.

## Adicionar rastreamento offline para aumentar a eficácia PWA

Você pode aumentar a eficácia de sua PWA usando recursos de rastreamento [offline do Analytics](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) com ele. Por padrão, esse recurso está desativado, mas você pode adicionar a seguinte propriedade ao arquivo appmeasurement. js para ativá-lo: `s.trackOffline=true;`.

Por exemplo, no arquivo appmeasurement. js a seguir, a propriedade é adicionada ao final `CONFIG SECTION`do:

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


Para obter mais informações sobre como editar o arquivo appmeasurement. js, consulte [Inserir código no arquivo appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

Para obter exemplos de configurações no arquivo appmeasurement. js, consulte [Configurar o arquivo appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7).

Para obter mais informações sobre as características do arquivo appmeasurement. js, consulte a visão geral da implementação [do Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).
