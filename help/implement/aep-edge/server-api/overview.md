---
title: Implementar o Adobe Analytics usando a API do Adobe Experience Platform Edge Network Server
description: Use a API do servidor do Adobe Experience Platform Edge Network para enviar dados para a Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 2e5171842794d7acc7bb67048b734f47a438cf1c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 33%

---

# Implementar o Adobe Analytics usando a API do Adobe Experience Platform Edge Network Server

Normalmente, você usa a API do servidor do Edge Network Experience Platform para coletar dados do lado do servidor, em vez de do lado do cliente, e ao coletar dados de dispositivos como dispositivos IoT, decodificadores de sinais e aplicativos de desktop. Em seguida, você envia esses dados para a rede da Edge e para serviços como o Adobe Analytics.

Considere também a API do servidor de Edge Network quando precisar que dados confidenciais sejam coletados com segurança e autenticados na rede. Consulte [Autenticação](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html?lang=pt-BR) para obter mais informações.

Uma visão geral de alto nível das tarefas de implementação:

![Adobe Analytics usando o fluxo de trabalho de extensão do Analytics](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarefa</b></th><th style="width:35%"><b>Mais informações</b></th>
</tr>

<tr>
<td>1</td>
<td>Certifique-se de que você <b>definiu um conjunto de relatórios</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gerenciador do conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurar esquemas</b>. Para padronizar a coleta de dados para uso em aplicativos que utilizam a Adobe Experience Platform, a Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR">Visão geral da interface de esquemas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configurar uma sequência de dados</b>. Uma sequência de dados representa a configuração do lado do servidor ao usar as APIs da API Edge Network do Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-br">Configurar uma sequência de dados<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implemente e teste a coleta de dados</b> usando as APIs de coleta de dados de evento único e de dados de evento em lote.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=pt-BR">Coleta de dados de evento único</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=pt-BR">Coleta de dados de evento em lote</a>
</tr>

<td>5</td>
<td><b>Adicionar um serviço Adobe Analytics</b> à sua sequência de dados. Esse serviço controla se e como os dados são enviados para o Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=pt-BR">Interação com o Adobe Analytics</a></td>
</tr>


</table>

Consulte a [documentação da API do Edge Network Server](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=pt-BR) e um exemplo de [integração com o Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=pt-BR) para obter mais informações.

