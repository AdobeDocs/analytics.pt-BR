---
description: A função s.t() é a que compila todas as variáveis definidas nessa página em uma solicitação de imagem e a envia a todos os nossos servidores.
keywords: track;Analytics Implementation;page tracking;track page
subtopic: Functions
title: A função s.t() - Rastreamento de página
topic: Developer and implementation
uuid: 67696e46-1e0d-4200-bfad-4217d1023948
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# A função s.t() - Rastreamento de página

A função s.t() é a que compila todas as variáveis definidas nessa página em uma solicitação de imagem e a envia a todos os nossos servidores.

## Propriedades da função {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* A remoção da chamada de [!UICONTROL s.t()] impede que os dados chegam ao [!DNL Analytics]. Várias chamadas de [!UICONTROL s.t()] acionam várias solicitações de imagem (dobrando o tráfego reportado em seu site).

* Se você quiser acionar mais que uma solicitação de imagem em uma única carga de página, é recomendável usar a função [!UICONTROL s.t()].
* O acionamento dessa função sempre aumenta as [!UICONTROL pageviews] e sempre inclui a variável [!UICONTROL s.pageName].

## Implementação {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

Ao gerar código dentro do [!UICONTROL gerenciador de código,] você recebe o seguinte na parte inferior do código da página:

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

Cada linha do código tem uma finalidade específica:

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

Essa linha de código é o que, na realidade, aciona a função JavaScript. A variável [!UICONTROL s_code] e seu método document.write é destinada aos navegadores que não suportam objetos de imagem (Navegadores Netscape anteriores à versão 3 e Internet Explorer anteriores à versão 4. Estima-se que menos que 5% de todos os usuários de internet).

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

Se você tiver dúvidas adicionais sobre a função [!UICONTROL s.t()], entre em contato com o gerente de conta da sua organização. Ele pode agendar uma reunião com um consultor de implementação da Adobe, que pode fornecer assistência.
