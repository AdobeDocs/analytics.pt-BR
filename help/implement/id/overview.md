---
title: Identificação do visitante no Adobe Analytics
description: Saiba como identificar visitantes no Adobe Analytics usando as práticas recomendadas mais recentes.
source-git-commit: 5bd1914dc52c664348f30793761f0fc347343156
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 17%

---

# Identificação do visitante no Adobe Analytics

A identificação do visitante é essencial para o valor que o Adobe Analytics oferece para entender o comportamento do usuário online. Envolve a vinculação de ocorrências à mesma pessoa ao longo do tempo usando um identificador comum. A identificação precisa do visitante garante métricas confiáveis e oferece suporte a uma estratégia de implementação íntegra. A Adobe recomenda que as organizações priorizem serviços de identidade modernos para garantir a consistência e a integridade dos dados em todas as plataformas.

A identificação do visitante no Adobe Analytics consiste nos seguintes componentes:

* Identificador do lado do cliente: normalmente armazenado em um cookie próprio. As implementações que dependem de cookies de terceiros são menos consistentes com a identificação do visitante devido aos padrões modernos de privacidade do navegador.
* Identificador do lado do servidor: cada ID de visitante do Analytics está vinculada a um perfil nos servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.

## Ordem de identificação de operações do Adobe Analytics

Quando o Adobe recebe uma ocorrência, as seguintes verificações são feitas em ordem. Se uma determinada propriedade estiver presente, o Adobe usará esse identificador para a ocorrência. Se vários identificadores estiverem presentes em uma ocorrência, somente o primeiro método será usado.

| Pedido usado | Parâmetros de consulta | Apresentar quando |
|---|---|---|
| **1<sup>st</sup>** | `vid` | A variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) está definida. |
| **2<sup>nd</sup>** | `aid` | O visitante tem um cookie [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=pt-BR) existente. Definido em implementações sem ou antes da implementação do serviço de ID do visitante. |
| **3<sup>rd</sup>** | `mid` | O visitante tem um cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=pt-BR) existente. Defina as implementações usando o [serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). A Adobe recomenda usar o serviço de ID para todas as implementações, quando possível. |
| **4<sup>th</sup>** | `fid` | O visitante tem um cookie [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=pt-BR) existente, ou se `aid` e `mid` não puderam ser definidos por algum motivo. |
| **5<sup>th</sup>** | Endereço IP, Agente do usuário, Endereço IP de gateway | Usado como último recurso para identificar um visitante único se o navegador do visitante não aceitar cookies. |

## Comportamento que afeta a contagem de visitantes únicos

Identificadores de visitante único normalmente são armazenados em um cookie de navegador. Um novo visitante único é contado se qualquer uma das seguintes situações ocorrer:

* Limpa os cookies a qualquer momento. Um visitante único é contado para uma ocorrência cada vez que o cache é limpo.
* Os cookies de ID do visitante expiram devido às configurações de privacidade do navegador. Muitos navegadores modernos incluem uma forma de prevenção de rastreamento.
* Abre um navegador diferente no mesmo computador. Um visitante único é contado por navegador.
* Abre uma sessão de navegação privada (como a guia Incógnito do Chrome). Um visitante único é contado por sessão de navegação depois que todas as guias são fechadas.
* Visita seu site em diferentes dispositivos. Um visitante único é contado por dispositivo.
* Visita seu site após mais de 13 meses de inatividade.

Considere usar a [compilação](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/stitching/overview) no Customer Journey Analytics para identificar a mesma pessoa usando vários navegadores ou vários dispositivos.

## Comportamento que não afeta a contagem de visitantes únicos

Um novo visitante único *não* é contado, desde que o identificador do visitante seja preservado:

* Fecha o navegador (por menos de 13 meses)
* Atualiza o navegador para a versão mais recente
* Reinicia o computador
