---
title: Criar uma propriedade do Analytics em tags
description: Crie um espaço para personalizar como os dados são coletados, usando tags.
feature: Tags
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/2cZHjGRwvLZPL-jmGLOQpgSXr5Rib8nMeqFWj2cCKAA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 91%

---

# Criar uma propriedade de tag do Adobe Analytics

As tags na Adobe Experience Platform permitem integrar soluções CX Enterprise em seu site (incluindo o Analytics). Esta página descreve especificamente como um administrador de tags pode configurar uma implementação básica do Adobe Analytics corretamente.

## Pré-requisitos

[Criar um conjunto de relatórios](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md): criar um silo para que os dados do Analytics sejam coletados.

## Criar uma propriedade de tag e instalar extensões essenciais

As propriedades são contêineres abrangentes que você usa para gerenciar tags. As extensões permitem instalar tags específicas do produto e configurá-las.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Nova propriedade]**.
1. Dê um nome à Propriedade, como o título do site, e insira o domínio em que você pretende implementar o Analytics. Clique em **[!UICONTROL Salvar]**.
1. Clique na propriedade de tag recém-criada para inserir as configurações.
1. Clique na guia **[!UICONTROL Extensões]** e, em seguida, clique em **[!UICONTROL Catálogo]**.
1. Localize &quot;Serviço da Experience Cloud ID&quot; e clique em **[!UICONTROL Instalar]**.
1. Todas as configurações, incluindo a ID da organização corporativa da CX, já devem ser preenchidas. Clique em **[!UICONTROL Salvar]**.
1. De volta ao catálogo de extensões, localize o Adobe Analytics e clique em **[!UICONTROL Instalar]**.

Veja a documentação completa da [Extensão do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=pt-BR) para obter informações mais detalhadas.

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
   * Duração do armazenamento: nenhum
1. Clique em **[!UICONTROL Salvar]**.

## Criar regras para o Adobe Analytics

As regras mapeiam os elementos de dados para os valores de variáveis do Analytics e determinam quando esses valores são enviados para os servidores da Adobe.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade da tag que pretende implementar no site.
1. Clique na guia **[!UICONTROL Regras]** e, em seguida, clique em **[!UICONTROL Adicionar regra]**. Nomeie-a como `Global Rule`.
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
