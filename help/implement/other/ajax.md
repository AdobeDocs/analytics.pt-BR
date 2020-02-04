---
title: Implementação com AJAX
description: Saiba como implementar o Adobe Analytics em um site usando o AJAX.
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# Implementação com AJAX

AJAX é uma prática de usar JavaScript e HTML para limpar e gerar conteúdo sem carregar uma nova página.

O Adobe Analytics normalmente depende da recarga de páginas para redefinir o objeto de rastreamento do Analytics. Toda vez que você navega para um URL diferente, todas as variáveis do Analytics são redefinidas e podem ser definidas novamente. Ao usar o AJAX em seu site, ajuste sua implementação na falta de atualizações de página para garantir que os dados não persistam incorretamente entre as ocorrências.

Depois que você tiver medidas para apagar valores variáveis, a implementação do Adobe Analytics em sites que usam AJAX será a mesma de outros métodos de implementação.

## Determinar interações e tipos de ocorrência

Como as páginas que usam AJAX normalmente não são recarregadas, há várias interações que um usuário pode realizar no seu site. Ao implementar o Adobe Analytics, certifique-se de diferenciar as exibições de página das chamadas de rastreamento de link. Considere a seguinte pergunta para cada interação que um usuário pode fazer no seu site:

*Quando um usuário interage com meu site, essa interação altera o suficiente do conteúdo na página para se qualificar como uma nova página?*

* Se a resposta for **sim**, considere usar uma chamada de rastreamento de exibição de página (`s.t()`).
* Se a resposta for **não**, considere rastrear essa interação usando uma chamada de rastreamento de link (`s.tl()`).

> [!NOTE] Nem todas as interações ou cliques precisam ser registrados. Considere cuidadosamente quais ações são mais importantes para rastrear e envie dados para a Adobe de acordo.

## Limpar variáveis em cada página

Os valores da variável persistem nas páginas que usam AJAX, pois a página não é recarregada. Portanto, é necessário acomodar especificamente os valores variáveis para que eles não persistam incorretamente nas ocorrências. A Adobe oferece a [`clearVars`](../vars/functions/clearvars.md) função de eliminar facilmente os valores variáveis. Certifique-se de usar essa função depois de enviar cada ocorrência para a Adobe e antes de definir valores de variável para a próxima ocorrência.

> [!TIP] A `clearVars()` função não está disponível no Código H. Se você não tiver atualizado para o AppMeasurement, defina cada valor de variável do Analytics como uma string vazia.

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
