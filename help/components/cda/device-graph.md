---
title: Gráfico de dispositivos
description: Entenda os pré-requisitos e as limitações da costura de dados usando o gráfico de dispositivos.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 96%

---

# Gráfico de dispositivos

O Cross-Device Analytics fornece dois métodos distintos para compilar dados. Este método usa o gráfico cooperativo ou o gráfico privado do Adobe Experience Platform Identity Service para unir os dados. O CDA se comunica regularmente com o gráfico do dispositivo para vincular dispositivos.

## Diferenças entre o gráfico cooperativo e o gráfico privado

A Adobe oferece dois tipos de gráficos de dispositivos como parte do serviço de ID:

* **Gráfico cooperativo**: um repositório de IDs de dispositivos com hash que qualquer cliente pode contribuir e fazer referência. Como esse tipo de gráfico de dispositivo é colaborativo, geralmente corresponde a mais dispositivos do que um gráfico privado.
* **Gráfico privado**: um repositório de IDs de dispositivo com hash que somente a sua organização faz referência.

## Pré-requisitos específicos do gráfico de dispositivos

Se você pretende implementar o Cross-Device Analytics usando o método de gráfico de dispositivo, as seguintes etapas são obrigatórias. Trabalhe com as equipes em sua organização e com seu Gerente de conta da Adobe para atender a todos os itens a seguir.

>[!IMPORTANT]
>
>O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Todos os pré-requisitos estão listados na [página de visão geral](overview.md).
* Sua organização deve usar o Gráfico cooperativo ou Gráfico privado do Serviço de Identidade da Adobe Experience Platform. Consulte a [Página inicial](https://experienceleague.adobe.com/docs/device-co-op/using/home.html?lang=pt-BR) no guia do usuário do cooperativo do dispositivo.
* Sua implementação deve usar a versão mais recente do serviço da Experience Cloud ID. Consulte a [Página inicial](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR) no guia do usuário do Serviço de identidade da Experience Cloud. A maioria das implementações que usam tags no Adobe Experience Platform provavelmente já implantou a ECID.
* Sua implementação deve chamar a função `setCustomerIDs` (ou SDK equivalente) sempre que um indivíduo puder ser identificado, como quando um usuário se conecta ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Consulte [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=pt-BR) no guia do usuário do Serviço de identidade da Experience Cloud.

## Limitações específicas ao gráfico de dispositivos

* As IDs herdadas do Analytics não são compatíveis. Somente os visitantes com Experience Cloud IDs são compilados.
* Se sua organização usar o Gráfico privado, novos dispositivos levarão até 24 horas para serem compilados.
* Se sua organização usar o Gráfico cooperativo, novos dispositivos que visitam seu site podem levar até duas semanas para serem unidos. Normalmente, o nível de compilação no CDA das duas últimas semanas é menor do que para os intervalos de datas com mais de duas semanas.
* Os gráficos de dispositivos de terceiros não são compatíveis.

## Próximas etapas

Assim que sua organização atender a todos os requisitos e entender as limitações, você poderá iniciar a [Configuração do Cross-Device Analytics](setup.md).
