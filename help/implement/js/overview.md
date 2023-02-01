---
title: Implementar o Adobe Analytics com o AppMeasurement para JavaScript
description: Saiba como implementar o Adobe Analytics usando JavaScript sem um sistema de gerenciamento de tags.
feature: Implementation Basics
source-git-commit: 93e16a538d6dc05c9cbf0703664aa5320f45b731
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 45%

---

# Implementar o Adobe Analytics com o AppMeasurement para JavaScript

O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics. No entanto, com o aumento da popularidade dos sistemas de Tag Management, é recomendado usar [tags na Adobe Experience Platform](../launch/overview.md).

Uma visão geral de alto nível das tarefas de implementação:

![Implementação do Adobe Analytics com visão geral do AppMeasurement](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th><b>Tarefa</b></th><th><b>Mais Informações</b></th>
</tr>

<tr>
<td>1</td><td>Certifique-se de que <b>definiu um conjunto de relatórios</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Gerenciador do Conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td><td><b>Baixe o código JavaScript necessário para AppMeasurement</b> do Gerenciador de código. Descompacte o arquivo.</td><td><a href="../../admin/admin/code-manager-admin.md">Gerenciador de código</a></td>
</tr>

<tr>
<td>3</td><td><b>Adicionar <code>AppMeasurement.js</code> para o arquivo de modelo do seu site</b>. O código contém as bibliotecas necessárias para enviar dados para o Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Defina as variáveis de configuração em <code>AppMeasurement.js</code></b>. Quando o objeto do Analytics é instanciado, essas variáveis garantem que as configurações de coleta de dados estejam corretas.

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">Variáveis de configuração</a></td>
</tr>

<tr>
<td>5</td><td><b>Defina variáveis de nível de página no código de página do site</b>. Essas variáveis determinam dimensões e métricas específicas enviadas para a Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Variáveis de página</a></td>
</tr>

<tr>
<td>6</td><td><b>Envie os dados para o Adobe usando o <code>t()</code> método</b>, quando todas as variáveis de página forem definidas.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">método t()</a></td>
</tr>

<tr>
<td>7</td><td><b>Estender e validar sua implementação</b> antes de empurrá-lo para a produção.</b></td><td></td>
</tr>

</table>

## Recursos adicionais

- [Visão geral sobre variáveis, funções, métodos e plug-ins](../vars/overview.md)
