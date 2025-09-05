---
description: Os Filtros internos do URL identificam referenciadores que você considera internos ao site. Eles ajudam os relatórios de fontes de tráfego a popular os dados, além de ajudarem a filtrar o tráfego interno.
title: Filtros internos do URL
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 31%

---


# Filtros internos de URL

Filtros de URL internos permitem identificar os referenciadores que você considera internos no site. Eles ajudam os relatórios de fontes de tráfego a popular os dados, além de ajudarem a filtrar o tráfego interno.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Filtros Internos de URL]**

Um referenciador ou uma página referenciadora é, normalmente, a página a partir da qual o visitante veio ao entrar do site. Para evitar o viés dos dados, você pode filtrar e eliminar os referenciadores internos. As dimensões que dependem de filtros internos de URL incluem [Referenciador](/help/components/dimensions/referrer.md), [Domínio de referência](/help/components/dimensions/referring-domain.md), [Canais de marketing](/help/components/dimensions/marketing-channel.md) e outras dimensões de fonte de tráfego.

As [Regras de processamento de canal de marketing](../marketing-channels/c-rules.md) fornecem &quot;[!UICONTROL Corresponde aos filtros internos de URL]&quot; como critérios de regra possíveis.

>[!IMPORTANT]
>
>Alguns conjuntos de relatórios têm um filtro de URL interno de um ponto (`.`) configurado por padrão. Quando esse filtro existe, todo o tráfego é classificado como interno. Os relatórios do referenciador não funcionam até que esse filtro seja removido e substituído por um ou mais domínios internos desejados.

* Exibir todos os filtros existentes na seção **[!UICONTROL Filtros atuais]**.
* Adicione um filtro usando a caixa de texto na seção **[!UICONTROL Adicionar filtro]** e clique em **[!UICONTROL Adicionar]**.

Os filtros operam usando a lógica **contains** em relação à URL completa. A Adobe recomenda omitir o protocolo (`https://`) e os subdomínios ao criar filtros, a menos que o tráfego de subdomínios separados seja desejado como tráfego externo.
