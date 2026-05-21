---
title: PWAs para Analytics
description: Progressive Web Apps para Adobe Analytics
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
TQID: https://experienceleague.adobe.com/IKf2D1AqfbD6qurNczyJWaZIOzQyOTURfJFSJNDucnU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 279
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

Para obter mais informações sobre como configurar o arquivo AppMeasurement.js, consulte a [Visão geral das variáveis de configuração](/help/implement/vars/config-vars/configuration-variables.md) e as páginas individuais específicas da variável no mesmo subcapítulo.

Para obter mais informações sobre as características do arquivo AppMeasurement.js, consulte a [Visão geral de implementação do JavaScript](/help/implement/js/overview.md).
