---
title: Gráfico de dispositivos
description: Entenda os pré-requisitos e as limitações da sutura de dados usando o gráfico de dispositivos.
translation-type: tm+mt
source-git-commit: eb2bee26dd58dcff13b4ddf41c6f6ab337d8d374
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 41%

---


# Gráfico de dispositivos

O Analytics entre dispositivos fornece dois métodos distintos para unir dados. Esse método usa o Gráfico cooperativo do Serviço de identidade do Adobe Experience Platform ou o Gráfico privado para unir dados. O CDA se comunica regularmente com o gráfico do dispositivo para vincular dispositivos.

## Diferenças entre o gráfico cooperativo e o gráfico privado

A Adobe oferta dois tipos de gráficos de dispositivos como parte do serviço de ID:

* **Gráfico** cooperativo: Um repositório de IDs de dispositivos com hash que qualquer cliente pode contribuir e fazer referência. Como esse tipo de gráfico de dispositivo é colaborativo, geralmente corresponde a mais dispositivos do que um gráfico privado.
* **Gráfico** privado: Um repositório de IDs de dispositivo com hash que somente a sua organização faz referência.

## Pré-requisitos específicos do gráfico de dispositivos

Se você pretende implementar o Analytics entre dispositivos usando o método de gráfico de dispositivos, as seguintes opções são obrigatórias. Trabalhe com as equipes em sua organização e com seu Gerente de conta da Adobe para atender a todos os itens a seguir.

>[!IMPORTANT] O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Todos os pré-requisitos listados na página [de](overview.md)visão geral.
* Sua organização deve usar o Gráfico cooperativo ou Gráfico privado do Serviço de Identidade da Adobe Experience Platform. Consulte a [Página inicial](https://docs.adobe.com/content/help/pt-BR/device-co-op/using/home.html) no guia do usuário do cooperativo do dispositivo.
* Sua implementação deve usar a versão mais recente do serviço de ID do Experience Cloud. Consulte a [Página inicial](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html) no guia do usuário do Serviço de identidade da Experience Cloud. Provavelmente, a maioria das implementações que usam o Adobe Experience Platform Launch já implantou a ECID.
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Consulte [`setCustomerIDs`](https://docs.adobe.com/content/help/pt-BR/id-service/using/id-service-api/methods/setcustomerids.html) no guia do usuário do Serviço de identidade da Experience Cloud.

## Limitações específicas ao gráfico de dispositivos

* As IDs herdadas do Analytics não são compatíveis. Somente os visitantes com Experience Cloud IDs são compilados.
* Se sua organização usar um Gráfico privado, novos dispositivos levarão até 24 horas para serem costurados.
* Se sua organização usar o Gráfico de cooperação, novos dispositivos que visitam seu site podem levar até duas semanas para serem costurados. Normalmente, o nível de compilação no CDA das duas últimas semanas é menor do que para os intervalos de datas com mais de duas semanas.
* Os gráficos de dispositivos de terceiros não são compatíveis.

## Próximas etapas

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).

