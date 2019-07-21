---
title: Implantar o Adobe Analytics em um ambiente dev
seo-title: Implantar o Adobe Analytics em um ambiente dev
description: Saiba como usar o Adobe Experience Platform Launch para implantar o Adobe Analytics em seu ambiente de desenvolvimento.
seo-description: Saiba como usar o Adobe Experience Platform Launch para implantar o Adobe Analytics em seu ambiente de desenvolvimento.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Implantar uma implementação do Analytics em um ambiente de desenvolvimento

Depois que uma propriedade tiver sido criada e configurada no Launch, as bibliotecas estarão prontas para serem implantadas e o código implementado em seu site.

## Pré-requisitos

[Crie e configure uma propriedade para o Adobe Analytics no Launch](create-analytics-property.md): Acesse a ferramenta e crie um espaço para sua implementação do Analytics.

## Criar adaptadores e ambientes

O Launch acomoda muitos fluxos de trabalho organizacional na implantação do código. Siga estas etapas para criar os componentes mínimos necessários para uma implementação do Analytics. Como administrador de lançamento, você pode trabalhar em sua organização para estabelecer o fluxo de trabalho correto para a implantação das soluções da Adobe.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Clique na propriedade Launch que pretende implementar em seu site.
3. Clique na guia Adaptadores e, em seguida, clique em Adicionar adaptador.
4. Dê um nome a ela "Akamai" e selecione Akamai no menu suspenso. Clique em Salvar.
5. Vá até a guia Ambientes e clique em Criar novo ambiente.
6. Selecione Desenvolvimento, nomeie-o como "Ambiente de desenvolvimento" e, em seguida, selecione o adaptador Akamai na lista suspensa. Clique em Criar e em Fechar.
7. Clique em Adicionar ambiente, selecione Armazenamento temporário, dê um nome a ele "Ambiente de armazenamento temporário" e selecione o adaptador Akamai. Clique em Criar e em Fechar.
8. Clique novamente em Adicionar ambiente, selecione Produção, nomeie como "Ambiente de produção" e, em seguida, selecione o adaptador Akamai. Clique em Criar e em Fechar.

## Criar uma biblioteca dev

Apesar de todas as alterações e configurações feitas até agora, nenhum código foi realmente publicado. A criação de uma biblioteca, traduzida lentamente como uma coleção de alterações, permite que a publicação de código seja usada em seu site.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Clique na propriedade Launch que pretende implementar em seu site.
3. Clique na guia Publicação e, em seguida, clique em Adicionar nova biblioteca.
4. Dê um nome para as alterações iniciais da biblioteca e selecione seu ambiente de desenvolvimento.
5. Clique em Adicionar todos os recursos alterados, que lista automaticamente o Adobe Analytics, o Serviço de identidade e o Core.
6. Clique em Salvar.
7. De volta à tela de fluxo de trabalho de publicação, clique na lista suspensa ao lado da nova biblioteca e clique em Criar para desenvolvimento. Após alguns segundos, o ponto amarelo na biblioteca fica verde, indicando que a criação foi bem-sucedida.
8. Vá para a guia Ambientes e clique em seu ambiente de desenvolvimento.
9. Em «Instalar lançamento», copie os blocos de código e forneça-os aos proprietários de site da sua organização.

## Instalar inicialização no ambiente de desenvolvimento do seu site

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. Esse código é normalmente colocado no modelo sobreposto do site. Uma página em branco contendo o código de implementação seria semelhante ao seguinte:

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
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Solução de problemas

**Falha ao tentar construir.**

Um motivo comum é porque os elementos já existem em outras bibliotecas enviadas para armazenamento temporário ou produção. Ao criar bibliotecas, certifique-se de que apenas os recursos alterados sejam adicionados à biblioteca.

## Documentação e recursos adicionais

- [Introdução ao Launch](https://docs.adobelaunch.com/getting-started): Saiba mais sobre o fluxo de trabalho básico do Launch
- [Iniciar administração](https://docs.adobelaunch.com/administration): Saiba mais sobre adaptadores e ambientes

## Próximas etapas

[Valide sua implementação do Analytics e publique na produção](validate-publish-prod.md): Comece a receber valor do Adobe Analytics.
