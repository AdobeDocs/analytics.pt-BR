---
description: Verifique se as variáveis foram preenchidas com base no script de servidor ou o código não poderá gerar nenhuma marca de cotação que interfira com os valores.
keywords: Implementação do Analytics
seo-description: Verifique se as variáveis foram preenchidas com base no script de servidor ou o código não poderá gerar nenhuma marca de cotação que interfira com os valores.
seo-title: Variáveis e valores
solution: Analytics
title: Variáveis e valores
topic: Desenvolvedor e implementação
uuid: 2 ff 4857 a -9451-4794-9146-f 417 abd 1 d 1 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. Verifique se o uso de letras maiúsculas e minúsculas de todas as variáveis e funções do [!DNL Analytics] foi mantido, como mostrado abaixo.

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

>[!NOTE]
>
>Vários registros de página não podem ser combinados nos relatórios.

Valide os links reportados no relatório [!UICONTROL Links personalizados]. Verifique se os parâmetros corretos foram transmitidos para a função [!UICONTROL tl]. Para obter mais informações sobre [!UICONTROL links personalizados], consulte [Rastreamento de link](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E).
