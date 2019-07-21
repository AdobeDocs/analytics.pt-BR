---
description: O código do Analytics cria um objeto de imagem, uma imagem não visível que não é mostrada na sua página.
keywords: Implementação do Analytics
seo-description: O código do Analytics cria um objeto de imagem, uma imagem não visível que não é mostrada na sua página.
seo-title: Inserção de código do Analytics na marca de cabeçalho
solution: Analytics
title: Inserção de código do Analytics na marca de cabeçalho
topic: Desenvolvedor e implementação
uuid: e 8 f 91 d 3 c-cb 72-454 d -9 bd 4-ff 54 d 83 d 981 f
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Inserção de código do Analytics na marca de cabeçalho

O código do Analytics cria um objeto de imagem, uma imagem não visível que não é mostrada na sua página.

>[!NOTE]
>
>Esta seção se aplica somente à implementação herdada s_ code. js. [O appmeasurement para javascript 1.0](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) oferece suporte à implantação da biblioteca e do código da página na `<head>` tag.

Anteriormente, uma prática comum de implementação era colocar o código javascript do Analytics entre a variável <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> e </head> específicos. Colocando o código entre essas tags, impede-se que a imagem de pixel de 1 x 1 retornada pela solicitação que enviou dados nos servidores da Adobe afetem o layout da página. Inserir o código no cabeçalho do documento significa que o código aparece é exibido mais cedo no código. Dessa forma, ele é executado antes, permitindo a você contar exibições de página para cargas parciais de página com mais eficiência.

Determinados elementos do código exigem a existência do objeto do corpo. Como os navegadores da Web executam código na ordem em que os recebem, se o código JavaScript do Analytics estiver no cabeçalho do documento, ele será executado antes de o objeto do corpo existir. Como resultado, sua implementação não coletará os dados do [!UICONTROL ClickMap] e o rastreamento automático dos downloads de arquivo ou links de [!UICONTROL saída] não estarão disponíveis. Você também não recebe dados do tipo de conexão ou dados da homepage do visitante. A inserção de código no cabeçalho do documento funciona, mas o resultado é uma versão muito limitada do Analytics, e os usuários poderão se perguntar por que determinados relatórios e ferramentas, incluindo o [!UICONTROL ClickMap], não estão registrando dados.

O código do Analytics pode ser inserido em qualquer lugar dentro das tags BODY (<BODY></BODY>) de uma página HTML bem formada. A Adobe recomenda colocar o código em um arquivo global de inclusão, na parte superior da página (dentro da tag do corpo HTML). O código pode ser inserido em qualquer lugar da página, exceto conforme observado abaixo:

* Se colocado em uma tabela, publique o código apenas na variável <td></td> específicos. Por exemplo, não coloque o código entre uma abertura <tr> tag e abertura <td> tag.
* O código que define as variáveis deve ocorrer depois da referência ao arquivo s_code.js.
* Make certain that the [!UICONTROL report suite ID]s in the *`s_account`* variable in the s_code.js file are set correctly. Essa variável geralmente é definida corretamente durante o download de código do Gerenciador de Códigos para um conjunto de relatórios específico, ou conforme fornecido por um consultor técnico da Adobe.

Se você quiser integrar o Analytics com o Alvo, o arquivo de inclusão do JavaScript deverá ser colocado na parte inferior da página. Os exemplos a seguir mostram o posicionamento correto do código do Analytics:

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3. 
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 
```

