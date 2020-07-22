---
title: Visão geral sobre variáveis, funções, métodos e plug-ins
description: Saiba quais variáveis podem ser incluídas nos dados enviados à Adobe para melhorar os relatórios.
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 97%

---


# Visão geral sobre variáveis, funções, métodos e plug-ins

O Analytics oferece diversas variáveis para coletar dados do Analytics. As variáveis nesta seção são divididas em várias seções:

* **As variáveis** de página são valores normalmente usados diretamente nos relatórios. São ariáveis de página comuns `props`, `eVars` e `events`.
* **As variáveis** de configuração são valores de configurações que ajudam a garantir que os dados corretos cheguem à Adobe. São variáveis de configuração comuns `trackingServerSecure`, `charSet` e `linkTrackVars`. As variáveis de configuração normalmente não preenchem itens de dimensão.
* **Funções e métodos** são pedaços de código que executam uma tarefa específica quando referenciados. São funções comuns `t()`, `tl()` e `clearVars()`.

## Variáveis e métodos de implementação

A Adobe oferece várias maneiras de implementar o Adobe Analytics. Cada página oferece uma seção sobre como implementar a variável usando o Launch e o AppMeasurement para JavaScript.

## Ordem das operações

As bibliotecas do AppMeasurement publicadas pelo Adobe Analytics seguem uma ordem específica ao enviar dados à Adobe. Se você executar essas tarefas fora de ordem, os dados poderão ficar incompletos.

1. Se o site usar uma camada de dados, verifique se todas as variáveis aplicáveis foram preenchidas primeiro. Consulte [Camada de dados](../prepare/data-layer.md) para obter mais informações.
2. Use a camada de dados para preencher as variáveis do Analytics. Se você usar o Launch, essa tarefa será facilmente realizada usando elementos de dados e, em seguida, atribuindo o elemento de dados a uma variável. Consulte [Elementos de dados](https://docs.adobe.com/content/help/pt-BR/launch/using/reference/manage-resources/data-elements.html) no guia do usuário do Launch.
3. Chame a função de rastreamento. A maioria das bibliotecas do AppMeasurement usam o método `t()`, no entanto, alguns SDKs móveis usam `track()`. Quando a função de rastreamento é chamada, todas as variáveis compatíveis definidas no objeto do Analytics são enviadas à Adobe na forma de uma solicitação de imagem.

## Caracteres inválidos

Os caracteres e strings a seguir nunca são permitidos em variáveis JavaScript.

* Tabulação (`0x09`)
* Caractere de nova linha (`0x0D`)
* Nova linha (`0x0A`)
* Marcas HTML (por exemplo, `<b></b>` ou `&#153`)

Algumas variáveis têm limitações adicionais ou requisitos de sintaxe. Por exemplo, a variável `products` reserva sinais de ponto e vírgula e vírgulas para delimitar produtos e categorias separados.
