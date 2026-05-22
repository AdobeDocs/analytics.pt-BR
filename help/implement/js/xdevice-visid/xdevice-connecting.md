---
description: A identificação de visitantes em vários dispositivos ajuda você a conectar visitantes em vários dispositivos.
keywords: Implementação do Analytics
subtopic: Visitors
title: Usuários do Connect em vários dispositivos
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
role: Developer
TQID: 'https://experienceleague.adobe.com/t4NC8Wdgldm6iFgdJ5EtrU13kOnUBuEGKhWnKExf614'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 94%

---

# Usuários do Connect em vários dispositivos

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte [Cross-Device Analytics](/help/components/cda/overview.md) no guia do usuário de Componentes.

A identificação de visitantes em vários dispositivos ajuda você a conectar visitantes em vários dispositivos. A identificação de visitantes entre dispositivos usa a variável `visitorID` para associar um usuário em dispositivos. A variável `visitorID` tem a prioridade mais alta ao identificar visitantes únicos.

Ao enviar uma ocorrência com uma ID de visitante personalizada, a Adobe verifica se há perfis de visitante com uma ID de visitante correspondente. Se existir, o perfil do visitante já no sistema é usado a partir desse ponto e o perfil do visitante anterior não é mais usado.

Normalmente, a variável `visitorID` é definida após a autenticação ou depois que um visitante executa alguma ação que permite a identificação exclusiva, independente do dispositivo usado. Os identificadores efetivos incluem um hash do nome de usuário, endereço de email ou uma ID interna que não contém informações pessoalmente identificáveis.

Depois que o cliente se conecta a cada dispositivo, todos são vinculados ao mesmo perfil de usuário. Se o visitante se desconectar de um dispositivo, ele continuará a pertencer ao mesmo perfil de visitante, pois a Adobe reconhece que o cookie do navegador em cada dispositivo pertence ao mesmo perfil de visitante. A Adobe recomenda usar a variável `visitorID` sempre que possível, caso o cookie do navegador seja excluído.

## Limitações

Usar suas próprias IDs de visitante personalizadas oferece mais controle sobre como os visitantes são identificados, mas há limitações.

* **A desduplicação do visitante não é retroativa**: se um visitante acessar o site pela primeira vez e, em seguida, se autenticar, dois visitantes únicos serão contados. Um visitante único é contado para a ID genérica do Analytics gerada automaticamente e outro para a ID de visitante personalizada ao fazer logon. Essa duplicação de visitantes únicos ocorre sempre que um visitante usa um novo dispositivo ou apaga os cookies.
* **Incompatibilidade com o serviço da Experience Cloud ID**: desde a introdução da identificação de visitantes entre dispositivos, a Adobe lançou maneiras mais avançadas e confiáveis de rastrear visitantes em todos os dispositivos. Esses novos métodos de identificação não são compatíveis com a substituição da ID de visitante personalizada. Se você planeja usar o ID Service ou Cross-Device Analytics (CDA), a Adobe recomenda não usar a variável `visitorID`.
