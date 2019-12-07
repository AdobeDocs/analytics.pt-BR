---
description: O código do Analytics cria um objeto de imagem, uma imagem não visível que não é mostrada na sua página.
keywords: Analytics Implementation
title: Inserção do código do Analytics na marca do cabeçalho
topic: Developer and implementation
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Inserção do código do Analytics na marca do cabeçalho

O código do Analytics cria um objeto de imagem, uma imagem não visível que não é mostrada na sua página.

>[!NOTE]
>
>Esta seção se aplica apenas à implementação herdada de s_code.js. O [AppMeasurement para JavaScript. 1.0](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) oferece suporte à implantação da biblioteca e do código de página na tag `<head>`.

Anteriormente, uma prática comum de implementação era colocar o código JavaScript do Analytics entre as <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> e </head> específicos. Colocando o código entre essas tags, impede-se que a imagem de pixel de 1 x 1 retornada pela solicitação que enviou dados nos servidores da Adobe afetem o layout da página. Inserir o código no cabeçalho do documento significa que o código aparece é exibido mais cedo no código. Dessa forma, ele é executado antes, permitindo a você contar exibições de página para cargas parciais de página com mais eficiência.

Determinados elementos do código exigem a existência do objeto do corpo. Como os navegadores da Web executam código na ordem em que os recebem, se o código JavaScript do Analytics estiver no cabeçalho do documento, ele será executado antes de o objeto do corpo existir. Como resultado, sua implementação não coletará os dados do [!UICONTROL ClickMap] e o rastreamento automático dos downloads de arquivo ou links de [!UICONTROL saída] não estarão disponíveis. Você também não recebe dados do tipo de conexão ou dados da homepage do visitante. A inserção de código no cabeçalho do documento funciona, mas o resultado é uma versão muito limitada do Analytics, e os usuários poderão se perguntar por que determinados relatórios e ferramentas, incluindo o [!UICONTROL ClickMap], não estão registrando dados.

O código do Analytics pode ser colocado em qualquer lugar dentro das tags BODY (<BODY></BODY>) de uma página HTML bem formada. A Adobe recomenda colocar o código em um arquivo global de inclusão, na parte superior da página (dentro da tag do corpo HTML). O código pode ser inserido em qualquer lugar da página, exceto conforme observado abaixo:

* Se colocado em uma tabela, insira o código somente em <td></td> específicos. Por exemplo, não coloque o código entre uma tag de abertura <tr> e uma abertura <td> TAG.
* O código que define as variáveis deve ocorrer depois da referência ao arquivo s_code.js.
* Verifique se as [!UICONTROL IDs do conjunto de relatórios] na variável *`s_account`* no arquivo s_code.js estão definidas corretamente. Essa variável geralmente é definida corretamente durante o download de código do Gerenciador de Códigos para um conjunto de relatórios específico, ou conforme fornecido por um consultor técnico da Adobe.

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

