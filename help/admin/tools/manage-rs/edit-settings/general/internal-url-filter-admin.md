---
description: Os filtros de URL internos identificam os referenciadores que você considera internos no site. Eles ajudam os relatórios de fontes de tráfego a preencher dados e ajudam a filtrar o tráfego interno.
title: Filtros internos do URL
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
TQID: https://experienceleague.adobe.com/J78ImTXRPFm6aMHqrxJXZOUVyG-ETnutipYYo2wrofc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 2%

---

# Filtros internos de URL

Filtros de URL internos permitem identificar os referenciadores que você considera internos no site. Eles ajudam os relatórios de fontes de tráfego a preencher dados e ajudam a filtrar o tráfego interno.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Filtros Internos de URL]**

Normalmente, um referenciador, ou página de referência, é a página da qual um visitante entrou em seu site. Para evitar o desvio de dados, você pode filtrar referenciadores internos. As dimensões que dependem de filtros internos de URL incluem [Referenciador](/help/components/dimensions/referrer.md), [Domínio de referência](/help/components/dimensions/referring-domain.md), [Canais de marketing](/help/components/dimensions/marketing-channel.md) e outras dimensões de fonte de tráfego.

As [Regras de processamento de canal de marketing](../marketing-channels/mc-proc-rules.md) fornecem &quot;[!UICONTROL Corresponde aos filtros internos de URL]&quot; como critérios de regra possíveis.

>[!IMPORTANT]
>
>Alguns conjuntos de relatórios têm um filtro de URL interno de um ponto (`.`) configurado por padrão. Quando esse filtro existe, todo o tráfego é classificado como interno. Os relatórios do referenciador não funcionam até que esse filtro seja removido e substituído por um ou mais domínios internos desejados.

* Exibir todos os filtros existentes na seção **[!UICONTROL Filtros atuais]**.
* Adicione um filtro usando a caixa de texto na seção **[!UICONTROL Adicionar filtro]** e clique em **[!UICONTROL Adicionar]**.

Os filtros operam usando a lógica **contains** em relação à URL completa. A Adobe recomenda omitir o protocolo (`https://`) e os subdomínios ao criar filtros, a menos que o tráfego de subdomínios separados seja desejado como tráfego externo.
