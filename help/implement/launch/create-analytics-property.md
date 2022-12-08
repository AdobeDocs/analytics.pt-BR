---
title: Criar uma propriedade do Analytics em tags
description: Crie um espaço para personalizar como os dados são coletados, usando tags.
feature: Launch Implementation
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 92%

---

# Criar uma propriedade de tag do Adobe Analytics

As tags na Adobe Experience Platform permitem integrar soluções da Experience Cloud em seu site (incluindo o Analytics). Esta página descreve especificamente como um administrador de tags pode configurar uma implementação básica do Adobe Analytics corretamente.

## Pré-requisitos

[Criar um conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): criar um silo para que os dados do Analytics sejam coletados..

## Criar uma propriedade de tag e instalar extensões essenciais

As propriedades são contêineres abrangentes que você usa para gerenciar tags. As extensões permitem instalar tags específicas do produto e configurá-las.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Nova propriedade]**.
1. Dê um nome à Propriedade, como o título do site, e insira o domínio em que você pretende implementar o Analytics. Clique em **[!UICONTROL Salvar]**.
1. Clique na propriedade de tag recém-criada para inserir as configurações.
1. Clique na guia **[!UICONTROL Extensões]** e, em seguida, clique em **[!UICONTROL Catálogo]**.
1. Localize &quot;Serviço da Experience Cloud ID&quot; e clique em **[!UICONTROL Instalar]**.
1. Todas as configurações, incluindo a Experience Cloud Organization ID, já devem ser preenchidas. Clique em **[!UICONTROL Salvar]**.
1. De volta ao catálogo de extensões, localize o Adobe Analytics e clique em **[!UICONTROL Instalar]**.

Veja a documentação completa para o [Extensão do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=pt-BR) para obter informações mais detalhadas.

## Criar elementos de dados do Adobe Analytics

Os elementos de dados são referências a partes específicas do site para coletar valores de variável.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade da tag que pretende implementar no site.
1. Clique na guia **[!UICONTROL Elementos de dados]** e, em seguida, clique em **[!UICONTROL Adicionar elemento de dados]**.
1. Atribua ao elemento de dados as seguintes configurações:

   * Nome: nome da página
   * Extensão: principal
   * Tipo de elemento de dados: variável JavaScript
   * Nome da variável JavaScript: `window.document.title`

      >[!NOTE]
      >
      >Esse valor serve como exemplo para ajudar a começar. Se sua empresa definir um valor melhor para o nome da página, como um valor de camada de dados, você pode inseri-lo aqui.
   * Limpar texto marcado
   * Duração do armazenamento: Nenhum
1. Clique em **[!UICONTROL Salvar]**.

## Criar regras para o Adobe Analytics

As regras mapeiam os elementos de dados para os valores de variáveis do Analytics e determinam quando esses valores são enviados para os servidores da Adobe.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade da tag que pretende implementar no site.
1. Clique no botão **[!UICONTROL Regras]** e, em seguida, clique em **[!UICONTROL Adicionar regra]**. Nomeie-o `Global Rule`.
1. Clique em **[!UICONTROL Adicionar]** ao lado dos eventos e insira as seguintes configurações:
   * Extensão: principal
   * Tipo de evento: biblioteca carregada (início da página)
   * Nome: principal - biblioteca carregada (início da página)
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

## Próximas etapas

[Implante a implementação do Analytics no ambiente de desenvolvimento](deploy-dev.md): faça com que o código do Analytics funcione em um ambiente de teste.
