---
title: linkDownloadFileTypes
description: Determine as extensões de arquivo que são automaticamente rastreadas como links de download.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) is enabled and a visitor clicks on a link, AppMeasurement checks the URL of the link for filetype extensions. Se o URL do link contiver um tipo de arquivo encontrado no `linkDownloadFileTypes`, uma solicitação de imagem do link de download será enviada automaticamente.

Use `linkDownloadFileTypes` para personalizar quais extensões de arquivo deseja contar como links de download.

>[!NOTE] Somente os cliques reais são rastreados automaticamente. Os seguintes tipos de links não são rastreados automaticamente:
>
> * Downloads de arquivos que começam automaticamente quando uma página é carregada
> * Downloads acionados após um redirecionamento
> * Clicar com o botão direito do mouse e selecionar &#39;Salvar destino como...&#39;
> * Links que usam JavaScript, como `javascript:openLink()`
>
> 
For these download types, you can manually call the [`tl()`](../functions/tl-method.md) method.

Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Baixar extensões no Adobe Experience Platform Launch

Download Extensions is a list of file extensions with a field to add more under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL Link Tracking] acordeão, que revela o [!UICONTROL Download Extensions] campo.

Add file extensions to the list by entering text in the field and clicking [!UICONTROL Add]. Remova as extensões de arquivo da lista clicando no respectivo ícone &#39;X&#39;.

## s.linkDownloadFileTypes no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkDownloadFileTypes` é uma cadeia de caracteres de extensões de arquivo separadas por vírgulas. Não use espaços.

Se essa variável não estiver definida, o rastreamento automático de link de download não funcionará (mesmo se [`trackDownloadLinks`](trackdownloadlinks.md) for `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
