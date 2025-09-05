---
title: Enviar dados para a Adobe Analytics usando a extensão de tag da Web SDK
description: Comece com uma implementação limpa da Coleção de dados do Adobe Experience Platform para enviar dados para a Adobe Analytics usando o XDM e o grupo de campos do Adobe Analytics ExperienceEvent.
exl-id: 235b3d68-92dd-4ca4-8889-1e1f2d83f47e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 16%

---

# Enviar dados para a Adobe Analytics usando a extensão de tag da Web SDK

Esse caminho de implementação envolve uma nova instalação do Web SDK usando tags na Coleção de dados da Adobe Experience Platform. Outros caminhos de implementação são abordados em páginas separadas:

* [Biblioteca JavaScript do Web SDK](web-sdk-javascript-library.md): uma nova instalação do Web SDK usando a biblioteca JavaScript do Web SDK (`alloy.js`). Semelhante à abordagem de extensão de tag do Web SDK (esta página), exceto que você gerencia a implementação por conta própria em vez de usar a interface do usuário de tags. Ele requer o grupo de campos Adobe Analytics ExperienceEvent, que inclui variáveis típicas do Analytics para serem incluídas no esquema XDM.
* [Extensão do Analytics para a extensão do Web SDK](analytics-extension-to-web-sdk.md): adote uma abordagem suave e metódica para mover da extensão de marcas da Adobe Analytics para a extensão de marcas do Web SDK. Essa abordagem elimina a necessidade de usar o XDM até que sua organização esteja pronta para usar os serviços da Adobe Experience Platform, como o Customer Journey Analytics. Use o objeto `data` em vez do objeto `xdm` para enviar dados ao Adobe.
* [Biblioteca JavaScript do AppMeasurement para Web SDK](appmeasurement-to-web-sdk.md): uma abordagem suave e metódica para migrar para o Web SDK, exceto por não usar marcas. Em vez disso, você remove manualmente a biblioteca de coleta de dados do Adobe Analytics (`AppMeasurement.js`) e a substitui pela biblioteca JavaScript do Web SDK (`alloy.js`).

## Vantagens e desvantagens desse caminho de implementação

O uso da extensão Web SDK para enviar dados para o Adobe Analytics tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Vantagens | Desvantagens |
| --- | --- |
| <ul><li>**Abordagem mais direta**: esse caminho de implementação é o mais simples e geralmente o caminho recomendado para novas implementações do Web SDK. Se você não tiver uma implementação atual do Adobe Analytics com a qual se preocupar, preencha os campos XDM aplicáveis do Web SDK.</li><li>**Esquema predefinido**: se sua organização não tiver uma necessidade para seu próprio esquema, você pode simplesmente usar o esquema direcionado para a Adobe Analytics. Esse conceito se aplica mesmo quando você avança em direção ao Customer Journey Analytics; o conceito de props e eVars não se aplica ao Customer Journey Analytics, mas você pode continuar usando props e eVars como dimensões personalizadas simples.</li><li>**Gerenciar marcas sem a intervenção do desenvolvedor**: as marcas permitem gerenciar a implementação sem solicitar que os desenvolvedores façam alterações de código na implementação. Seus desenvolvedores instalam o script do carregador de tags e você tem controle total sobre como os dados são coletados.</li></ul> | <ul><li>**Bloqueado para usar um esquema específico**: quando sua organização mudar para o Customer Journey Analytics, você deve optar por continuar usando o esquema do Adobe Analytics ou migrar para o esquema de sua própria organização (que seria um conjunto de dados separado). Se a sua organização quiser evitar o esquema do Adobe Analytics e a migração para um conjunto de dados separado ao migrar para o Customer Journey Analytics, a Adobe recomenda um dos dois métodos a seguir:<ul><li>Usar o objeto `data`: o objeto `data` permite enviar dados para a Adobe Analytics sem estar em conformidade com um esquema XDM. Depois que o esquema da sua organização for criado, você poderá usar o mapeamento de sequência de dados para mapear campos de objeto `data` para o XDM. A [extensão do Analytics para a extensão do Web SDK](analytics-extension-to-web-sdk.md) e a [biblioteca JavaScript do AppMeasurement para o Web SDK](appmeasurement-to-web-sdk.md) usam este objeto `data`.</li><li>Ignorar totalmente o Adobe Analytics: se estiver implementando a Web SDK, você poderá enviar esses dados para um conjunto de dados na Adobe Experience Platform para uso no Customer Journey Analytics. Você pode usar qualquer esquema que desejar; a Adobe Analytics não está envolvida nesse fluxo de trabalho e, portanto, não requer o grupo de campos Adobe Analytics ExperienceEvent. Este método incorre no menor montante de dívida técnica, mas também deixa a Adobe Analytics totalmente fora de contexto.</li></ul></ul> |

