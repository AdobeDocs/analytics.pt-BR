---
title: PWAs para Analytics
description: Progressive Web Apps para Adobe Analytics
translation-type: ht
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: ht
source-wordcount: '332'
ht-degree: 100%

---


# PWAs para o Adobe Analytics

Esta página descreve como usar o Adobe Analytics com Progressive Web Apps (PWAs).

## Introdução

Os PWAs podem proporcionar uma experiência de aplicativo nativa, bem como recursos offline para um site. Geralmente, os PWAs incluem um funcionário de serviço, provisões de armazenamento em cache e um arquivo de manifesto, os quais podem ajudar com tempos de carregamento mais rápidos, navegação mais fácil e comportamento responsivo.

O Adobe Analytics funciona perfeitamente com PWAs e com sites tradicionais. Embora os PWAs tenham mais alguns requisitos para se comportar progressivamente, eles não criam barreiras ou limitações sobre como o Analytics coleta ou relata dados de maneira diferente dos sites tradicionais. Na verdade, como o Analytics já inclui recursos de rastreamento offline, os PWAs podem ajudar a aproveitar esse recurso integrado com maior facilidade do que os sites tradicionais.

## Obtenção de dados do PWA Analytics

Para coletar e analisar os dados do PWA com o [!UICONTROL Analytics] é necessário fazer alterações na configuração. O [!UICONTROL Analytics] fornece automaticamente todos os recursos e funcionalidades iguais aos de um site tradicional.

## Adicione o rastreamento offline para aumentar a eficácia do PWA

Você pode aumentar a eficácia do PWA usando os [recursos de rastreamento offline](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/functions/forceoffline.html) do Adobe Analytics. Por padrão, esse recurso está desativado, mas é possível adicionar a seguinte propriedade ao arquivo AppMeasurement.js para ativá-lo: `s.trackOffline=true;`.

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

Para obter mais informações sobre como editar o arquivo AppMeasurement.js, consulte [Inserir código no arquivo AppMeasurement.js](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.html).

Para exemplos de configurações no arquivo AppMeasurement.js, consulte [Configuração do arquivo AppMeasurement.js](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/js/overview.html#section_042412C29CC249E298F19B2BC2F43CE7).

Para obter mais informações sobre as características do arquivo AppMeasurement.js, consulte a [Visão geral da implementação do Javascript](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/js/migrate-from-hcode.html).
