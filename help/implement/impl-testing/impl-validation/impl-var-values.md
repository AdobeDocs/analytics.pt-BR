---
description: Verifique se as variáveis foram preenchidas com base no script de servidor ou o código não poderá gerar nenhuma marca de cotação que interfira com os valores.
keywords: Analytics Implementation
solution: Analytics
title: Variáveis e valores
topic: Developer and implementation
uuid: 2ff4857a-9451-4794-9146-f417abd1d1ba
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variáveis e valores

Verifique se as variáveis foram preenchidas com base no script de servidor ou o código não poderá gerar nenhuma marca de cotação que interfira com os valores.

Por exemplo:

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

Verifique se os valores das variáveis não excedem os limites máximos, especificados neste documento. Caracteres adicionais serão cortados nos servidores de coleta de dados. Eles podem interferir com o tamanho total, aumentar a largura de banda desnecessariamente e causar outros problemas.

Não use $, ™, ®, © ou vírgulas (,) na variável products. Geralmente, esses caracteres não são úteis em nenhuma variável do [!DNL Analytics] e podem interferir com a capacidade de interpretar ou exportar campos. A prática recomendada é limitar os caracteres aos primeiros 127 caracteres ASCII.

Verifique se a variável de eventos está preenchida com um valor apropriado ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen] ou event1-event5) sempre que *`products`* estiver preenchido. Verifique se o uso de letras maiúsculas e minúsculas de todas as variáveis e funções do [!DNL Analytics] foi mantido, como mostrado abaixo.

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 
```

Os nomes de página fazem distinção de letras maiúsculas e minúsculas e as diferenças criam registros de páginas adicionais. "Home" e "home" são duas páginas diferentes no [!DNL Analytics].

> [!NOTE] Não é possível combinar vários registros de página nos relatórios.

Valide os links reportados no relatório [!UICONTROL Links personalizados]. Verifique se os parâmetros corretos foram transmitidos para a função [!UICONTROL tl]. Para obter mais informações sobre [!UICONTROL links personalizados], consulte [Rastreamento de link](/help/implement/js-implementation/function-tl.md).
