---
title: Criar uma propriedade do Analytics no Launch
description: Crie um espaço para personalizar como os dados são coletados, usando o Adobe Experience Platform Launch.
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Criar uma propriedade do Analytics no Adobe Experience Platform Launch

O Adobe Experience Platform Launch é a ferramenta que você pode usar para integrar soluções da Experience Cloud em seu site (incluindo o Analytics). Esta página descreve especificamente como um administrador do Launch pode configurar uma implementação básica do Adobe Analytics corretamente.

## Pré-requisitos

[Criar um conjunto de relatórios](/help/admin/admin-console/create-report-suite.md): criar um silo para que os dados do Analytics sejam coletados.

## Criar uma propriedade e instalar extensões essenciais

As propriedades são contêineres abrangentes que você usa para gerenciar tags. As extensões permitem instalar tags específicas do produto e configurá-las.

1. Vá para [launch.adobe.com](https://launch.adobe.com) e faça logon, se solicitado.
1. Clique em &quot;Nova propriedade&quot;.
1. Dê um nome à Propriedade, como o título do site, e insira o domínio em que você pretende implementar o Analytics. Clique em Salvar.
1. Clique na propriedade recém-criada para inserir as configurações.
1. Clique na guia Extensões e, em seguida, clique em Catálogo.
1. Localize Serviço de identidade e clique em Instalar.
1. Todas as configurações, incluindo a Experience Cloud Organization ID, já devem ser preenchidas. Clique em Salvar.
1. De volta ao catálogo de extensões, localize o Adobe Analytics e clique em Instalar.

## Criar elementos de dados do Adobe Analytics

Os elementos de dados são referências a partes específicas do site para coletar valores de variável.

1. Vá para [launch.adobe.com](https://launch.adobe.com) e faça logon, se solicitado.
2. Clique na propriedade do Launch que pretende implementar no site.
3. Clique na guia Elementos de dados e, em seguida, clique em Criar novo elemento de dados.
4. Atribua ao elemento de dados as seguintes configurações:
   * Nome: nome da página
   * Extensão: principal
   * Tipo de elemento de dados: variável JavaScript
   * Caminho para a variável: `window.document.title`
      > [!NOTE] Observação: este é um exemplo de valor para ajudar a começar. Se sua empresa definir um valor melhor para o nome da página, como um valor de camada de dados, você pode inseri-lo aqui.
   * Limpar texto marcado
   * Duração: Pageview
5. Clique em Salvar.

## Criar regras para o Adobe Analytics

As regras mapeiam os elementos de dados para os valores de variáveis do Analytics e determinam quando esses valores são enviados para os servidores da Adobe.

1. Vá para [launch.adobe.com](https://launch.adobe.com) e faça logon, se solicitado.
1. Clique na propriedade do Launch que pretende implementar no site.
1. Clique em Criar nova regra e nomeie-a `Global Rule`.
1. Clique em Adicionar ao lado dos eventos e insira as seguintes configurações:
   * Extensão: principal
   * Tipo de evento: biblioteca carregada (início da página)
   * Nome: principal - biblioteca carregada (início da página)
   * Ordem: 50
1. Clique em Manter alterações.
1. Em Ações, clique em Adicionar e insira as seguintes configurações:
   * Extensão: Adobe Analytics
   * Tipo de ação: definir variáveis
   * Nome da página: clique no ícone de contêiner e selecione o elemento de dados `Page Name`
   * Campanha: parâmetro de consulta com um valor de `cid`
1. Clique em Manter alterações.
1. Clique no sinal de Mais ao lado das ações para adicionar outra ação e insira as seguintes configurações:
   * Extensão: Adobe Analytics
   * Tipo de ação: enviar beacon
   * Nome: Adobe Analytics - enviar beacon
   * Rastreamento: s.t()
1. Clique em Manter alterações.
1. Verifique se o evento e duas ações estão definidos e clique em Salvar.

## Documentação e recursos adicionais

* [Documentação de extensão do Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): documentação completa específica para a extensão do Adobe Analytics no Adobe Experience Platform Launch.
* [Introdução ao Launch](https://docs.adobelaunch.com/getting-started): documentação completa do Launch, incluindo um guia de introdução mais detalhado.
* [Canal do Adobe Experience Platform Launch no YouTube](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&amp;shelf_id=0&amp;sort=dd): saiba como usar o Launch por meio de vídeos

## Próximas etapas

[Implante a implementação do Analytics no ambiente de desenvolvimento](deploy-dev.md): faça com que o código do Analytics funcione em um ambiente de teste.
