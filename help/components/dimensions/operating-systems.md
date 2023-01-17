---
title: Sistema operacional
description: O sistema operacional do visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 26de81f090cebb45473a04a2edbe281f1c8591a4
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 29%

---

# Sistema operacional

A dimensão “Sistema operacional” mostra o sistema operacional e a versão que o visitante usou. Se você tiver recursos em sua propriedade da Web que sejam específicos do SO, essa dimensão o ajudará a entender quais sistemas operacionais são mais comuns.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem sistemas operacionais que os visitantes usam. Os exemplos incluem `"Windows 10"`, `"OS X 10.15"` e `"Android 9"`.

## Alterações na rotulagem e definição

Abaixo está uma lista de problemas específicos com como o sistema operacional foi representado no Agente do usuário e nos relatórios do Adobe Analytics.

### Alteração na convenção de nomenclatura do sistema operacional Apple:

A partir da versão 11, usaremos o OS X em vez do sistema operacional Mac para fazer referência ao sistema operacional Apple.

Exemplos:

* macOS versão 10.15.7 (consulte a observação abaixo sobre a versão 10.15.7 sobre representação em cadeias de caracteres UA).
* OS X versão 11.0.0

### A versão do sistema operacional Mac está incorreta no Agente do usuário após a versão 10.15.7 

A partir de janeiro de 2023, o Agente do usuário em todos os navegadores mostrará a versão do sistema operacional Mac como 10.15.7, mesmo para versões mais recentes. Isso foi feito porque a inclusão da versão 11 no AI aparentemente causou problemas em alguns sites. A Apple também observa que a inclusão de uma versão incorreta do SO no UA oferece alguns benefícios de privacidade.

Observe que as dicas do cliente incluem a versão correta na dica de versão da plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Esta é uma dica de alta entropia, portanto, não é coletada automaticamente pelo Adobe. Consulte a [Perguntas frequentes sobre dicas do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obter detalhes sobre como coletar dicas de alta entropia.

### A versão do Windows está incorreta no Agente do Usuário que inicia com o Windows 11

A partir de janeiro de 2023, o Agente do usuário em todos os navegadores mostrará o Windows 11 como Windows 10.

Observe que as dicas do cliente incluem a versão correta na dica de versão da plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Esta é uma dica de alta entropia, portanto, não é coletada automaticamente pelo Adobe. Consulte a [Perguntas frequentes sobre dicas do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obter detalhes sobre como coletar dicas de alta entropia.
