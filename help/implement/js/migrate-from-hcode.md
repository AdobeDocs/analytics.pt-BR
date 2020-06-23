---
title: Migrar para o AppMeasurement para JavaScript
description: Determine o que é necessário para migrar a implementação do Código H.
translation-type: ht
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Migrar para o AppMeasurement para JavaScript

Se sua implementação ainda usar o Código H, a Adobe recomenda migrar para a versão mais recente do AppMeasurement. Recomendamos a implementação do Analytics por meio do [Adobe Experience Platform Launch](../launch/overview.md), mas uma implementação atualizada do JavaScript pode ser usada.

As seguintes alterações notáveis estão presentes no AppMeasurement quando comparadas ao Código H:

* De 3 a 7 vezes mais rápido que o código H.
* Mais leve que o Código H - 21kb descompactado em comparação ao Código H, que possui 33kb descompactado.
* O código da biblioteca e da página pode ser implantado dentro da tag `<head>`.
* O Código H existente no nível da página é compatível com o AppMeasurement.
* A biblioteca oferece utilitários nativos para obter parâmetros de consulta, cookies de leitura e gravação e executar rastreamento de links avançado.
* A biblioteca não é compatível com variáveis de configuração de conta dinâmica (incluindo `dynamicAccountSelection`, `dynamicAccountMatch` e `dynamicAccountList`).
* O módulo Survey não é suportado.

As etapas a seguir descrevem um fluxo de trabalho de migração típico.

1. **Baixar o novo arquivo AppMeasurement**: acesse o novo arquivo ao fazer logon no Adobe Analytics e navegue até Admin > Gerenciador de código. O arquivo compactado baixado contém um arquivo `AppMeasurement.js` minificado, juntamente com os módulos de mídia e integração.
1. **Copiar as personalizações do`s_code.js`para`AppMeasurement.js`**: mova todo o código antes da seção`DO NOT ALTER ANYTHING BELOW THIS LINE`no`s_code.js`para o início do`AppMeasurement.js`.
1. **Atualizar todos os plug-ins**: verifique se está usando a versão mais recente de cada plug-in listado no arquivo `s_code.js`. Isso inclui os módulos Mídia e Integração.
1. **Implantar o arquivo AppMeasurement.js**: carregue o arquivo `AppMeasurement.js` no servidor da Web.
1. **Atualizar referências de script para apontar para`AppMeasurement.js`**: verifique se todas as páginas fazem referência a`AppMeasurement.js`em vez de`s_code.js`.

## Exemplo de código Appmeasurement

Um arquivo `AppMeasurement.js` típico. Verifique se as variáveis de configuração estão definidas acima da função `doPlugins`.

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

Certifique-se de incluir uma referência a `AppMeasurement.js` e `VisitorAPI.js` em cada página. Consulte [Implementação do JavaScript](/help/implement/js/overview.md) para obter mais informações.
