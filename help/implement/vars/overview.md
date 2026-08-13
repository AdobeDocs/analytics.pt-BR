---
title: Visão geral de variáveis, funções, métodos e plug-ins
description: Saiba quais variáveis podem ser incluídas nos dados enviados à Adobe para melhorar os relatórios.
keywords: appmeasurement,variáveis,vars,configuração,página,implementação
feature: Appmeasurement Implementation
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Jyw64eX30vu3tLyimiM5A-t9aTqkAZE0wrsd4i0BCmc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 417
ht-degree: 100%

---

# Visão geral de variáveis, funções, métodos e plug-ins

O Analytics oferece diversas variáveis para coletar dados do Analytics. As variáveis nesta seção são divididas em várias seções:

* **As variáveis** de página são valores normalmente usados diretamente nos relatórios. São ariáveis de página comuns `props`, `eVars` e `events`.
* **As variáveis** de configuração são valores de configurações que ajudam a garantir que os dados corretos cheguem à Adobe. São variáveis de configuração comuns `trackingServerSecure`, `charSet` e `linkTrackVars`. As variáveis de configuração normalmente não preenchem itens de dimensão.
* **Funções e métodos** são pedaços de código que executam uma tarefa específica quando referenciados. São funções comuns `t()`, `tl()` e `clearVars()`.

## Variáveis e métodos de implementação

A Adobe oferece várias maneiras de implementar o Adobe Analytics. Cada página oferece uma seção sobre como implementar a variável usando o SDK da Web, a extensão do Adobe Analytics e o AppMeasurement para JavaScript.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuração de variáveis](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/administration/manage-report-suites/configuring-variables-in-the-admin-console){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Ordem das operações

As bibliotecas do AppMeasurement publicadas pelo Adobe Analytics seguem uma ordem específica ao enviar dados à Adobe. Se você executar essas tarefas fora de ordem, os dados poderão ficar incompletos.

1. Se o site usar uma camada de dados, verifique se todas as variáveis aplicáveis foram preenchidas primeiro. Por exemplo, preencha o `adobeDataLayer.page.title` com o título da página. Consulte [Camada de dados](../prepare/data-layer.md) para obter mais informações.
2. Use a camada de dados para preencher as variáveis do Analytics. <br/>Se você usar tags na Adobe Experience Platform, essa tarefa será realizada usando elementos de dados entre elas. Os elementos de dados são preenchidos com valores da camada de dados. Por exemplo, o elemento de dados `Page Title` obtém o valor da variável de camada de dados `adobeDataLayer.page.title`. <br/>Em seguida, você pode usar o elemento de dados para preencher as variáveis do Analytics. Por exemplo, `eVar4` obtém o valor do elemento de dados `Page Title`. <br/>Consulte [Elementos de dados](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=pt-BR), [Mapear objetos de camada de dados para elementos de dados](../launch/layer-to-elements.md) e [Mapear elementos de dados de tag para variáveis do Analytics](../launch/elements-to-variable.md) para obter mais informações.
3. Por fim, chame a função de rastreamento. A maioria das bibliotecas do AppMeasurement usam o método `t()`, no entanto, alguns SDKs móveis usam `track()`. Quando a função de rastreamento é chamada, todas as variáveis compatíveis definidas no objeto do Analytics são enviadas à Adobe na forma de uma solicitação de imagem.

## Caracteres inválidos

Os caracteres e strings a seguir nunca são permitidos em variáveis JavaScript.

* Tabulação (`0x09`)
* Caractere de nova linha (`0x0D`)
* Nova linha (`0x0A`)
* Marcas HTML (por exemplo, `<b></b>` ou `&#153`)

Algumas variáveis têm limitações adicionais ou requisitos de sintaxe. Por exemplo, a variável [`products`](page-vars/products.md) reserva sinais de ponto e vírgula e vírgulas para delimitar produtos e categorias separados.
