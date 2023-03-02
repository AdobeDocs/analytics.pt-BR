---
title: Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform
description: Use a extensão SDK da Web na coleção de dados da Adobe Experience Platform para enviar dados ao Adobe Analytics.
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: ht
source-wordcount: '799'
ht-degree: 100%

---

# Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform

Você pode usar o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=pt-BR) para enviar dados ao Adobe Analytics. Este método de implementação funciona traduzindo o [Modelo de dados de experiência (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) em um formato usado pelo Analytics.

Você pode enviar dados para o Experience Edge diretamente usando o SDK da Web ou por meio da extensão do SDK da Web em Tags.

## SDK da Web

Uma visão geral de alto nível das tarefas de implementação:

![Implementar o Adobe Analytics usando o fluxo de trabalho do SDK da Web](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarefa</b></th><th style="width:35%"><b>Mais Informações</b></th>
</tr>

<tr>
<td>1</td>
<td>Certifique-se de ter <b>definido um conjunto de relatórios</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gerenciador do Conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurar esquemas e conjuntos de dados</b>. Para padronizar a coleta de dados para uso em aplicativos que utilizam a Adobe Experience Platform, a Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR">Visão geral da interface de esquemas</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=pt-BR">Visão geral da interface de conjuntos de dados</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Criar uma camada de dados</b> para gerenciar o rastreamento dos dados no seu site.</td>
<td><a href="../../prepare/data-layer.md">Criar uma camada de dados</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Instalar a versão independente pré-criada</b>. Você pode fazer referência à biblioteca (<code>alloy.js</code>) na CDN diretamente na sua página ou baixá-la e hospedá-la na sua própria infraestrutura. Como alternativa, você pode usar o pacote NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR#option-2%3A-installing-the-prebuilt-standalone-version">Instalar a versão independente pré-criada</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR#option-3%3A-using-the-npm-package">Usar o pacote NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurar uma sequência de dados</b>. Uma sequência de dados representa a configuração do lado do servidor ao implementar o SDK da Web da Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR">Configurar uma sequência de dados<a></td> 
</tr>

<td>6</td>
<td><b>Adicionar um serviço do Adobe Analytics</b> à sua sequência de dados. Esse serviço controla se e como os dados são enviados para o Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR#analytics">Adicionar o serviço Adobe Analytics a uma sequência de dados</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurar o SDK da Web</b>. Certifique-se de que a biblioteca instalada na etapa 4 esteja configurada corretamente com a ID da sequência de dados (anteriormente conhecida como ID de configuração de borda (<code>edgeConfigId</code>)), ID da organização (<code>orgId</code>) e outras opções disponíveis.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR">Configurar o SDK da Web</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Executar comandos</b> e/ou <b>rastrear eventos</b>. Depois que o código base tiver sido implementado em sua página da Web, você poderá começar a executar comandos e rastrear eventos com o SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=pt-BR">Executar comandos</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=pt-BR">Rastrear eventos</a></td>
</tr>

<tr>
<td>9</td><td><b>Estender e validar sua implementação</b> antes de empurrá-lo para a produção.</td><td></td> 
</tr>
</table>


## Extensão do SDK da Web

Uma visão geral de alto nível das tarefas de implementação:

![Implementar o Adobe Analytics usando o fluxo de trabalho da extensão do SDK da Web](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarefa</b></th><th style="width:35%"><b>Mais informações</b></th>
</tr>

<tr>
<td>1</td>
<td>Certifique-se de ter <b>definido um conjunto de relatórios</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gerenciador do Conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurar esquemas e conjuntos de dados</b>. Para padronizar a coleta de dados para uso em aplicativos que utilizam a Adobe Experience Platform, a Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR">Visão geral da interface de esquemas</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=pt-BR">Visão geral da interface de conjuntos de dados</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Criar uma camada de dados</b> para gerenciar o rastreamento dos dados no seu site.</td>
<td><a href="../../prepare/data-layer.md">Criar uma camada de dados</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configurar uma sequência de dados</b>. Uma sequência de dados representa a configuração do lado do servidor ao implementar o SDK da Web da Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR">Configurar uma sequência de dados<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Adicionar um serviço Adobe Analytics</b> à sua sequência de dados. Esse serviço controla se e como os dados são enviados para o Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR#analytics">Adicionar o serviço Adobe Analytics a uma sequência de dados</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Criar uma propriedade de tag</b>. Propriedades são contêineres abrangentes usados para referenciar dados de gerenciamento de tags.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=pt-BR#for-web">Criar ou configurar uma propriedade de tag para a web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Instalar e configurar a extensão do SDK da Web</b> na propriedade da tag. Configure a extensão do SDK da Web para enviar dados para a sequência de dados configurada na etapa 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=pt-BR">Visão geral da extensão do SDK da Web da Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Iterar, validar e publicar</b> para produção. Adicione a propriedade da tag ao seu site. Em seguida, use elementos de dados, regras, entre outros, para personalizar sua implementação.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR">Visão geral da publicação</a></td>
</tr>

</table>


## Recursos adicionais

As tags podem ser altamente personalizadas. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#): saiba como a interface funciona e quais extensões estão disponíveis.

- [Documentação do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=pt-BR)
