---
title: Implementar o Adobe Analytics usando a extensão do Analytics
description: Saiba como implementar o Adobe Analytics usando tags e a extensão do Analytics
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 83%

---

# Implementar o Adobe Analytics usando a extensão do Analytics

Durante a vida útil do Adobe Analytics, a Adobe ofereceu vários diferentes métodos de implementação do código no site para a coleta de dados. O método recomendado atual de Adobe é por meio de [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR) no Adobe Experience Platform.

Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.

Todos os clientes com um contrato ativo do Adobe Experience Cloud podem usar Tags. Se não tiver certeza se tem acesso, entre em contato com um dos administradores de sistema da Experience Cloud na organização.

Uma visão geral de alto nível das tarefas de implementação:



![Como implementar o Adobe Analytics usando o fluxo de trabalho da extensão do Analytics, conforme descrito nesta seção.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarefa</b></th><th style="width:35%"><b>Mais informações</b></th>
</tr>

<tr>
<td> 1</td>
<td>Certifique-se de que você <b>definiu um conjunto de relatórios</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gerenciador do conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Criar uma camada de dados</b> para gerenciar o rastreamento dos dados no seu site.</td>
<td>
<a href="../prepare/data-layer.md">Criar uma camada de dados</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Crie uma propriedade de tag</b>. Propriedades são containers abrangentes usados para referenciar dados de gerenciamento de tags.</td>
<td><a href="../launch/create-analytics-property.md">Criar uma propriedade de tag do Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Instale a extensão do Analytics</b> na propriedade da tag. Configure a extensão do Analytics para enviar dados para o Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=pt-BR">Visão geral da extensão do Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Implante em um ambiente de desenvolvimento</b>: tenha um ambiente em que você possa interagir com o desenvolvimento de tags.</td>
<td><a href="./deploy-dev.md">Implantar uma implementação do Analytics em um ambiente de desenvolvimento</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validar e publicar na produção</b>. Incorpore o código para incluir a propriedade da tag nas páginas do site. Em seguida, use elementos de dados, regras, entre outros, para personalizar sua implementação.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code">Incorporar código</a><br/><a href="./validate-publish-prod.md">Validar uma implementação de desenvolvimento e publicar na produção</a></td>
</tr>

</table>

## Recursos adicionais

As tags podem ser altamente personalizadas. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#): saiba como a interface funciona e quais extensões estão disponíveis.

- [Variáveis de implementação](../vars/overview.md): determine quais variáveis você deseja enviar para os servidores de coleta de dados.
