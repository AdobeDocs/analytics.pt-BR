---
title: Criar uma propriedade do Analytics no Launch
seo-title: Criar uma propriedade do Adobe Analytics na Adobe Experience Platform Launch
description: Crie um espaço para personalizar como os dados são coletados usando o Adobe Experience Platform Launch.
seo-description: Crie um espaço para personalizar como os dados são coletados no Adobe Analytics usando o Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Criar uma propriedade do Analytics na Adobe Experience Platform Launch

O Adobe Experience Platform Launch é a ferramenta que você pode usar para integrar as soluções da Experience Cloud em seu site (incluindo o Analytics). Esta página descreve especificamente como um administrador de inicialização pode obter uma implementação básica do Adobe Analytics configurada corretamente.

## Pré-requisitos

[Criar um conjunto de relatórios](../../admin/admin-console/create-report-suite.md): Criar um silo para que os dados do Analytics sejam coletados

## Criar uma propriedade e instalar extensões vitais

As propriedades são contêineres abrangentes que você usa para gerenciar tags. As extensões permitem instalar tags específicas do produto e configurá-las.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Clique em «Nova propriedade».
1. Dê um nome à sua Propriedade, como o título do seu site, e insira o domínio que pretende implementar do Analytics. Clique em Salvar.
1. Clique em sua propriedade recém-criada para inserir suas configurações.
1. Clique na guia Extensões e clique em Catálogo.
1. Localize o Serviço de identidade e clique em Instalar.
1. Todas as configurações, incluindo a ID de empresa da Experience Cloud, já devem estar preenchidas. Clique em Salvar.
1. De volta ao catálogo de extensões, localize o Adobe Analytics e clique em Instalar.

## Criar elementos de dados para o Adobe Analytics

Os elementos de dados são referências a partes específicas do site para coletar valores de variável.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. Clique na propriedade Launch que pretende implementar em seu site.
3. Clique na guia Elementos de dados e clique em Criar novo elemento de dados.
4. Forneça ao elemento de dados as seguintes configurações:
   * Nome: Nome da página
   * Extensão: Principal
   * Tipo de elemento de dados: Variável javascript
   * Path to variable: `window.document.title`
      > [!NOTE] Observação: Este é um valor de exemplo para ajudar a começar. Se a sua organização definir um valor melhor para o nome da página, como um valor de camada de dados, você pode inseri-lo aqui.
   * Texto limpo marcado
   * Duração: Pageview
5. Clique em Salvar.

## Criar regras para o Adobe Analytics

As regras mapeiam elementos de dados para valores de variável do Analytics e determinam quando esses valores são enviados para os servidores da Adobe.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Clique na propriedade Launch que pretende implementar em seu site.
1. Click Create New Rule and name it `Global Rule`.
1. Clique em Adicionar ao lado de eventos e insira as seguintes configurações:
   * Extensão: Principal
   * Tipo de evento: Biblioteca carregada (Início da página)
   * Nome: Core - Biblioteca carregada (Início da página)
   * Pedido: 50
1. Clique em Manter alterações.
1. Em Ações, clique em Adicionar e insira as seguintes configurações:
   * Extensão: Adobe Analytics
   * Tipo de ação: Definir variáveis
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. Clique em Manter alterações.
1. Clique no sinal de Mais ao lado das ações para adicionar outra ação e insira as seguintes configurações:
   * Extensão: Adobe Analytics
   * Tipo de ação: Enviar sinal
   * Nome: Adobe Analytics - Enviar sinal
   * Rastreamento: s. t ()
1. Clique em Manter alterações.
1. Verifique se você tem o evento e duas ações definidas e clique em Salvar.

## Documentação e recursos adicionais

* [Documentação de extensão do Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): Documentação completa específica à extensão do Adobe Analytics na Adobe Experience Platform Launch.
* [Introdução ao Launch](https://docs.adobelaunch.com/getting-started): Documentação completa para o Launch, incluindo um guia de introdução mais detalhado
* [Canal do youtube inicialização da Adobe Experience Platform](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd): Saiba como usar o Launch através de vídeos

## Próximas etapas

[Implante sua implementação do Analytics no ambiente dev](deploy-dev.md): Obtenha o código do Analytics em um ambiente de teste.
