---
title: linkDownloadFileTypes
description: Determine as extensões de arquivo que são automaticamente rastreadas como links de download.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkDownloadFileTypes

Quando `trackDownloadLinks` estiver definido como `true` e um visitante clicar em um link, o AppMeasurement verificará o URL do link para as extensões do tipo de arquivo. Se o URL do link contiver um tipo de arquivo encontrado no, uma solicitação de imagem do link de download será enviada automaticamente. `linkDownloadFileTypes`

Use `linkDownloadFileTypes` para personalizar quais extensões de arquivo você deseja contar como links de download.

> [!NOTE] Somente os cliques reais são rastreados automaticamente. Os seguintes tipos de links não são rastreados automaticamente:
>
> * Downloads de arquivos que iniciam automaticamente quando uma página é carregada
> * Downloads que são acionados após um redirecionamento
> * Clicar com o botão direito do mouse e selecionar &#39;Salvar destino como...&#39;
> * Links que usam JavaScript, como `javascript:openLink()`
>
> 
Para esses tipos de download, você pode chamar a `tl()` função manualmente.

Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Baixar extensões no Adobe Experience Platform Launch

Baixar extensões é uma lista de extensões de arquivo com um campo para adicionar mais na opção Rastreamento [!UICONTROL de] link ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda a opção Rastreamento [!UICONTROL de] link, que revela o campo [!UICONTROL Baixar extensões] .

Adicione extensões de arquivo à lista inserindo texto no campo e clicando em [!UICONTROL Adicionar]. Remova as extensões de arquivo da lista clicando no ícone X correspondente.

## s.linkDownloadFileTypes no AppMeasurement e Iniciar editor de código personalizado

A `s.linkDownloadFileTypes` variável é uma string de extensões de arquivo separadas por vírgulas. Não use espaços.

Se essa variável não estiver definida, o rastreamento automático de link de download não funcionará (mesmo se `trackDownloadLinks` estiver `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v"
```
