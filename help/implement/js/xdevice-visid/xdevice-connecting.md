---
description: A identificação de visitantes em vários dispositivos ajuda você a conectar visitantes em vários dispositivos. A identificação de visitantes entre dispositivos usa a variável de ID de visitante, s.visitorID, para associar um usuário em dispositivos.
keywords: Analytics Implementation
subtopic: Visitors
title: Usuários do Connect em vários dispositivos
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# Usuários do Connect em vários dispositivos

> [!IMPORTANT] Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte Análise [](/help/components/cda/cda-home.md) entre dispositivos no guia do usuário Componentes.

A identificação de visitantes em vários dispositivos ajuda você a conectar visitantes em vários dispositivos. Cross-device visitor identification uses the `visitorID` variable to associate a user across devices. A `visitorID` variável tem a prioridade mais alta ao identificar visitantes únicos.

Quando você envia uma ocorrência com uma ID de visitante personalizada, a Adobe verifica se há perfis de visitante com uma ID de visitante correspondente. Se existir, o perfil de visitante já existente no sistema será usado a partir desse ponto e o perfil de visitante anterior não será mais usado.

Setting the `visitorID` variable is typically set after authentication, or after a visitor performs some other action that allows you to uniquely identify them independently of the device that is used. Os identificadores efetivos incluem um hash de seu nome de usuário, endereço de email ou uma ID interna que não contém nenhuma informação pessoalmente identificável.

Depois que o cliente entra em cada dispositivo, todos estão vinculados ao mesmo perfil de usuário. Se o visitante sair posteriormente em um dispositivo, ele continuará a pertencer ao mesmo perfil de visitante, pois a Adobe reconhece que o cookie do navegador em cada dispositivo pertence ao mesmo perfil de visitante. A Adobe recomenda usar a `visitorID` variável sempre que possível, caso o cookie do navegador seja excluído.

## Limitações

Usar suas próprias IDs de visitante personalizadas oferece mais controle sobre como os visitantes são identificados, mas isso vem com suas limitações.

* **A desduplicação do visitante não é retroativa**: Se um visitante acessar seu site pela primeira vez, em seguida, se autenticar, dois visitantes únicos serão contados. Um visitante único conta para a ID genérica do Analytics gerada automaticamente e outro conta para a ID de visitante personalizada ao fazer logon. Essa duplicação de visitantes únicos está presente sempre que um visitante usa um novo dispositivo ou apaga seus cookies.
* **Incompatibilidade com o serviço** da Experience Cloud ID: Desde a introdução da identificação de visitantes entre dispositivos, a Adobe lançou maneiras mais poderosas e confiáveis de rastrear visitantes em todos os dispositivos. Esses novos métodos de identificação não são compatíveis com a substituição da ID de visitante personalizada. Se você planeja usar o serviço de ID, o CDA (Cross-device Analytics) ou a cooperativa de dispositivos, a Adobe recomenda não usar a `visitorID` variável.
