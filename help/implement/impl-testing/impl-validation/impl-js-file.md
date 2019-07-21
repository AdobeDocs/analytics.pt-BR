---
description: Verifique se o arquivo .JS está referenciado corretamente na página. É possível especificar o caminho relativo para o documento atual, ou um nome de caminho absoluto pode ser usado.
keywords: Implementação do Analytics
seo-description: Verifique se o arquivo .JS está referenciado corretamente na página. É possível especificar o caminho relativo para o documento atual, ou um nome de caminho absoluto pode ser usado.
seo-title: Arquivo JS javascript
solution: Analytics
title: Arquivo JS javascript
topic: Desenvolvedor e implementação
uuid: 6 e 83223 f -2127-41 d 3-9806-bd 085 fa 2 a 747
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Arquivo JS javascript

Verifique se o arquivo .JS está referenciado corretamente na página. É possível especificar o caminho relativo para o documento atual, ou um nome de caminho absoluto pode ser usado.

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

If some pages of the site are loaded in a secure protocol (https:), and reference the [!DNL AppMeasurement] for JavaScript file, ensure that the reference to the file is either secure (via https:) or code the reference as shown below. Este exemplo adota o protocolo da página atual e impede o aviso de que "alguns elementos não são seguros".

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Ensure that the [!DNL .JS] file on the web servers have permissions appropriately set so that the file may be downloaded and executed by website visitors. If a different [!DNL .JS] file is used on development servers, set the "read only" attribute for the [!DNL .JS] file on production servers to avoid an overwrite. If altered, ensure that the following settings are set appropriately at the top of the [!DNL .JS] file:

```js
/************************** CONFIG SECTION **************************/
/* You may add or alter any code config here.                       */
/* Link Tracking Config */
s.trackDownloadLinks=false /* true for download tracking */
s.trackExternalLinks=false /* true for exit link tracking */
s.trackInlineStats=false /* true for ClickMap support */
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls"
s.linkInternalFilters="javascript:"
s.linkLeaveQueryString=false
s.linkTrackVars="None" 
s.linkTrackEvents="None"
```

If " *`s_account`*" is assigned a value at the top of the [!DNL .JS] file, ensure that the report suite ID (populated in the [!UICONTROL s_account]variable) is correct. Also ensure that the code in the page is not setting the [!UICONTROL Report Suite ID] ( *`s_account`* variable).

Examine the image request and variables to ensure that the "fallback method" (the third part of the "split" code in the example above) is not creating the image request instead of the [!DNL .JS] file. Isso pode ser determinado porque o método de "fallback" cria apenas uma solicitação de imagem com o mínimo de informações.
