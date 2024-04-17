---
title: Enviar dados para a Adobe Analytics usando a biblioteca JavaScript do SDK da Web
description: Comece com uma implementação limpa do SDK da Web para enviar dados para a Adobe Analytics usando a biblioteca do JavaScript.
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Enviar dados para a Adobe Analytics usando a biblioteca JavaScript do SDK da Web

Esse caminho de implementação envolve uma nova instalação do SDK da Web usando a biblioteca JavaScript do SDK da Web. Outros caminhos de implementação são abordados em páginas separadas:

* [Extensão de tag do SDK da Web](web-sdk-tag-extension.md): uma instalação nova do SDK da Web usando a extensão de tag do SDK da Web. Semelhante à abordagem da biblioteca JavaScript do SDK da Web (esta página), exceto que você gerencia a implementação usando tags na Coleção de dados da Adobe Experience Platform. Ele requer o grupo de campos Adobe Analytics ExperienceEvent, que inclui variáveis típicas do Analytics para serem incluídas no esquema XDM.
* [Extensão do Analytics para a extensão SDK da Web](analytics-extension-to-web-sdk.md): adote uma abordagem suave e metódica para mover a extensão de tag da Adobe Analytics para a extensão de tag do SDK da Web. Essa abordagem elimina a necessidade de usar o XDM até que sua organização esteja pronta para usar os serviços da Adobe Experience Platform, como o Customer Journey Analytics. Use o `data` em vez do `xdm` objeto para enviar dados ao Adobe.
* [AppMeasurement para a biblioteca JavaScript do SDK da Web](appmeasurement-to-web-sdk.md): uma abordagem suave e metódica para migrar para o SDK da Web, exceto pelo fato de que não usa tags. Em vez disso, você pode remover manualmente a biblioteca de coleta de dados do Adobe Analytics (`AppMeasurement.js`) e substitua-a pela biblioteca JavaScript do SDK da Web (`alloy.js`).

## Vantagens e desvantagens desse caminho de implementação

O uso da biblioteca JavaScript do SDK da Web para enviar dados para a Adobe Analytics tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Benefícios | Desvantagens |
| --- | --- |
| <ul><li>**Abordagem direta**: esse caminho de implementação é mais simples que as abordagens que movem as implementações existentes do Adobe Analytics. Se você não tiver uma implementação atual do Adobe Analytics com a qual se preocupar, preencha os campos XDM do SDK da Web aplicáveis.</li><li>**Esquema predefinido**: se sua organização não tiver necessidade de ter seu próprio esquema, você pode simplesmente usar o esquema direcionado para o Adobe Analytics. Esse conceito se aplica mesmo quando você avança em direção ao Customer Journey Analytics; o conceito de props e eVars não se aplica ao Customer Journey Analytics, mas você pode continuar usando props e eVars como dimensões personalizadas simples.</li></ul> | <ul><li>**Alterações de implementação exigem intervenção do desenvolvedor**: se quiser fazer alterações na implementação do SDK da Web, você deve trabalhar com a equipe de desenvolvimento para editar o código no site. A abordagem que utiliza a [Extensão de tag do SDK da Web](web-sdk-tag-extension.md) evita essa desvantagem.</li><li>**Bloqueado no usando um schema específico**: quando sua organização muda para o Customer Journey Analytics, você deve optar por continuar usando o esquema do Adobe Analytics ou migrar para o esquema de sua própria organização (que seria um conjunto de dados separado). Se a sua organização quiser evitar o esquema do Adobe Analytics e a migração para um conjunto de dados separado ao mudar para o Customer Journey Analytics, o Adobe recomenda um dos dois métodos a seguir:</li><ul><li>Use o `data` object: o `data` permite enviar dados para a Adobe Analytics sem estar em conformidade com um esquema XDM. Depois que o esquema da sua organização for criado, você poderá usar o mapeamento de sequência de dados para mapear `data` campos de objeto para XDM. Ambos os [Extensão do Analytics para a extensão SDK da Web](analytics-extension-to-web-sdk.md) e [AppMeasurement para a biblioteca JavaScript do SDK da Web](appmeasurement-to-web-sdk.md) usar este `data` objeto.</li><li>Ignorar totalmente o Adobe Analytics: se estiver implementando o SDK da Web, você pode enviar esses dados para um conjunto de dados na Adobe Experience Platform para uso no Customer Journey Analytics. Você pode usar qualquer esquema que desejar; a Adobe Analytics não está envolvida nesse fluxo de trabalho e, portanto, não requer o grupo de campos Adobe Analytics ExperienceEvent. Este método incorre no menor montante de dívida técnica, mas também deixa a Adobe Analytics totalmente fora de contexto.</li></ul></ul> |
