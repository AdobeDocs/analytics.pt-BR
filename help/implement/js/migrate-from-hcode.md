---
title: Migrando para o AppMeasurement para JavaScript
description: Determine o que é necessário para migrar sua implementação do Código H.
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Migrando para o AppMeasurement para JavaScript

Se sua implementação ainda usar o código H, a Adobe recomenda migrar para a versão mais recente do AppMeasurement. A implementação do Analytics por meio do [Adobe Experience Platform Launch](../launch/overview.md) é recomendada, mas uma implementação atualizada do JavaScript pode ser usada.

As seguintes alterações notáveis estão presentes no AppMeasurement quando comparadas ao Código H:

* 3 a 7 vezes mais rápido que o código H.
* Mais leve que o código H - 21kb descompactado vs. código H, que é 33kb descompactado.
* O código da biblioteca e da página pode ser implantado dentro da tag `<head>`.
* O código H existente no nível da página é compatível com o AppMeasurement.
* A biblioteca oferece utilitários nativos para obter parâmetros de consulta, cookies de leitura e gravação e executar rastreamento de links avançado.
* A biblioteca não suporta variáveis de configuração de conta dinâmica (incluindo `dynamicAccountSelection`, `dynamicAccountMatch`e `dynamicAccountList`).
* O módulo Survey não é suportado.

As etapas a seguir descrevem um fluxo de trabalho de migração típico.

1. **Baixe o novo arquivo** AppMeasurement: Acesse o novo arquivo fazendo logon no Adobe Analytics e navegando até Admin > Gerenciador de código. O arquivo compactado baixado contém um `AppMeasurement.js` arquivo minified, juntamente com os módulos de mídia e integração.
1. **Copie suas`s_code.js`personalizações para`AppMeasurement.js`**: Mova todo o código antes da`DO NOT ALTER ANYTHING BELOW THIS LINE`seção`s_code.js`para o início de`AppMeasurement.js`.
1. **Atualizar todos os plug-ins**: Verifique se você está usando a versão mais recente de cada plug-in listado no seu `s_code.js` arquivo. Isso inclui os módulos de mídia e integração.
1. **Implantar o arquivo** AppMeasurement.js: Carregue seu `AppMeasurement.js` arquivo no servidor da Web.
1. **Atualizar referências de script para apontar para`AppMeasurement.js`**: Verifique se todas as páginas fazem referência`AppMeasurement.js`em vez de`s_code.js`.

## Exemplo de código Appmeasurement

Um `AppMeasurement.js` arquivo típico. Verifique se as variáveis de configuração estão definidas acima da `doPlugins` função.

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.sc.omtrdc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## Exemplo de código de página

Código comum que é carregado em cada página.

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

Certifique-se de incluir uma referência a `AppMeasurement.js` e `VisitorAPI.js` em cada página. Consulte Implementação [do](/help/implement/js/overview.md) JavaScript para obter mais informações.
