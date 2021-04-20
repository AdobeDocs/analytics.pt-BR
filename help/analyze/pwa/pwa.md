---
title: PWAs para Analytics
description: Progressive Web Apps para Adobe Analytics
role: Business Practitioner, Administrator
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
translation-type: tm+mt
source-git-commit: 3f3a9b7f81ce671a94b7fe71c3ef7e4ae206b875
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 78%

---

# PWAs para o Adobe Analytics

Esta página descreve como usar o Adobe Analytics com Progressive Web Apps (PWAs).

## Introdução

Os PWAs podem proporcionar uma experiência de aplicativo nativa, bem como recursos offline para um site. Geralmente, os PWAs incluem um funcionário de serviço, provisões de armazenamento em cache e um arquivo de manifesto, os quais podem ajudar com tempos de carregamento mais rápidos, navegação mais fácil e comportamento responsivo.

O Adobe Analytics funciona perfeitamente com PWA, assim como com sites tradicionais. Embora os PWAs tenham mais alguns requisitos para se comportar progressivamente, eles não criam barreiras ou limitações sobre como o Analytics coleta ou relata dados de maneira diferente dos sites tradicionais. Na verdade, como o Analytics já inclui recursos de rastreamento offline, os PWAs podem ajudar a aproveitar esse recurso integrado com maior facilidade do que os sites tradicionais.

## Obtenção de dados do PWA Analytics

Para coletar e analisar os dados do PWA com o [!UICONTROL Analytics] é necessário fazer alterações na configuração. O [!UICONTROL Analytics] fornece automaticamente todos os recursos e funcionalidades iguais aos de um site tradicional.

## Adicione o rastreamento offline para aumentar a eficácia do PWA

Você pode aumentar a eficácia do PWA usando os [recursos de rastreamento offline](/help/implement/vars/config-vars/trackoffline.md) do Adobe Analytics. Por padrão, esse recurso está desativado, mas é possível adicionar a seguinte propriedade ao arquivo AppMeasurement.js para ativá-lo: `s.trackOffline=true;`.

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

Para obter mais informações sobre como editar o arquivo AppMeasurement.js, consulte [Inserir o código principal do AppMeasurement](/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md).

Para obter mais informações sobre como configurar o arquivo AppMeasurement.js, consulte a [Visão geral das variáveis de configuração](/help/implement/vars/config-vars/configuration-variables.md) e as páginas individuais específicas da variável no mesmo subcapítulo.

Para obter mais informações sobre as características do arquivo AppMeasurement.js, consulte a [Visão geral da implementação do JavaScript](/help/implement/js/overview.md).
