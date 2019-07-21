---
description: A tabela a seguir contém uma lista de tarefas necessárias para migrar sua implementação.
keywords: Implementação do Analytics; appmeasurement; migrar; migrando; javascript
seo-description: A tabela a seguir contém uma lista de tarefas necessárias para migrar sua implementação.
seo-title: Migrando para o AppMeasurement para JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrando para o AppMeasurement para JavaScript
topic: Desenvolvedor e implementação
uuid: 5 be 345 a 8-5 a 95-4176-a 2 e 6-97139 b 9 b 46 ce
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Migrando para o AppMeasurement para JavaScript

A tabela a seguir contém uma lista de tarefas necessárias para migrar sua implementação.

>[!NOTE]
>
>We recommend migrating to the [Identity Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) Verificar a compatibilidade de plug-in

Onde: s\_ code. js

Alguns plug-ins não são mais suportados. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) .

![](assets/step2_icon.png) Baixar o novo AppMeasurement

Onde: Administrador &gt; Gerenciador de código

O zip do download contém um arquivo minified AppMeasurement.js e arquivos JavaScript para os módulos de mídia e integração.

![](assets/step3_icon.png) Copie a personalização s\_ code. js para `AppMeasurement.js`.

Onde: s\_ code. js e appmeasurement. js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (Opcional) Atualizar plug-ins

Onde: Appmeasurement. js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (Opcional) Atualizar módulos de mídia e integração

Onde: Appmeasurement. js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Implantar o novo JavaScript

Onde: Seu site

O novo arquivo JavaScript pode ser implantado de acordo com seu processo padrão. O código de página existente é compatível com essa versão.