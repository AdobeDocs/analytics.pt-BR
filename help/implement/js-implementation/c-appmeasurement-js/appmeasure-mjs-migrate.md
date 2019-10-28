---
description: A tabela a seguir contém uma lista de tarefas necessárias para migrar sua implementação.
keywords: Implementação do Analytics, appmeasurement, migrar, migração, javascript
seo-description: A tabela a seguir contém uma lista de tarefas necessárias para migrar sua implementação.
seo-title: Migrando para o AppMeasurement para JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrando para o AppMeasurement para JavaScript
topic: Desenvolvedor e implementação
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: ht
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Migrando para o AppMeasurement para JavaScript

A tabela a seguir contém uma lista de tarefas necessárias para migrar sua implementação.

>[!NOTE]
>
>Recomendamos migrar para o [Serviço de identidade](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) ao migrar para [!DNL AppMeasurement] para JavaScript.

![](assets/step1_icon.png) Verificar a compatibilidade de plug-in

Onde: s\_code.js

Alguns plug-ins não são mais suportados. Consulte [Suporte ao plug-in AppMeasurement](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

![](assets/step2_icon.png) Baixar o novo AppMeasurement

Onde: Admin &gt; Gerenciador de código

O zip do download contém um arquivo minified AppMeasurement.js e arquivos JavaScript para os módulos de mídia e integração.

![](assets/step3_icon.png) Copiar sua personalização do s_code.js em `AppMeasurement.js`.

Onde: s\_code.js e AppMeasurement.js

Mova todos os códigos que aparecem antes da seção `DO NOT ALTER ANYTHING BELOW THIS LINE` em s\_code.js para o início do AppMeasurement.js.

![](assets/step4_icon.png) (Opcional) Atualizar plug-ins

Onde: AppMeasurement.js

Se você estiver usando o plug-in getQueryParam, atualize essas chamadas para usar o novo utilitário, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (Opcional) Atualizar módulos de mídia e integração

Onde: AppMeasurement.js

Se você estiver usando um desses módulos, copie o código de AppMeasurement\_Module\_Media.js e/ou AppMeasurement\_Module\_Integrate.js e cole-o antes de `DO NOT ALTER ANYTHING BELOW THIS LINE` em AppMeasurement.js.

![](assets/step6_icon.png) Implantar o novo JavaScript

Onde: o site

O novo arquivo JavaScript pode ser implantado de acordo com seu processo padrão. O código de página existente é compatível com essa versão.