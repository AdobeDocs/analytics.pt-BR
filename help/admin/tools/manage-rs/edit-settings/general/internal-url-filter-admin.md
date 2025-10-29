---
description: Os filtros de URL internos identificam os referenciadores que você considera internos no site. Eles ajudam os relatórios de fontes de tráfego a preencher dados e ajudam a filtrar o tráfego interno.
title: Filtros internos do URL
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '221'
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
