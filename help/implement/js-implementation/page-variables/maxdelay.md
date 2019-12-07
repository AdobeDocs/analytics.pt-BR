---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# maxDelay

A variável s.maxDelay é usada principalmente nas integrações do Genesis DFA para determinar o período de tempo limite no contato com o host de DFA. Se a Adobe não receber uma resposta dos servidores DFA dentro do período especificado definido na variável, a conexão será interrompida e os dados serão processados normalmente. Implemente esta variável se você estiver preocupado com o tempo de resposta de DFA em cada página. É recomendável experimentar este valor para determinar o período ideal do tempo limite.


<!-- 

maxDelay.xml

 -->

**Exemplo de implementação**

```
s.maxDelay="750";
```

**Propriedades**

* Esta variável é uma métrica de evento opcional preenchida pelo JavaScript implementado em seu site.
* Se o host DFA não responder no tempo determinado, o evento designado como Tempo limite será executado (atribuído pelo assistente de integração do Genesis).
* Essa variável só pode conter valor numérico.
* O tempo especificado é medido em milissegundos.
* O aumento do tempo de espera coleta mais dados de DFA, mas também aumenta o risco de perder dados de ocorrência do Analytics.

   A perda dos dados de hit do Analytics acontece quando o usuário sai da página durante o período de *`s.maxDelay`*.

* A redução do tempo de espera reduzirá o risco de perda de dados de ocorrência do Analytics, mas pode reduzir a quantidade de dados de DFA enviados com os dados de ocorrência.

   A perda de dados de integração do DFA ocorreria quando o período *`s.maxDelay`* não acomodasse tempo suficiente para o host do DFA responder.

> [!NOTE] A Adobe não tem controle sobre o tempo de resposta do DFA. Se você estiver observando problemas consistentes depois de elevar o período máximo de atraso a um prazo razoável, consulte o administrador da conta do DFA de sua organização.
