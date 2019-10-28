---
description: Verifique se o arquivo .JS está referenciado corretamente na página. É possível especificar o caminho relativo para o documento atual, ou um nome de caminho absoluto pode ser usado.
keywords: Implementação do Analytics
seo-description: Verifique se o arquivo .JS está referenciado corretamente na página. É possível especificar o caminho relativo para o documento atual, ou um nome de caminho absoluto pode ser usado.
seo-title: Arquivo JS JavaScript
solution: Analytics
title: Arquivo JS JavaScript
topic: Desenvolvedor e implementação
uuid: 6e83223f-2127-41d3-9806-bd085fa2a747
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Arquivo JS JavaScript

Verifique se o arquivo .JS está referenciado corretamente na página. É possível especificar o caminho relativo para o documento atual, ou um nome de caminho absoluto pode ser usado.

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

Se algumas páginas do site forem carregadas em um protocolo seguro (https:) e referenciarem o [!DNL AppMeasurement] do arquivo JavaScript, verifique se a referência ao arquivo é segura (via https:) ou codifica a referência, como mostrado abaixo. Este exemplo adota o protocolo da página atual e impede o aviso de que "alguns elementos não são seguros".

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Verifique se o arquivo [!DNL .JS] nos servidores da Web têm permissão definida de maneira apropriada para que os visitantes do site possam baixar o arquivo e executá-lo. Se um arquivo [!DNL .JS] diferente for usado em servidores de desenvolvimento, defina o atributo "somente leitura" para o arquivo [!DNL .JS] nos servidores de produção, para evitar sobreposição. Se houver alterações, verifique se as configurações a seguir foram definidas adequadamente na parte superior do arquivo [!DNL .JS]:

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

Se "*`s_account`*" for atribuído a um valor na parte superior do arquivo [!DNL .JS], verifique se a ID do conjunto de relatórios (preenchida na variável [!UICONTROL s_account] está correta). Além disso, verifique se o código na página não está configurando a [!UICONTROL ID do conjunto de relatórios] (variável *`s_account`*).

Examine a solicitação de imagem e as variáveis para garantir que o "método de fallback" (a terceira parte do código "dividido" no exemplo acima) não crie a solicitação de imagem, em vez do arquivo[!DNL .JS].. Isso pode ser determinado porque o método de "fallback" cria apenas uma solicitação de imagem com o mínimo de informações.
