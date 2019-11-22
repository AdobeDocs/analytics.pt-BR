---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# purchaseID

A é usada para impedir que um pedido seja contado várias vezes na geração de relatórios.


<!-- 

purchaseID.xml

 -->

Sempre que o evento de [!UICONTROL compra] for usado em seu site, você deve usar a variável *`purchaseID`*.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 20 bytes | purchaseID | Conversão &gt; Compras &gt; Conversão de Receita | "" |

Quando um visitante compra um item no seu site,  *`purchaseID`* é preenchida na página "Obrigado" no mesmo local que o evento [!UICONTROL purchase] é acionado. Se a *`purchaseID`* for preenchida, os produtos da página "Obrigado" serão contados apenas uma vez de acordo com *`purchaseID`*. Isso é crítico porque muitos visitantes do seu site salvarão a página "Obrigado" ou de "Confirmação" para seus objetivos próprios. A variável *`purchaseID`* impede a contagem das compras sempre que a página é exibida.

Além de impedir que os dados de compra sejam contados duas vezes, o *`purchaseID`*, quando usado, impede que todos os dados de conversão sejam contados duas vezes nos relatórios.

**Sintaxe e valores possíveis** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

O *`purchaseID`* deve ter até 20 caracteres e ser ASCII por padrão.

**Exemplos** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Configurações** {#section_1808631C96674380BF9C4A6D9A2C568E}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

A variável *`purchaseID`* permite que todas as variáveis de conversão da página sejam contadas apenas uma vez nos relatórios.
