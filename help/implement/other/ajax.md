---
title: Implementação com AJAX
description: Saiba como implementar o Adobe Analytics em um site usando o AJAX.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

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

>[!NOTE] Nem todas as interações ou cliques precisam ser registrados. Considere cuidadosamente quais ações são mais importantes a serem rastreadas e envie dados para a Adobe.

## Limpar variáveis em cada página

Os valores da variável persistem nas páginas que usam AJAX, pois a página não é recarregada. Portanto, é necessário acomodar especificamente os valores de variável para que eles não persistam incorretamente nas ocorrências. A Adobe oferece a função [`clearVars`](../vars/functions/clearvars.md) para eliminar facilmente os valores de variáveis. Certifique-se de usar essa função depois de enviar cada ocorrência para a Adobe e antes de definir valores de variável para a próxima ocorrência.

>[!TIP] A função `clearVars()` não está disponível no Código H. Se não tiver atualizado para o AppMeasurement, defina cada valor de variável do Analytics como uma cadeia de caracteres vazia.

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
