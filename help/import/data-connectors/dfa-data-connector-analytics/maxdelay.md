---
title: maxDelay
description: Determine o tempo máximo que o AppMeasurement aguarda por uma resposta do DFA antes de enviar uma solicitação de imagem.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

The `s.maxDelay` variable is used in the DFA data connector to determine the timeout period in contacting the DFA host. Se a Adobe não receber uma resposta dos servidores do DFA dentro do período especificado definido nessa variável, a conexão será interrompida e os dados serão processados normalmente. Inclua essa variável na sua implementação se estiver preocupado com o tempo de resposta do DFA em cada página. A Adobe recomenda fazer testes com esse valor para determinar o período de tempo limite ideal.

Essa variável é usada somente em implementações que usam o conector de dados do DFA. Mesmo com implementações usando o DFA, essa variável é opcional.

## Atraso máximo no lançamento da plataforma Adobe Experience

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.maxDelay no AppMeasurement e Iniciar editor de código personalizado

A `s.maxDelay` variável é um número inteiro que representa o número de milissegundos que o AppMeasurement aguarda por uma resposta do DFA. Se o AppMeasurement não receber uma resposta do DFA a tempo, uma solicitação de imagem será enviada para a Adobe sem dados do DFA.

```js
s.maxDelay = 750;
```

## Propriedades

* O aumento do tempo de espera coleta mais dados de DFA, mas também aumenta o risco de perder dados de ocorrência do Analytics. Losing Analytics hit data happens when the user navigates away from the page during the `s.maxDelay` period.
* A redução do tempo de espera diminui o risco de perda de dados de ocorrência do Analytics, mas pode reduzir a quantidade de dados do DFA enviados com dados de ocorrência.
* Losing DFA integration data happens when the `s.maxDelay` period does not accommodate enough time for the DFA host to respond.

> [!NOTE] A Adobe não tem controle sobre o tempo de resposta do DFA. Se você encontrar problemas consistentes mesmo depois de elevar o período máximo de atraso para um período razoável, consulte o administrador da conta do DFA de sua organização.
