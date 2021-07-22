---
title: Criar uma propriedade do Analytics nas tags
description: Crie um espaço para personalizar como os dados são coletados, usando tags .
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 59%

---

# Criar uma propriedade de tag do Analytics

As tags no Adobe Experience Platform permitem integrar soluções do Experience Cloud em seu site (incluindo o Analytics). Esta página descreve especificamente como um administrador de tags pode configurar uma implementação básica do Adobe Analytics corretamente.

>[!NOTE]
>A Adobe Experience Platform Launch foi reformulada como um conjunto de tecnologias de coleta de dados no Experience Platform. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o seguinte [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obter uma referência consolidada das alterações de terminologia.

## Pré-requisitos

[Criar um conjunto de relatórios](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): criar um silo para que os dados do Analytics sejam coletados..

## Criar uma propriedade de tag e instalar extensões essenciais

As propriedades são contêineres abrangentes que você usa para gerenciar tags. As extensões permitem instalar tags específicas do produto e configurá-las.

1. Vá para [experience.adobe.com](https://experience.adobe.com) e faça logon quando solicitado.
1. Selecione **[!UICONTROL Launch / Data Collection]**.
1. Clique em **[!UICONTROL Ir para Iniciar/Coleta de dados]** e selecione **[!UICONTROL Tags]**.
1. Clique em **[!UICONTROL Nova propriedade]**.
1. Dê um nome à Propriedade, como o título do site, e insira o domínio em que você pretende implementar o Analytics. Clique em **[!UICONTROL Salvar]**.
1. Clique na propriedade de tag recém-criada para inserir as configurações.
1. Clique na guia **[!UICONTROL Extensões]** e, em seguida, clique em **[!UICONTROL Catálogo]**.
1. Localize o Serviço de identidade e clique em **[!UICONTROL Instalar]**.
1. Todas as configurações, incluindo a Experience Cloud Organization ID, já devem ser preenchidas. Clique em **[!UICONTROL Salvar]**.
1. De volta ao catálogo de extensões, localize o Adobe Analytics e clique em **[!UICONTROL Instalar]**.

## Criar elementos de dados do Adobe Analytics

Os elementos de dados são referências a partes específicas do site para coletar valores de variável.

1. Vá para [experience.adobe.com](https://experience.adobe.com) e faça logon quando solicitado.
1. Selecione **[!UICONTROL Launch / Data Collection]**.
1. Clique em **[!UICONTROL Ir para Iniciar/Coleta de dados]** e selecione **[!UICONTROL Tags]**.
1. Clique na propriedade de tag que você pretende implementar em seu site.
1. Clique na guia **[!UICONTROL Elementos de dados]** e, em seguida, clique em **[!UICONTROL Criar novo elemento de dados]**.
1. Atribua ao elemento de dados as seguintes configurações:

   * Nome: nome da página
   * Extensão: principal
   * Tipo de elemento de dados: variável JavaScript
   * Caminho para a variável: `window.document.title`

      >[!NOTE]
      >
      >Este é um exemplo de valor para ajudar a começar. Se sua empresa definir um valor melhor para o nome da página, como um valor de camada de dados, você pode inseri-lo aqui.
   * Limpar texto marcado
   * Duração: Pageview
1. Clique em **[!UICONTROL Salvar]**.

## Criar regras para o Adobe Analytics

As regras mapeiam os elementos de dados para os valores de variáveis do Analytics e determinam quando esses valores são enviados para os servidores da Adobe.

1. Vá para [experience.adobe.com](https://experience.adobe.com) e faça logon quando solicitado.
1. Selecione **[!UICONTROL Launch / Data Collection]**.
1. Clique em **[!UICONTROL Ir para Iniciar/Coleta de dados]** e selecione **[!UICONTROL Tags]**.
1. Clique na propriedade de tag que você pretende implementar em seu site.
1. Clique em **[!UICONTROL Criar nova regra]** e a nomeie como `Global Rule`.
1. Clique em **[!UICONTROL Adicionar]** ao lado dos eventos e insira as seguintes configurações:
   * Extensão: principal
   * Tipo de evento: biblioteca carregada (início da página)
   * Nome: principal - biblioteca carregada (início da página)
   * Ordem: 50
1. Clique em **[!UICONTROL Manter alterações]**.
1. Em **[!UICONTROL Ações]**, clique em **[!UICONTROL Adicionar]** e insira as seguintes configurações:
   * Extensão: Adobe Analytics
   * Tipo de ação: definir variáveis
   * Nome da página: clique no ícone de contêiner e selecione o elemento de dados `Page Name`
   * Campanha: parâmetro de consulta com um valor de `cid`
1. Clique em **[!UICONTROL Manter alterações]**.
1. Clique no sinal de Mais ao lado das ações para adicionar outra ação e insira as seguintes configurações:
   * Extensão: Adobe Analytics
   * Tipo de ação: enviar beacon
   * Nome: Adobe Analytics - enviar beacon
   * Rastreamento: s.t()
1. Clique em **[!UICONTROL Manter alterações]**.
1. Verifique se o evento e as duas ações estão configurados e clique em **[!UICONTROL Salvar]**.

## Documentação e recursos adicionais

* [Documentação](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en) da extensão do Adobe Analytics: Documentação completa específica para a extensão do Adobe Analytics nas tags.
* [Introdução às tags](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en): Documentação completa para tags, incluindo um guia de introdução mais detalhado
* [Canal](https://experienceleague.adobe.com?tag=Launch&amp;lang=pt-BR#recommended/solutions/experience-platform) Adobe Experience Platform Launch: Saiba como usar tags por meio de vídeos

## Próximas etapas

[Implante a implementação do Analytics no ambiente de desenvolvimento](deploy-dev.md): faça com que o código do Analytics funcione em um ambiente de teste.
