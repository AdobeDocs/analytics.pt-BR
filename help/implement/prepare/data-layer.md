---
title: Criar uma camada de dados
description: Saiba o que é uma camada de dados na implementação do Analytics e como ela pode ser usada para mapear variáveis no Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 476
ht-degree: 100%

---

# Criar uma camada de dados

Uma camada de dados é uma estrutura de objetos JavaScript no site que contém os valores de variável utilizados na implementação do Analytics. Isso permite maior controle e manutenção simplificada ao atribuir valores às variáveis do Analytics.

## Pré-requisitos

[Criar um documento de design de solução](solution-design.md) - É importante que sua organização se alinhe aos requisitos de rastreamento. Esteja preparado com um documento de design de solução antes de entrar em contato com as equipes de desenvolvimento em sua organização.

## Fluxo de trabalho

A implementação do Adobe Analytics usando uma camada de dados geralmente segue estas etapas:

1. **Trabalhar com a equipe de desenvolvimento do site para implementar uma camada de dados**: a equipe de desenvolvimento do site é responsável principalmente por garantir que o objeto da camada de dados seja preenchido com valores corretos. Consulte esta página com a equipe de desenvolvimento do site para garantir que as expectativas estejam alinhadas entre as equipes.

   >[!NOTE]
   >
   >As especificações recomendadas da camada de dados da Adobe são opcionais. Se já tiver uma camada de dados, ou optar por não seguir as especificações da Adobe, certifique-se de que sua organização se alinha a qual especificação seguir.

1. **Validar a camada de dados usando um console do navegador**: depois que uma camada de dados é criada, você pode validar se ela está funcionando usando qualquer console de desenvolvedor do navegador. Abra o console do desenvolvedor na maioria dos navegadores usando a tecla `F12`. Um exemplo de valor de variável seria `adobeDataLayer.page.title`.
1. **Usar a coleção de dados da Adobe Experience Platform para mapear objetos de camada de dados para elementos de dados**: essa etapa varia de acordo com o método de implementação de sua organização:
   * **Se estiver utilizando o SDK da Web**: mapeie os objetos da camada de dados desejados para os campos XDM desejados no Adobe Experience Platform Edge. Consulte [Mapeamento de variáveis XDM do Analytics](../aep-edge/xdm-var-mapping.md) para determinar o mapeamento de camada de dados desejado.
   * **Se estiver utilizando a extensão do Analytics**: crie elementos de dados em Tags, na Coleção de dados da Adobe Experience Platform, e atribua-os aos objetos da camada de dados desejados. Em seguida, na extensão do Analytics, atribua cada elemento de dados à variável adequada do Analytics.

## Especificações

A Adobe recomenda a utilização da variável [Camada de dados do cliente Adobe](https://github.com/adobe/adobe-client-data-layer/wiki) para implementações novas ou reestruturadas.

Sua organização pode usar outras especificações de camada de dados, como a [Camada de dados digitais da experiência do cliente](https://www.w3.org/2013/12/ceddl-201312.pdf), ou mesmo outra especificação personalizada. Alinhar a uma camada de dados consistente que atenda às necessidades de sua organização é o mais importante.

As camadas de dados são extensíveis; se você tiver requisitos específicos da organização, poderá incluir objetos na camada de dados para acomodar essas necessidades.

## Configuração de valores da camada de dados

As camadas de dados normalmente são geradas no lado do servidor, referenciando os mesmos objetos usados para criar o conteúdo do site. Estabeleça a camada de dados do site com base nos requisitos de rastreamento definidos no [documento de design de solução](solution-design.md) da organização.

## Próximas etapas

[Mapear objetos de camada de dados para elementos de dados](../launch/layer-to-elements.md): use a camada de dados do site no Adobe Experience Platform.
