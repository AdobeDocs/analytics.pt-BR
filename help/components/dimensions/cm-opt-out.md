---
title: Recusa no gerenciamento de consentimento
description: Veja quais configurações de privacidade um visitante recusou.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
TQID: https://experienceleague.adobe.com/tsMhHR84qhEUZIZjPTluCJOHMPc37-JRwLsipAycgJI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 83%
---
# Recusa no gerenciamento de consentimento

A [dimensão](overview.md) de &#39;Recusa no gerenciamento de consentimento&#39; exibe quais configurações de privacidade um visitante recusou explicitamente. Você pode usar essa dimensão para filtrar dados com base nas configurações de privacidade ou ver os motivos mais comuns de recusa de privacidade.

## Preencher esta dimensão com dados

Essa dimensão coleta dados das seguintes [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` quando definido como `1`. Se `cm.ssf` igual a `0` ou está em branco, essa variável não faz nada.
* `contextData.['opt.dmp']` quando definido como `N`. Se `opt.dmp` igual a `Y`, a dimensão [Aceitação do gerenciamento de consentimento](cm-opt-in.md) é preenchida.
* `contextData.['opt.sell']` quando definido como `N`. Se `opt.sell` igual a `Y`, a dimensão [Aceitação do gerenciamento de consentimento](cm-opt-in.md) é preenchida.

Sua organização determina a lógica para implementar essas variáveis de dados de contexto. Defina cada variável de dados de contexto em cada página.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (definido por meio de sinais de consentimento) |
| **Web SDK / campo XDM** | Nenhum |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | 100 bytes |
| **Persistência** | Hit |

## Itens de dimensão

Os itens de dimensão incluem os três valores a seguir:

* **`SSF`**: o visitante recusou o [Encaminhamento pelo lado do servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md). Esse item de dimensão está presente quando a variável de dados de contexto `cm.ssf` é igual a `1`. Consulte [Visão geral da privacidade de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=pt-BR) no guia do usuário do Audience Manager para obter mais informações. O hit não é encaminhado ao Adobe Audience Manager.
* **`DMP`**: ol visitante recusou o compartilhamento nas plataformas de gerenciamento de dados. Esse item de dimensão está presente quando a variável de dados de contexto `opt.dmp` é igual a `N`. Semelhante a `SSF`, o hit não é encaminhado ao Adobe Audience Manager.
* **`SELL`**: o visitante recusou o compartilhamento ou a venda dos dados a terceiros. Essa dimensão está presente quando a variável de dados de contexto `opt.sell` é igual a `N`.
