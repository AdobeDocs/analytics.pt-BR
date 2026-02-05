---
title: Implementar o Adobe Analytics com AppMeasurement para JavaScript
description: Saiba como implementar o Adobe Analytics usando JavaScript sem um sistema de gerenciamento de tags.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: ht
source-wordcount: '206'
ht-degree: 100%

---

# Implementar o Adobe Analytics com AppMeasurement para JavaScript

O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics. No entanto, com o aumento da popularidade dos sistemas de Tag Management, é recomendado usar [tags na Adobe Experience Platform](../launch/overview.md).

Uma visão geral de alto nível das tarefas de implementação:

![Como implementar o Adobe Analytics com AppMeasurement para Javascript, conforme descrito nesta seção.](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Tarefa</b></th><th style="width:20%"><b>Mais informações</b></th>
</tr>

<tr>
<td>1</td><td>Certifique-se de ter <b>definido um conjunto de relatórios</b></td><td><a href="../../admin/tools/manage-rs/report-suites-admin.md">Gerenciador do conjunto de relatórios</a></td>
</tr>

<tr>
<td>2</td><td><b>Baixe o código JavaScript necessário para o AppMeasurement</b> do Gerenciador de código. Descompacte o arquivo.</td><td><a href="../../admin/tools/code-manager-admin.md">Gerenciador de código</a></td>
</tr>

<tr>
<td>3</td><td><b>Adicione <code>AppMeasurement.js</code> ao arquivo de modelo do site</b>. O código contém as bibliotecas necessárias para enviar dados para a Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Defina as variáveis de configuração no <code>AppMeasurement.js</code></b>. Quando o objeto do Analytics é instanciado, essas variáveis garantem que as configurações de coleção de dados estejam corretas.

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
<td>5</td><td><b>Defina variáveis de nível de página no código da página do seu site</b>. Essas variáveis determinam dimensões e métricas específicas enviadas para a Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Variáveis de página</a></td>
</tr>

<tr>
<td>6</td><td><b>Envie os dados para a Adobe usando o método <code>t()</code></b>, quando todas as variáveis da página estiverem definidas.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">Método t()</a></td>
</tr>

<tr>
<td>7</td><td><b>Estender e validar sua implementação</b> antes de empurrá-la para a produção.</b></td><td></td>
</tr>

</table>

## Recursos adicionais

- [Visão geral de variáveis, funções, métodos e plug-ins](../vars/overview.md)
