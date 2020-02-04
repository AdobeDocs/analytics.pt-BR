---
title: Visão geral de variáveis, funções, métodos e plug-ins
description: Saiba quais variáveis podem ser incluídas nos dados enviados à Adobe para melhorar os relatórios.
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# Visão geral de variáveis, funções, métodos e plug-ins

O Analytics oferece diversas variáveis para coletar dados do Analytics. As variáveis nesta seção são divididas em várias seções:

* **As variáveis** de página são valores normalmente usados diretamente nos relatórios. As variáveis de página comuns incluem `props`, `eVars`e `events`.
* **As variáveis** de configuração são valores de configurações que ajudam a garantir que os dados corretos cheguem à Adobe. As variáveis de configuração comuns incluem `trackingServerSecure`, `charSet`e `linkTrackVars`. As variáveis de configuração normalmente não preenchem valores de dimensão.
* **Funções e métodos** são pedaços de código que executam uma tarefa específica quando referenciados. As funções comuns incluem `t()`, `tl()`e `clearVars()`.

## Variáveis e métodos de implementação

A Adobe oferece várias maneiras de implementar o Adobe Analytics. Cada página oferece uma seção sobre como implementar a variável usando Launch e AppMeasurement para JavaScript.

## Ordem de funcionamento

As bibliotecas do AppMeasurement publicadas pelo Adobe Analytics seguem uma ordem específica ao enviar dados para a Adobe. Se você executar essas tarefas fora de ordem, os dados poderão estar incompletos.

1. Se o site usar uma camada de dados, verifique se todas as variáveis aplicáveis foram preenchidas primeiro. See [Data layer](../prepare/data-layer.md) for more information.
2. Use a camada de dados para preencher as variáveis do Analytics. Se você usar o Launch, essa tarefa será facilmente realizada usando elementos de dados e, em seguida, atribuindo o elemento de dados a uma variável. Consulte Elementos [de dados](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html) no guia do usuário Iniciar.
3. Chame a função de rastreamento. A maioria das bibliotecas do AppMeasurement usam a `t()` função, no entanto, alguns SDKs móveis usam `track()`. Quando a função de rastreamento é chamada, todas as variáveis compatíveis definidas no objeto do Analytics são enviadas para a Adobe na forma de uma solicitação de imagem.

## Caracteres ilegais

Os caracteres e strings a seguir nunca são permitidos em variáveis JavaScript.

* Tabulação (`0x09`)
* Retorno de carro (`0x0D`)
* Nova linha (`0x0A`)
* Marcas HTML (por exemplo, `<b></b>` ou `&#153`)

Algumas variáveis têm limitações adicionais ou requisitos de sintaxe. Por exemplo, a `products` variável reserva pontos-e-vírgulas e vírgulas para delimitar produtos e categorias separados.
