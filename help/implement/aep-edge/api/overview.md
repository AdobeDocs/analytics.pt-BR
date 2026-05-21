---
title: Implementar o Adobe Analytics usando a API Edge Network do Adobe Experience Platform
description: Use a API Edge Network do Adobe Experience Platform para enviar dados ao Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 42%

---

# Implementar o Adobe Analytics usando a API Edge Network do Adobe Experience Platform

Normalmente, você usa a API do Edge Network do Experience Platform para coletar dados do lado do servidor, em vez de do lado do cliente, e ao coletar dados de dispositivos como dispositivos IoT, decodificadores de sinais e aplicativos de desktop. Em seguida, você envia esses dados para a rede da Edge e para serviços como o Adobe Analytics.

Considere também a API do Edge Network quando precisar que dados confidenciais sejam coletados com segurança e autenticados na rede. Consulte [Autenticação](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html) para obter mais informações.

Uma visão geral de alto nível das tarefas de implementação:

![Adobe Analytics usando o fluxo de trabalho de extensão do Analytics](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarefa</b></th><th style="width:35%"><b>Mais informações</b></th>
</tr>

<tr>
<td>1</td>
<td>Certifique-se de que você <b>definiu um conjunto de relatórios</b>.</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">Gerenciador do conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurar esquemas</b>. Para padronizar a coleta de dados para uso em aplicativos que utilizam a Adobe Experience Platform, a Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR">Visão geral da interface de esquemas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configurar uma sequência de dados</b>. Uma sequência de dados representa a configuração do lado do servidor ao usar as APIs da API do Adobe Experience Platform Edge Network.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-br">Configurar uma sequência de dados<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implemente e teste a coleta de dados</b> usando as APIs de coleta de dados de evento único e de dados de evento em lote.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=pt-BR">Coleta de dados de evento único</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">Coleta de dados de evento em lote</a>
</tr>

<td>5</td>
<td><b>Adicionar um serviço Adobe Analytics</b> à sua sequência de dados. Esse serviço controla se e como os dados são enviados para o Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=pt-BR">Interação com o Adobe Analytics</a></td>
</tr>


</table>

Consulte a [documentação da API do Edge Network](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=pt-BR) para obter mais informações.

