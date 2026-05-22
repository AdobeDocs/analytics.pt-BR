---
title: Implementação com AJAX
description: Saiba como implementar o Adobe Analytics em um site usando o AJAX.
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
role: Developer
autotag-review: '2026-05-22T08:06:40.936Z'
TQID: 'https://experienceleague.adobe.com/M0MNFZRcHpPwxL-ZtTky67DHDr1A0fL-peaGKicXgIM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 373
ht-degree: 100%

---

# Implementação com AJAX

AJAX é uma prática de usar o JavaScript e o HTML para limpar e gerar conteúdo sem carregar uma nova página.

O Adobe Analytics geralmente depende da recarga de páginas para redefinir o objeto de rastreamento do Analytics. Toda vez que você navega para um URL diferente, todas as variáveis do Analytics são redefinidas e podem ser definidas novamente. Ao usar o AJAX no site, ajuste a implementação na falta de atualizações de página para garantir que os dados não persistam incorretamente entre as ocorrências.

Depois de tomar medidas para apagar valores de variável, a implementação do Adobe Analytics em sites que usam AJAX será a mesma de outros métodos de implementação.

## Determinar interações e tipos de ocorrência

Como as páginas que usam AJAX geralmente não são recarregadas, há várias interações que um usuário pode realizar no site. Ao implementar o Adobe Analytics, certifique-se de diferenciar as exibições de página das chamadas de rastreamento de link. Considere a seguinte pergunta para cada interação que um usuário pode fazer no site:

*Quando um usuário interage com meu site, essa interação altera o conteúdo o suficiente na página para se qualificar como uma nova página?*

* Se a resposta for **sim**, considere usar uma chamada de rastreamento de exibição de página (`s.t()`).
* Se a resposta for **não**, considere rastrear essa interação usando uma chamada de rastreamento de link (`s.tl()`).

>[!NOTE]
>
>Nem todas as interações ou cliques precisam ser registrados. Considere cuidadosamente quais ações são mais importantes a serem rastreadas e envie dados para a Adobe.

## Limpar variáveis em cada página

Os valores da variável persistem nas páginas que usam AJAX, pois a página não é recarregada. Portanto, é necessário acomodar especificamente os valores de variável para que eles não persistam incorretamente nas ocorrências. A Adobe oferece a função [`clearVars`](../vars/functions/clearvars.md) para eliminar facilmente os valores de variáveis. Certifique-se de usar essa função depois de enviar cada ocorrência para a Adobe e antes de definir valores de variável para a próxima ocorrência.

>[!TIP]
>
>A função `clearVars()` não está disponível no Código H. Se não tiver atualizado para o AppMeasurement, defina cada valor de variável do Analytics como uma cadeia de caracteres vazia.

## Exemplos

O exemplo a seguir usa um JavaScript simples para apagar valores de variáveis existentes, definir novos valores e enviar uma solicitação de imagem à Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

O exemplo a seguir mostra uma chamada de rastreamento no retorno de chamada `done` da função `.ajax` de JQuery:

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```
