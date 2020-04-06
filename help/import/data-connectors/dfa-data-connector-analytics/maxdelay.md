---
title: maxDelay
description: Determine o tempo máximo de espera do AppMeasurement por uma resposta do DFA antes de enviar uma solicitação de imagem.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# maxDelay

A variável `s.maxDelay` é usada principalmente no conector de dados do DFA para determinar o período de tempo limite no contato com o host do DFA. Se a Adobe não receber uma resposta dos servidores do DFA dentro do período especificado definido nessa variável, a conexão será interrompida e os dados serão processados normalmente. Inclua esta variável na implementação se você estiver preocupado com o tempo de resposta do DFA em cada página. A Adobe recomenda fazer testes com esse valor para determinar o período de tempo limite ideal.

Essa variável é usada somente em implementações que usam o conector de dados do DFA. Mesmo em implementações que usam o DFA essa variável é opcional.

## Atraso máximo no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.maxDelay no AppMeasurement e no editor de código personalizado do Launch

A variável `s.maxDelay` é um número inteiro que representa o número de milissegundos da espera do AppMeasurement por uma resposta do DFA. Se o AppMeasurement não receber uma resposta do DFA a tempo, uma solicitação de imagem será enviada à Adobe sem dados do DFA.

```js
s.maxDelay = 750;
```

## Propriedades

* O aumento do tempo de espera coleta mais dados do DFA, mas também aumenta o risco de perder dados de ocorrência do Analytics. A perda dos dados de hit do Analytics acontece quando o usuário sai da página durante o período de `s.maxDelay`.
* A redução do tempo de espera reduzirá o risco de perda de dados de hit do Analytics, mas pode reduzir a quantidade de dados do DFA enviados com os dados de hit.
* A perda de dados de integração do DFA acontece quando o período de `s.maxDelay` não acomoda tempo suficiente para o host do DFA responder.

>[!NOTE] A Adobe não tem controle sobre o tempo de resposta do DFA. Se você observar problemas consistentes depois de elevar o período máximo de atraso a um prazo razoável, consulte o administrador da conta do DFA de sua organização.
