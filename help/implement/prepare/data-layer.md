---
title: Criar uma camada de dados
description: Saiba o que é uma camada de dados na implementação do Analytics e como ela pode ser usada para mapear variáveis no Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 571192e27972f2bc15912481f9a578427e1c1cfb
workflow-type: tm+mt
source-wordcount: '468'
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
   * **Se estiver utilizando o SDK da Web**: mapeie os objetos da camada de dados desejados para os campos XDM desejados no Adobe Experience Platform Edge. Consulte [Mapeamento de variáveis do Analytics](../aep-edge/variable-mapping.md) para determinar o mapeamento da camada de dados desejado.
   * **Se estiver utilizando a extensão do Analytics**: crie elementos de dados em Tags, na Coleção de dados da Adobe Experience Platform, e atribua-os aos objetos da camada de dados desejados. Em seguida, na extensão do Analytics, atribua cada elemento de dados à variável adequada do Analytics.

## Especificações

A Adobe recomenda a utilização da variável [Camada de dados do cliente Adobe](https://github.com/adobe/adobe-client-data-layer/wiki) para implementações novas ou reestruturadas.

Sua organização pode usar outras especificações de camada de dados, como a [Camada de dados digitais da experiência do cliente](https://www.w3.org/2013/12/ceddl-201312.pdf), ou mesmo outra especificação personalizada. Alinhar a uma camada de dados consistente que atenda às necessidades de sua organização é o mais importante.

As camadas de dados são extensíveis; se você tiver requisitos específicos da organização, poderá incluir objetos na camada de dados para acomodar essas necessidades.

## Configuração de valores da camada de dados

As camadas de dados normalmente são geradas no lado do servidor, referenciando os mesmos objetos usados para criar o conteúdo do site. Estabeleça a camada de dados do site com base nos requisitos de rastreamento definidos no [documento de design de solução](solution-design.md) da organização.

## Próximas etapas

[Mapear objetos de camada de dados para elementos de dados](../launch/layer-to-elements.md): use a camada de dados do site no Adobe Experience Platform.
