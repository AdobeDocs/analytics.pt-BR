---
title: Excluir por endereço IP
description: Impedir que os dados gerados por determinados endereços IP apareçam nos relatórios.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 85%

---


# Excluir por endereço IP

É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a exatidão do relatório, pois exclui os dados do endereço IP. Além disso, você pode remover dados de negação de serviço, além de outros eventos mal-intencionados que podem causar um viés nos dados do relatório. Você pode configurar a exclusão ou usar seu firewall para isso.

**[!UICONTROL Analytics]** > **[!UICONTROL Administração]** > **[!UICONTROL Excluir por IP]**

>[!NOTE]
>
>As ocorrências excluídas pelo endereço IP são cobradas como [chamadas do servidor](https://docs.adobe.com/content/help/pt-BR/analytics/technotes/terms.html).

Você pode usar indicadores curinga (*) para excluir um intervalo de endereços. Por exemplo, `[!DNL 0.0.*.0]` excluiria todos os endereços IP entre `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. É possível excluir até 50 endereços IP diferentes.

>[!TIP]
>
>Os endereços IP privados não precisam ser excluídos. Somente endereços IP externos chegam aos servidores de coleta de dados de Adobe. Os endereços privados incluem `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*`e `169.254.*.*`.

## Impacto da ofuscação de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso ocorrerá antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. A correspondência de * deve corresponder a 0.
