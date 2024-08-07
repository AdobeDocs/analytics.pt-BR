---
title: Excluir por endereço IP
description: Impeça que os dados gerados por determinados endereços IP apareçam nos relatórios.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 76%

---

# Excluir por endereço IP

É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a exatidão do relatório, pois exclui os dados do endereço IP. Além disso, você pode remover dados de negação de serviço, além de outros eventos mal-intencionados que podem causar um viés nos dados do relatório. Você pode configurar a exclusão ou usar seu firewall para isso.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Excluir por IP]**

>[!NOTE]
>
>As ocorrências excluídas pelo endereço IP são cobradas como [chamadas do servidor](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=pt-BR).

Você pode usar indicadores curingas (&#42;) para excluir um intervalo de endereços. Por exemplo, `[!DNL 0.0.*.0]` excluiria todos os endereços IP entre `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. É possível excluir até 50 endereços IP diferentes.

>[!TIP]
>
>Endereços IP privados não precisam ser excluídos. Somente endereços IP externos atingem os servidores de coleta de dados do Adobe. Os endereços privados incluem `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` e `169.254.*.*`.

## Impacto da ofuscação de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso ocorrerá antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. O &#42; correspondente deve corresponder a 0.
