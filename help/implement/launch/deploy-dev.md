---
title: Implantar o Adobe Analytics em um ambiente de desenvolvimento
description: Saiba como usar tags para implantar o Adobe Analytics no ambiente de desenvolvimento.
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 48%

---

# Implantar uma implementação do Analytics em um ambiente de desenvolvimento

Depois de criar e configurar uma propriedade de tag, as bibliotecas estarão prontas para serem implantadas e o código será implementado em seu site.

## Pré-requisitos

[Criar e configurar uma propriedade de tag para o Adobe Analytics](create-analytics-property.md): acesse a ferramenta e crie um espaço para a implementação do Analytics.

## Criar adaptadores e ambientes

As tags acomodam muitos workflows organizacionais na implantação do código. Siga estas etapas para criar os componentes mínimos necessários para uma implementação do Analytics. Como administrador de tags, você pode trabalhar na empresa para estabelecer o fluxo de trabalho correto para implantar as soluções da Adobe.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade da tag que pretende implementar no site.
3. Clique em **[!UICONTROL Hosts]** e em **[!UICONTROL Adicionar Host]**.
4. Nomeie-o como `"Adobe managed"` e selecione **[!UICONTROL Gerenciado por Adobe]** na lista suspensa de tipos. Clique em Salvar.
5. Navegue até **[!UICONTROL Ambientes]** e clique em **[!UICONTROL Adicionar ambiente]**.
6. Selecione **[!UICONTROL Desenvolvimento]**, nomeie-o como `"Dev Environment"` e selecione o host gerenciado de Adobe na lista suspensa. Clique em **[!UICONTROL Salvar]**.
7. Uma janela modal é exibida mostrando as Instruções de instalação da Web. Retornaremos a esta janela posteriormente; clique em **[!UICONTROL Fechar]** por enquanto.
8. Clique em **[!UICONTROL Adicionar ambiente]**, selecione **[!UICONTROL Preparo]**, nomeie-o como `"Staging Environment"` e selecione o host gerenciado de Adobe. Clique em **[!UICONTROL Criar]** e feche a janela modal de instruções de instalação.
9. Clique novamente em **[!UICONTROL Adicionar ambiente]**, selecione **[!UICONTROL Produção]**, nomeie-o como `"Production Environment"` e selecione o host gerenciado de Adobe. Clique em **[!UICONTROL Criar]** e feche a janela modal de instruções de instalação.

## Criar uma biblioteca de desenvolvimento

Apesar de todas as mudanças e configurações feitas até agora, nenhum código foi publicado. A criação de uma biblioteca, praticamente traduzida como uma coleção de alterações, permite que a publicação do código seja usada no site.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade da tag que pretende implementar no site.
3. Clique na guia **[!UICONTROL Fluxo de publicação]** e em **[!UICONTROL Adicionar biblioteca]**. Consulte [Visão geral da publicação](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR) na documentação de Marcas para obter mais informações sobre esta página.
4. Nomeie a biblioteca `'Initial changes'` e selecione seu ambiente de desenvolvimento.
5. Clique em **[!UICONTROL Adicionar todos os recursos alterados]**, que lista automaticamente o Adobe Analytics, o Serviço de Identidade e o Principal.
6. Clique em **[!UICONTROL Salvar]**.
7. De volta à tela do fluxo de trabalho de publicação, clique na lista suspensa ao lado da nova biblioteca e clique em **[!UICONTROL Criar para desenvolvimento]**. Após alguns segundos, o ponto amarelo na biblioteca fica verde, indicando que a criação foi bem-sucedida.
8. Navegue até **[!UICONTROL Ambientes]** e clique no ícone de instalação à direita do ambiente de desenvolvimento. Essa ação exibe a janela modal Instruções de instalação da Web novamente.
9. Copie os blocos de código e forneça-os aos proprietários do site da organização.

## Instale tags no ambiente de desenvolvimento do site

Se você controlar o código do site, implemente cada bloco de código no respectivo local:

* A marca principal pertence à marca `<head>` no site.
* Se você optar por carregar tags de forma síncrona, também deverá incluir um segundo bloco de código logo abaixo da tag `</body>` de fechamento no site. Você pode optar por carregar as marcas da biblioteca de forma síncrona alternando a opção **[!UICONTROL Carregar biblioteca de forma assíncrona]** nas Instruções de Instalação da Web.

O código da tag normalmente é colocado no modelo abrangente do site. Uma página em branco contendo apenas o código de implementação seria semelhante ao seguinte:

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Solução de problemas

**Falha ao tentar criar**.

Um motivo comum é porque os elementos já existem em outras bibliotecas enviadas para preparo ou produção. Ao criar bibliotecas inicialmente, verifique se apenas os recursos alterados foram adicionados à biblioteca.

## Próximas etapas

[Valide a implementação do Analytics e publique na produção](validate-publish-prod.md): comece a obter valor do Adobe Analytics.
