---
title: linkDownloadFileTypes
description: Determine as extensões de arquivo que são automaticamente rastreadas como links de download.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkDownloadFileTypes

Quando [`trackDownloadLinks`](trackdownloadlinks.md) está ativado e um visitante clica em um link, o AppMeasurement verifica o URL do link para obter extensões de tipo de arquivo. Se o URL do link contiver um tipo de arquivo encontrado no, `linkDownloadFileTypes`uma solicitação de imagem do link de download será enviada automaticamente.

Use `linkDownloadFileTypes` para personalizar quais extensões de arquivo você deseja contar como links de download.

> [!NOTE] Somente os cliques reais são rastreados automaticamente. Os seguintes tipos de links não são rastreados automaticamente:
>
> * Downloads de arquivos que iniciam automaticamente quando uma página é carregada
> * Downloads que são acionados após um redirecionamento
> * Clicar com o botão direito do mouse e selecionar &#39;Salvar destino como...&#39;
> * Links que usam JavaScript, como `javascript:openLink()`
>
> 
Para esses tipos de download, você pode chamar manualmente o [`tl()`](../functions/tl-method.md) método.

Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Baixar extensões no Adobe Experience Platform Launch

Baixar extensões é uma lista de extensões de arquivo com um campo para adicionar mais sob a [!UICONTROL Link Tracking] opção ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão em Adobe Analytics.
4. Amplie o [!UICONTROL Link Tracking] acordeão, que revela o [!UICONTROL Download Extensions] campo.

Adicione extensões de arquivo à lista digitando texto no campo e clicando em [!UICONTROL Add]. Remova as extensões de arquivo da lista clicando no respectivo ícone &#39;X&#39;.

## s.linkDownloadFileTypes no AppMeasurement e Iniciar editor de código personalizado

A `s.linkDownloadFileTypes` variável é uma string de extensões de arquivo separadas por vírgulas. Não use espaços.

Se essa variável não estiver definida, o rastreamento automático de link de download não funcionará (mesmo se [`trackDownloadLinks`](trackdownloadlinks.md) estiver `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
