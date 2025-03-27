---
title: Excluir por endereço IP
description: Impeça que os dados gerados por determinados endereços IP apareçam nos relatórios.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: d642bf8703d7c4c1545bfd9763c70ed8b1237eac
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 51%

---

# Excluir por endereço IP

É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a exatidão do relatório, pois exclui os dados do endereço IP. Além disso, você pode remover dados de negação de serviço, entre outros eventos mal-intencionados, que podem causar um viés nos dados do relatório.

Para excluir dados por endereço IP, você pode configurar exclusões conforme descrito abaixo ou [configurar seu firewall](/help/technotes/ip-addresses.md).

## Configurar exclusões por endereço IP

>[!NOTE]
>
>Ao configurar exclusões por endereço IP, considere o seguinte:
>
>* As ocorrências excluídas pelo endereço IP são cobradas como [chamadas do servidor](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=pt-BR).
>* Endereços IP privados não precisam ser excluídos. Somente endereços IP externos chegam aos servidores de coleta de dados da Adobe. Os endereços privados incluem `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` e `169.254.*.*`.
>* Você pode usar indicadores curingas (&#42;) para excluir um intervalo de endereços. Por exemplo, `[!DNL 0.0.*.0]` excluiria todos os endereços IP entre `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. É possível excluir até 50 endereços IP diferentes.
* Os dados de um endereço IP excluído são excluídos para quaisquer novas ocorrências que cheguem ao sistema dentro de 5 minutos após a definição da exclusão.
* Os dados de ocorrências capturadas antes do momento em que as alterações foram feitas no endereço IP não são afetados.
>

Para configurar exclusões por endereço IP:

1. No Adobe Analytics, selecione **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]**.

1. Na página Admin, selecione **[!UICONTROL Excluir por IP]**.




## Impacto da ofuscação de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso ocorrerá antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. O &#42; correspondente deve corresponder a 0.
