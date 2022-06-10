---
title: linkDownloadFileTypes
description: Determine as extensões de arquivo que são automaticamente rastreadas como links de download.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 49%

---

# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) ou [`clickCollectionEnabled`](trackdownloadlinks.md) (SDK da Web) estiver ativado e um visitante clicar em um link, o AppMeasurement verificará o URL do link por extensões do tipo de arquivo. Se o URL do link contiver um tipo de arquivo correspondente, uma solicitação de imagem do link de download será enviada automaticamente.

Use `linkDownloadFileTypes` para personalizar quais extensões de arquivo deseja contar como links de download.

>[!NOTE]
>
>Somente os cliques reais são rastreados automaticamente. Os seguintes tipos de links não são rastreados automaticamente:
>
>* Downloads de arquivos que começam automaticamente quando uma página é carregada
>* Downloads acionados após um redirecionamento
>* Clicar com o botão direito do mouse e selecionar &#39;Salvar destino como...&#39;
>* Links que usam JavaScript, como `javascript:openLink()`
>
>Nesses tipos de download, você pode enviar manualmente uma [`link tracking`](../functions/tl-method.md) chame.

Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Baixar qualificador de link usando a extensão SDK da Web

O [!UICONTROL Baixar qualificador de link] o campo de texto usa regex para determinar se um link clicado se qualifica para ser um link de download.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para o [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** botão abaixo [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleta de dados], defina o valor desejado no **[!UICONTROL Baixar qualificador de link]** campo de texto.

## Baixar qualificador de link manualmente implementando o SDK da Web

[Configurar](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) o SDK que usa [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). O campo usa regex no URL clicado para determinar se é um link de download válido. If `downloadLinkQualifier` não estiver definido, o valor padrão será definido como `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Baixar extensões usando a extensão Adobe Analytics

Baixar extensões é uma lista de extensões de arquivo com um campo para adicionar mais na opção [!UICONTROL Rastreamento de link] ao configurar a extensão Adobe Analytics.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela o campo **[!UICONTROL Baixar extensões]**.

Adicione extensões de arquivo à lista inserindo texto no campo e clicando em **[!UICONTROL Adicionar]**. Remova as extensões de arquivo da lista clicando nas respectivas **&#39;X&#39;** ícone .

## s.linkDownloadFileTypes no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.linkDownloadFileTypes` é uma cadeia de caracteres de extensões de arquivo separadas por vírgulas. Não use espaços.

Se essa variável não estiver definida, o rastreamento automático de link de download não funcionará (mesmo se [`trackDownloadLinks`](trackdownloadlinks.md) for `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
