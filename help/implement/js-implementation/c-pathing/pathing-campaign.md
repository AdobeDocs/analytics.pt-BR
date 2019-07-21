---
description: Ajuda a responder a pergunta "Depois que um usuário clica no meu site por uma campanha, para onde ele vai no meu site?".
keywords: Implementação do Analytics
seo-description: Ajuda a responder a pergunta "Depois que um usuário clica no meu site por uma campanha, para onde ele vai no meu site?".
seo-title: Definição de caminho por campanha ou código de rastreamento
solution: Analytics
title: Definição de caminho por campanha ou código de rastreamento
topic: Desenvolvedor e implementação
uuid: eb 6 e 3484-1 b 40-4 ec 6-8017-ac 1003 cdf 636
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Definição de caminho por campanha ou código de rastreamento

Ajuda a responder a pergunta "Depois que um usuário clica no meu site por uma campanha, para onde ele vai no meu site?".

Para responder essa pergunta, você deverá definir uma [!UICONTROL sprop] que será usada para este relatório. Em seguida, você deve estruturar os dados para preenchimento na prop, de forma que faça sentido quando a definição de caminho for ativada.

Para este exemplo, você usará [!UICONTROL prop1] como prop de definição de caminho da campanha. Agora, você decide preencher essa [!UICONTROL sprop] com o mesmo valor colocado na variável [!UICONTROL page name]. Consulte abaixo:

```js
s.prop1=s.pageName;
```

Você deverá fazer isso em todas as páginas, a menos que a pessoa tenha clicado de uma campanha. Se isso tiver acontecido e a pessoa estiver na página inicial da campanha, você poderá preencher a prop com uma concatenação da campanha e da [!UICONTROL pagename]. Consulte abaixo:

```js
 s.prop1=s.campaign + ‘ : ’ + s.pageName;
```

Se a campanha em que ela clicou se chamava "banner1234" e a página a que ela chegou se chamava "Homepage", o valor da prop seria "banner1234 : Home Page". Em todas as páginas subsequentes, você coloca [!UICONTROL pagename] na prop, como mostrado acima.

Quando um usuário clica nesta campanha e exibe quatro páginas no total na visita, você obtém os valores a seguir na sprop, nesta ordem:

```js
“banner1234 : Home Page” > “Page 2” > “Page 3” > “Page 4”
```

Com nossos dados capturados na [!UICONTROL prop1] dessa forma e com a definição de caminho realizada nesta prop, você agora pode observar um dos vários relatórios de definição de caminho para compreender os caminhos adotados no site depois do clique por uma campanha.

Você pode especificar a página inicial pela qual começar o relatório de caminho. Nesse caso, você selecionou "banner1234 : Home Page", pois quer saber para onde os usuários foram depois que clicaram em "banner 1234" pela campanha. Este relatório é somente um exemplo de um dos muitos relatórios de caminho.
