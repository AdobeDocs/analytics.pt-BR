---
title: Implantar o Adobe Analytics em um ambiente de desenvolvimento
description: Saiba como usar tags para implantar o Adobe Analytics no ambiente de desenvolvimento.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: 9b9a338e3652c85ae0f8ce79b98a2babf427ab4c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 66%

---

# Implantar uma implementação do Analytics em um ambiente de desenvolvimento

Depois de criar e configurar uma propriedade de tag, as bibliotecas estarão prontas para serem implantadas e o código será implementado em seu site.

>[!NOTE]
>A Adobe Experience Platform Launch foi reformulada como um conjunto de tecnologias de coleta de dados no Experience Platform. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o seguinte [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obter uma referência consolidada das alterações de terminologia.

## Pré-requisitos

[Criar e configurar uma propriedade de tag para o Adobe Analytics](create-analytics-property.md): Acesse a ferramenta e crie um espaço para a implementação do Analytics.

## Criar adaptadores e ambientes

As tags acomoda muitos fluxos de trabalho organizacionais na implantação do código. Siga estas etapas para criar os componentes mínimos necessários para uma implementação do Analytics. Como administrador de tags, você pode trabalhar em sua organização para estabelecer o fluxo de trabalho correto para implantar soluções do Adobe.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
2. Clique na propriedade de tag que você pretende implementar em seu site.
3. Clique na guia Adaptadores e depois clique em Adicionar adaptador.
4. Nomeie-o como &quot;Akamai&quot; e selecione Akamai na lista suspensa de tipos. Clique em Salvar.
5. Vá para a guia Ambientes e depois clique em Criar novo ambiente.
6. Selecione Desenvolvimento, nomeie-o como &quot;Ambiente de desenvolvimento&quot; e selecione o adaptador Akamai na lista suspensa. Clique em Criar e depois em Fechar.
7. Clique em Adicionar ambiente, selecione Preparo, nomeie-o como &quot;Ambiente de preparo&quot; e depois selecione o adaptador Akamai. Clique em Criar e depois em Fechar.
8. Clique em Adicionar ambiente novamente, selecione Produção, nomeie-o como &quot;Ambiente de produção&quot; e depois selecione o adaptador Akamai. Clique em Criar e depois em Fechar.

## Criar uma biblioteca de desenvolvimento

Apesar de todas as mudanças e configurações feitas até agora, nenhum código foi publicado. A criação de uma biblioteca, praticamente traduzida como uma coleção de alterações, permite que a publicação do código seja usada no site.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
2. Clique na propriedade de tag que você pretende implementar em seu site.
3. Clique na guia Publicação e depois em Adicionar nova biblioteca.
4. Nomeie a biblioteca como &quot;Alterações iniciais&quot; e selecione o ambiente de desenvolvimento.
5. Clique em Adicionar todos os recursos alterados, que lista automaticamente o Adobe Analytics, o Serviço de identidade e o Principal.
6. Clique em Salvar.
7. De volta à tela de fluxo de trabalho da publicação, clique na lista suspensa ao lado da nova biblioteca e clique em Criar para desenvolvimento. Após alguns segundos, o ponto amarelo na biblioteca fica verde, indicando que a criação foi bem-sucedida.
8. Vá para a guia Ambientes e clique no ambiente de desenvolvimento.
9. Em &quot;Instalar tags&quot;, copie os blocos de código e forneça-os aos proprietários do site de sua organização.

## Instalar tags no ambiente de desenvolvimento do seu site

Se você controlar o código do site, implemente os dois blocos de código nos respectivos locais (na tag `<head>` e logo acima da tag de fechamento `</body>`) em cada página do site. Esse código geralmente é colocado no modelo abrangente do site. Uma página em branco contendo apenas o código de implementação seria semelhante ao seguinte:

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

**Falha ao tentar criar**.

Um motivo comum é porque os elementos já existem em outras bibliotecas enviadas para preparo ou produção. Ao criar bibliotecas inicialmente, verifique se apenas os recursos alterados foram adicionados à biblioteca.

## Documentação e recursos adicionais

- [Guia](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en) de início rápido: Saiba mais sobre o fluxo de trabalho básico da implementação de tags
- [Visão geral](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en) da publicação: Saiba mais sobre publicação e ambientes

## Próximas etapas

[Valide a implementação do Analytics e publique na produção](validate-publish-prod.md): comece a obter valor do Adobe Analytics.
