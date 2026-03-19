---
title: Excluir por endereço IP
description: Impeça que os dados gerados por determinados endereços IP apareçam nos relatórios.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 4b4febd839682d88164b2f505245441d18ef2543
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 17%

---

# Excluir por endereço IP

É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a precisão do relatório ao excluir dados de endereço IP. Além disso, você pode remover dados de negação de serviço ou outros eventos mal-intencionados que podem distorcer os dados do relatório.

Para excluir dados por endereço IP, você pode configurar exclusões conforme descrito abaixo ou [configurar seu firewall](/help/technotes/ip-addresses.md).

## Configurar exclusões por endereço IP

>[!NOTE]
>
>Ao configurar exclusões por endereço IP, considere o seguinte:
>
>* As ocorrências excluídas pelo endereço IP são cobradas como [chamadas do servidor](/help/technotes/terms.md).
>* Endereços IP privados não precisam ser excluídos. Somente endereços IP externos chegam aos servidores de coleta de dados da Adobe. Os endereços privados incluem `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` e `169.254.*.*`.
>* Você pode usar indicadores curingas (&#42;) para excluir um intervalo de endereços. Por exemplo, `[!DNL 0.0.*.0]` excluiria todos os endereços IP entre `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. É possível excluir até 50 endereços IP diferentes.
>* Os dados de um endereço IP excluído são excluídos para quaisquer novas ocorrências que cheguem ao sistema dentro de 5 minutos após a definição da exclusão.
>* Os dados de ocorrências capturadas antes do momento em que as alterações foram feitas no endereço IP não são afetados. A exclusão de IP se aplica somente aos dados que avançam.
>* As ocorrências excluídas ainda estão visíveis nos [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md) (sinalizados como `exclude_hit = 4`).

Para configurar exclusões por endereço IP:

1. No Adobe Analytics, selecione **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]**.

1. Na página Admin, selecione **[!UICONTROL Excluir por IP]**.

## Impacto do uso de ofuscação de IP com exclusão de IP

O impacto do uso de [ofuscação de IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) junto com exclusão de IP depende da configuração de ofuscação de IP de cada conjunto de relatórios:

* **Ofuscação de IP (último octeto)**: IP parcialmente ofuscado ANTES da execução da exclusão de IP. Verifique se as regras de exclusão de IP sempre esperam um `0` como o último octeto (os curingas são válidos, pois incluem `0`).
* **Ofuscação de IP (remover IP)**: o IP é totalmente ofuscado APÓS a execução da exclusão de IP. Nenhuma acomodação de regra de exclusão de IP é necessária.
