---
description: O exemplo ilustra o uso de uma tag de imagem gerada no servidor dentro de uma página HTML de amostra.
keywords: Analytics Implementation;variables
solution: Analytics
title: Código de exemplo
topic: Developer and implementation
uuid: 47e5e82c-cfb2-4912-919b-720b2ee852ba
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Código de exemplo

O exemplo ilustra o uso de uma tag de imagem gerada no servidor dentro de uma página HTML de amostra.

A tabela abaixo exibe os valores usados na amostra.

| Variável | Valor |
|---|---|
| pageName | Confirmação de pedido |
| URL atual | https://www.somesite.com/cart/confirmation.asp |
| events | purchase,event1 |
| c1 | Registrado |
| purchaseID | 0123456 |
| products | Books;Book Name;1;19.95 |
| state | CA |
| zip | 90210 |
| um número aleatório | 123456 |

## Exemplo 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

O exemplo abaixo exibe uma tag de imagem do lado do servidor. O número aleatório realçado impede o armazenamento da imagem em cache.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456.
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## Exemplo 2 {#section_726D12029583428BA853043F988ED1B8}

O exemplo abaixo mostra uma tag mínima da imagem de JavaScript.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456.
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 
```

