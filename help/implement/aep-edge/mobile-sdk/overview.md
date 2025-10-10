---
title: Implementar o Adobe Analytics usando o SDK móvel da Adobe Experience Platform
description: Use a extensão SDK móvel na coleção de dados da Adobe Experience Platform para enviar dados ao Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 99%

---

# Implementar o Adobe Analytics usando o SDK móvel da Adobe Experience Platform

O SDK móvel da Adobe Experience Platform ajuda a potencializar as soluções e os serviços da Experience Cloud em seus aplicativos móveis. Ele está disponível para Android™, iOS e várias estruturas de desenvolvimento entre plataformas. A configuração é feita por meio da Coleção de dados da Adobe Experience Platform.

>[!IMPORTANT]
>
>Uma extensão do Adobe Analytics também está disponível na Coleção de dados da Adobe Experience Platform. Se você instalar essa extensão, não será possível usar o XDM ou a Rede de borda.

## SDK da Adobe Experience Platform

Uma visão geral de alto nível das tarefas de implementação:

![Adobe Analytics usando o fluxo de trabalho de extensão do Analytics](../../assets/mobilesdk-annotated.png)

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
<td><b>Configurar uma sequência de dados</b>. Uma sequência de dados representa a configuração do lado do servidor ao implementar o SDK da Web da Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR">Configurar uma sequência de dados<a></td> 
</tr>

<td>3</td>
<td><b>Adicionar um serviço do Adobe Analytics</b> à sua sequência de dados. Esse serviço controla se e como os dados são enviados para o Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Adicionar o serviço Adobe Analytics a uma sequência de dados</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Criar uma propriedade móvel</b>. Uma propriedade é um container que você preenche com extensões, regras, elementos de dados e bibliotecas.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">Configurar uma propriedade móvel</a></tr>

<tr>
<td>5</td>
<td><b>Instale a extensão Rede de borda da Adobe Experience Platform</b> na propriedade da tag móvel e configure a sequência de dados na extensão.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Rede de borda da Adobe Experience Platform</a>
</tr>

<tr>
<td>6</td>
<td><b>Usar código no aplicativo</b> para registrar as extensões necessárias e carregar a configuração da tag.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Defina a configuração</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Implementar e testar a funcionalidade</b> usando a combinação de elementos de dados da tag, regras, extensões adicionais e chamadas da API do SDK no seu aplicativo. Inspecione, valide e depure a coleta de dados e experiências para seu aplicativo para dispositivos móveis.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Usar o aplicativo de exemplo</a>
</tr>

<tr>
<td>8</td>
<td><b>Estender e validar a implementação do aplicativo para dispositivos móveis</b> antes de colocá-lo em produção.</td>
<td></td> 
</tr>

</table>


## Extensão do Adobe Analytics.

Uma visão geral de alto nível das tarefas de implementação:

![Adobe Analytics usando o fluxo de trabalho de extensão do Analytics](../../assets/mobilesdk-analytics-annotated.png)

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
<td><b>Instale a extensão do Adobe Analytics</b> na propriedade da tag móvel e configure a extensão para apontar para o conjunto de relatórios.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Extensão do Adobe Analytics para propriedade móvel</a>
</tr>

<tr>
<td>3</td>
<td><b>Usar código no aplicativo</b> para registrar as extensões necessárias e carregar a configuração da tag.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Defina a configuração</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Implementar e testar a funcionalidade</b> usando a combinação de elementos de dados da tag, regras, extensões adicionais e chamadas da API do SDK no seu aplicativo. Inspecione, valide e depure a coleta de dados e experiências para seu aplicativo para dispositivos móveis.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Usar o aplicativo de exemplo</a>
</tr>

<tr>
<td>5</td>
<td><b>Estenda e valide a implementação do aplicativo móvel</b> antes de empurrá-lo para a produção.</td>
<td></td> 
</tr>

</table>

## Recursos adicionais

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#)

- [Documentação do SDK móvel](https://developer.adobe.com/client-sdks/documentation/)
