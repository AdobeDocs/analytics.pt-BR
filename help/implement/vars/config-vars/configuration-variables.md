---
title: Variáveis de configuração
description: Use variáveis de configuração para ajudar a determinar como os dados são coletados.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 19%

---

# Visão geral das variáveis de configuração

As variáveis de configuração controlam como os dados são capturados e processados nos relatórios. Normalmente, elas não contêm valores de dimensão ou métrica.

## Definir variáveis de configuração

Em implementações que usam a extensão do Web SDK ou a extensão do Analytics, as variáveis de configuração normalmente são encontradas nas configurações da extensão:

1. Faça logon em [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Clique na guia [!UICONTROL Extensões] e em [!UICONTROL Configurar] na extensão.

Em implementações JavaScript que usam `AppMeasurement.js`, as variáveis de configuração normalmente são definidas no lugar do arquivo JS.

>[!IMPORTANT]
>
>Verifique se todas as variáveis de configuração estão definidas antes de chamar um método de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Evite definir variáveis de configuração na função [`doPlugins()`](../functions/doplugins.md).

## Variáveis de configuração desativadas

As variáveis de configuração a seguir foram removidas. Eles estão documentados aqui para referência se você os encontrar em uma implementação herdada.

* **`account`**: Determinado o conjunto de relatórios para o qual os dados foram enviados. O conjunto de relatórios agora é manipulado por meio da instanciação do objeto de rastreamento (o método [`s_gi()`](../functions/s-gi.md)). Use o método [`s.sa()`](../functions/sa-method.md) se precisar alterar o conjunto de relatórios depois que o objeto de rastreamento for instanciado.
* **`cookieDomain`**: determinado o domínio no qual o AppMeasurement definiu cookies. As versões atuais do AppMeasurement detectam automaticamente o domínio de cookie correto, tornando essa variável obsoleta.
* **`cookieDomainPeriods`**: ajudou a AppMeasurement a determinar onde armazenar cookies quando um domínio continha vários períodos. As versões atuais do AppMeasurement detectam automaticamente o domínio correto, tornando essa variável obsoleta.
* **`fpCookieDomainPeriods`**: o equivalente próprio de `cookieDomainPeriods`, usado para definir cookies no local correto quando o sufixo de um domínio próprio continha um ponto extra (como `example.co.uk`). As versões atuais do AppMeasurement detectam automaticamente o domínio correto, tornando essa variável obsoleta.
* **`trackingServer`**: O domínio usado para enviar dados para o Adobe por HTTP foi especificado. Está obsoleto em favor da coleção de dados segura em HTTPS. Use [`trackingServerSecure`](trackingserversecure.md) no lugar dela.
* **`trackInlineStats`**: versões anteriores do [Activity Map](/help/analyze/activity-map/overview.md) habilitadas ou desabilitadas.
* **`visitorMigrationKey`**: uma chave usada para migrar visitantes de cookies de terceiros para cookies próprios foi carregada. Ele foi removido porque as bibliotecas modernas definem um cookie de fallback primário (`fid`) e dependem do Serviço de ID de visitante para identificar.
* **`visitorMigrationServer`**: Especificado o servidor usado durante a migração de cookies de terceiros para cookies próprios.
* **`visitorMigrationServerSecure`**: O equivalente HTTPS de `visitorMigrationServer`.
* **`visitorNameSpace`**: ajudou a determinar o domínio do cookie de terceiros. Foi removido em favor do uso da variável [`trackingServerSecure`](trackingserversecure.md) para implementações que não usam o Serviço de ID de visitante.
