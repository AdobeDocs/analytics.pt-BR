---
description: A identificação de visitantes em vários dispositivos ajuda você a conectar visitantes em vários dispositivos. A identificação de visitantes entre dispositivos usa a variável de ID de visitante, s.visitorID, para associar um usuário em dispositivos.
keywords: Analytics Implementation
subtopic: Visitors
title: Usuários do Connect em vários dispositivos
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Usuários do Connect em vários dispositivos

>[!IMPORTANT] Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte [Análise entre dispositivos](/help/components/cda/cda-home.md) no guia do usuário Componentes.

A identificação de visitantes em vários dispositivos ajuda você a conectar visitantes em vários dispositivos. A identificação de visitantes entre dispositivos usa a variável `visitorID` para associar um usuário em dispositivos. A variável `visitorID` tem a prioridade mais alta ao identificar visitantes únicos.

Ao enviar uma ocorrência com uma ID de visitante personalizada, a Adobe verifica se há perfis de visitante com uma ID de visitante correspondente. Se existir, o perfil do visitante já no sistema é usado a partir desse ponto e o perfil do visitante anterior não é mais usado.

Normalmente, a variável `visitorID` é definida após a autenticação ou depois que um visitante executa alguma ação que permite a identificação exclusiva, independente do dispositivo usado. Os identificadores efetivos incluem um hash do nome de usuário, endereço de email ou uma ID interna que não contém informações pessoalmente identificáveis.

Depois que o cliente se conecta a cada dispositivo, todos são vinculados ao mesmo perfil de usuário. Se o visitante se desconectar de um dispositivo, ele continuará a pertencer ao mesmo perfil de visitante, pois a Adobe reconhece que o cookie do navegador em cada dispositivo pertence ao mesmo perfil de visitante. A Adobe recomenda usar a variável `visitorID` sempre que possível, caso o cookie do navegador seja excluído.

## Limitações

Usar suas próprias IDs de visitante personalizadas oferece mais controle sobre como os visitantes são identificados, mas há limitações.

* **A desduplicação do visitante não é retroativa**: se um visitante acessar o site pela primeira vez e, em seguida, se autenticar, dois visitantes únicos serão contados. Um visitante único é contado para a ID genérica do Analytics gerada automaticamente e outro para a ID de visitante personalizada ao fazer logon. Essa duplicação de visitantes únicos ocorre sempre que um visitante usa um novo dispositivo ou apaga os cookies.
* **Incompatibilidade com o serviço da Experience Cloud ID**: desde a introdução da identificação de visitantes entre dispositivos, a Adobe lançou maneiras mais avançadas e confiáveis de rastrear visitantes em todos os dispositivos. Esses novos métodos de identificação não são compatíveis com a substituição da ID de visitante personalizada. Se você planeja usar o serviço de ID, a Análise entre dispositivos (CDA) ou o Device co-op, a Adobe recomenda não usar a variável `visitorID`.
