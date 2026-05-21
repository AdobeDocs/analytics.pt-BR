---
title: Identificação do visitante no Adobe Analytics
description: Saiba como identificar visitantes no Adobe Analytics usando as práticas recomendadas mais recentes.
exl-id: 8d26a556-84fe-4fb5-98d6-a16b69423e5b
TQID: https://experienceleague.adobe.com/uwEv9cl3234uiWhZEZLqgAVo42b-9L-9YEIGD97Pw-Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 617
ht-degree: 12%

---

# Identificação do visitante no Adobe Analytics

A identificação do visitante é essencial para o valor que o Adobe Analytics oferece para entender o comportamento do usuário online. Envolve a vinculação de ocorrências à mesma pessoa ao longo do tempo usando um identificador comum. A identificação precisa do visitante garante métricas confiáveis e oferece suporte a uma estratégia de implementação íntegra. A Adobe recomenda que as organizações priorizem serviços de identidade modernos para garantir a consistência e a integridade dos dados em todas as plataformas.

A identificação do visitante no Adobe Analytics consiste nos seguintes componentes:

* Identificador do lado do cliente: normalmente armazenado em um cookie próprio. As implementações que dependem de cookies de terceiros são menos consistentes com a identificação do visitante devido aos padrões modernos de privacidade do navegador.
* Identificador do lado do servidor: cada ID de visitante do Analytics está vinculada a um perfil nos servidores da Adobe. Esses perfis de visitante são o que permite a persistência em variáveis como [eVars](/help/components/dimensions/evar.md). Os perfis são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID de visitante.

## Ordem de identificação de operações do Adobe Analytics

Quando o Adobe recebe uma ocorrência, as seguintes verificações são feitas em ordem. Se uma determinada propriedade estiver presente, o Adobe usará esse identificador para a ocorrência. Se vários identificadores estiverem presentes em uma ocorrência, somente o primeiro método será usado. Observe que a ordem das operações não reflete a ordem que a Adobe recomenda identificar os visitantes.

| Pedido usado | Parâmetros de consulta | Apresentar quando |
|---|---|---|
| **1<sup>st</sup>** | `vid` | A variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) está definida. |
| **2<sup>nd</sup>** | `aid` | O visitante tem um cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) existente. Definido em implementações sem ou antes da implementação do serviço de ID do visitante. |
| **3<sup>rd</sup>** | `mid` | O visitante tem um cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) existente. Defina as implementações usando o [serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). A Adobe recomenda usar o serviço de ID para todas as implementações, quando possível. |
| **4<sup>th</sup>** | `fid` | O visitante tem um cookie [`s_fid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) existente. O AppMeasurement gera automaticamente uma ID de fallback se `aid` e `mid` não puderem ser definidos por algum motivo. |
| **5<sup>th</sup>** | Endereço IP + agente do usuário | Usado como último recurso para identificar um visitante único se o navegador do visitante não aceitar cookies. Uma ID de visitante com hash é gerada antes de [ofuscação de IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). Se o endereço IP não estiver disponível, outros detalhes IP (como IP de gateway) serão usados. |

Em seguida, a ID de visitante selecionada é transformada em hash e se torna o identificador do lado do servidor. Este identificador do lado do servidor está disponível como `visid_high` + `visid_low` em [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md).

## Comportamento que afeta a contagem de visitantes únicos

Identificadores de visitante único normalmente são armazenados em um cookie de navegador. Um novo visitante único é contado se um visitante executar qualquer uma das seguintes ações:

* Limpa os cookies a qualquer momento. Um visitante único é contado para uma ocorrência cada vez que o cache é limpo.
* Os cookies de ID do visitante expiram devido às configurações de privacidade do navegador. Alguns navegadores incluem métodos de prevenção de rastreamento que limitam a duração dos cookies.
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
