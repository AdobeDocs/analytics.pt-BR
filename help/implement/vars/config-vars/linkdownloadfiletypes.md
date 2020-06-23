---
title: linkDownloadFileTypes
description: Determine as extensões de arquivo que são automaticamente rastreadas como links de download.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkDownloadFileTypes

Quando a [`trackDownloadLinks`](trackdownloadlinks.md) estiver ativada e um visitante clicar em um link, o AppMeasurement verificará o URL do link por extensões do tipo de arquivo. Se o URL do link contiver um tipo de arquivo encontrado no `linkDownloadFileTypes`, uma solicitação de imagem do link de download será enviada automaticamente.

Use `linkDownloadFileTypes` para personalizar quais extensões de arquivo deseja contar como links de download.

>[!NOTE] Somente os cliques reais são rastreados automaticamente. Os seguintes tipos de links não são rastreados automaticamente:
>
> * Downloads de arquivos que começam automaticamente quando uma página é carregada
> * Downloads acionados após um redirecionamento
> * Clicar com o botão direito do mouse e selecionar &#39;Salvar destino como...&#39;
> * Links que usam JavaScript, como `javascript:openLink()`
>
> 
Nesses tipos de download, você pode chamar o método [`tl()`](../functions/tl-method.md) manualmente.

Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Baixar extensões no Adobe Experience Platform Launch

Baixar extensões é uma lista de extensões de arquivo com um campo para adicionar mais na opção [!UICONTROL Rastreamento de link] ao configurar a extensão Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela o campo [!UICONTROL Baixar extensões].

Adicione extensões de arquivo à lista inserindo texto no campo e clicando em [!UICONTROL Adicionar]. Remova as extensões de arquivo da lista clicando no ícone &#39;X&#39; correspondente.

## s.linkDownloadFileTypes no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkDownloadFileTypes` é uma cadeia de caracteres de extensões de arquivo separadas por vírgulas. Não use espaços.

Se essa variável não estiver definida, o rastreamento automático de link de download não funcionará (mesmo se [`trackDownloadLinks`](trackdownloadlinks.md) for `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
