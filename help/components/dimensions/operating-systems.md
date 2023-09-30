---
title: Sistema operacional
description: O sistema operacional do visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 24972ec79cb42224a97dda6b073b517b301113ba
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 18%

---

# Sistema operacional

O &#39;Sistema operacional&#39; [dimension](overview.md) mostra o sistema operacional e a versão que o visitante usou. Se você tiver recursos em sua propriedade da Web que sejam específicos do SO, essa dimensão o ajudará a entender quais sistemas operacionais são mais comuns.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. parceiros Adobe com [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente do usuário e o sistema operacional.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do SDK da Web, habilite [!UICONTROL Pesquisa de dispositivo] quando [configurar um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens de dimensão incluem sistemas operacionais que os visitantes usam. Os exemplos incluem `"Windows 10"`, `"OS X 10.15"` e `"Android 9"`.

## Alterações da rotulagem e da definição

Veja abaixo uma lista de problemas específicos com o modo como o sistema operacional foi representado no usuário-agente e nos relatórios do Adobe Analytics.

### Alteração na granularidade do sistema operacional

Em 2 de março de 2023, atualizamos nossos relatórios para incluir mais detalhes no sistema operacional. Após essa data incluiremos a versão do patch do sistema operacional. Assim, por exemplo, um usuário com OS X 10.15.7 teria aparecido como &quot;OS X 10.15&quot; antes de 2 de março. Depois de 2 de março, eles aparecerão como &quot;OS X 10.15.7&quot;.

### Alteração na convenção de nomenclatura do sistema operacional Apple:

A partir da versão 11, usaremos o MacOS em vez do OS X para consultar o sistema operacional Apple.

Exemplos:

* &quot;OS X 10.15&quot; (veja a nota abaixo sobre a versão 10.15.7 sobre a representação em strings UA).
* &quot;MacOS 11.0.0

### A versão do Mac OS está incorreta no Agente do usuário após a versão 10.15.7 

O Agente do usuário em computadores Apple mostra a versão do SO como 10.15.7, mesmo para versões mais recentes. Isso foi feito porque a inclusão da versão 11 no UA aparentemente causou problemas em alguns sites. Isso é verdadeiro para *todos os navegadores* e não está relacionado ao &quot;congelamento&quot; do agente do usuário do Google em navegadores Chromium.

Observe que as dicas do cliente incluem a versão correta na dica de versão da plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Essa é uma dica de alta entropia, portanto, não é coletada automaticamente pelo Adobe. Consulte a [Perguntas frequentes sobre Adobe Analytics Hints](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obter detalhes sobre como coletar dicas de alta entropia.

### A versão do Windows está incorreta no Agente do usuário a partir do Windows 11

A partir de janeiro de 2023, o agente do usuário em todos os navegadores mostrará que representa o Windows 11 como o Windows 10.

Observe que as dicas do cliente incluem a versão correta na dica de versão da plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Essa é uma dica de alta entropia, portanto, não é coletada automaticamente pelo Adobe. Consulte a [Perguntas frequentes sobre Adobe Analytics Hints](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obter detalhes sobre como coletar dicas de alta entropia.