>[!IMPORTANT]
>
>Esse método de implementação exige que você use um esquema configurado para o Adobe Analytics. Se sua organização planejar usar seu próprio esquema com a Customer Journey Analytics no futuro, o uso do esquema da Adobe Analytics poderá criar confusão para administradores de dados ou arquitetos. Há várias opções para atenuar esse obstáculo:
>
>* Você pode usar o esquema do Adobe Analytics no CJA. Observe que o CJA não tem um conceito de props ou eVars; eles são tratados como qualquer outro campo de esquema. Observe também que o uso do esquema do Adobe Analytics no CJA pode dificultar o uso de outros serviços de plataforma, como o Adobe Journey Optimizer ou o Real-Time Customer Data Platform.
>* Você pode usar o objeto de dados, de modo semelhante a um fluxo de trabalho de migração. Observe que o uso do objeto de dados exige o mapeamento de cada campo de objeto de dados para um campo de esquema XDM.
>* Você pode ignorar completamente a implementação do Adobe Analytics e enviar dados para o Adobe Experience Platform usando seu próprio esquema. Essa abordagem é ideal a longo prazo e permite que sua organização comece a usar o Customer Journey Analytics.

## Etapas necessárias para implementar a extensão de tag do Web SDK

Uma visão geral de alto nível das tarefas de implementação:

![Como implementar o Adobe Analytics usando o fluxo de trabalho de extensão do Web SDK, conforme descrito nesta seção.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarefa</b></th><th style="width:35%"><b>Mais informações</b></th>
</tr>

<tr>
<td>1</td>
<td>Certifique-se de que você <b>definiu um conjunto de relatórios</b>.</td>
<td><a href="/help/admin/tools/manage-rs/report-suites-admin.md">Gerenciador do conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurar esquemas</b>. Para padronizar a coleta de dados para uso em aplicativos que utilizam a Adobe Experience Platform, a Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR">Visão geral da interface de esquemas</a></td>
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
<td><b>Adicionar um serviço Adobe Analytics</b> à sua sequência de dados. Esse serviço controla se e como os dados são enviados para o Adobe Analytics e para quais conjuntos de relatórios especificamente.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Adicionar o serviço Adobe Analytics a uma sequência de dados</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Criar uma propriedade de marca</b>. As propriedades são contêineres abrangentes usados para fazer referência aos dados do gerenciamento de tags.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-web">Criar ou configurar uma propriedade de tag para a web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Instalar e configurar a extensão do SDK da Web</b> na propriedade da tag. Configure a extensão do SDK da Web para enviar dados para a sequência de dados configurada na etapa 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=pt-BR">Visão geral da extensão do SDK da Web da Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Iterar, validar e publicar</b> para produção. Incorpore o código para incluir a propriedade da tag nas páginas do site. Em seguida, use elementos de dados, regras, entre outros, para personalizar sua implementação.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code">Código de inserção</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR">Visão geral da publicação</a></td>
</tr>

</table>
