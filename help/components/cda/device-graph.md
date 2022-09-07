---
title: Gráfico de dispositivos
description: Entenda os pré-requisitos e as limitações da costura de dados usando o gráfico de dispositivos.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: be913fb9bae7954864b180490364c275c7bf7f15
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 92%

---

# Gráfico de dispositivos

O Cross-Device Analytics pode usar o Gráfico privado para unir dados. O Gráfico privado é um repositório de IDs de dispositivos com hash que são específicas da sua organização. O CDA se comunica regularmente com o gráfico do dispositivo para vincular dispositivos.

## Pré-requisitos específicos do gráfico de dispositivos

Se você pretende implementar o Cross-Device Analytics usando o método de gráfico de dispositivo, as seguintes etapas são obrigatórias. Trabalhe com as equipes em sua organização e com seu Gerente de conta da Adobe para atender a todos os itens a seguir.

>[!WARNING]
>
>O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Todos os pré-requisitos estão listados na [página de visão geral](overview.md).
* Sua organização deve usar o Gráfico cooperativo ou Gráfico privado do Serviço de Identidade da Adobe Experience Platform. Consulte a [Página inicial](https://experienceleague.adobe.com/docs/device-co-op/using/home.html?lang=pt-BR) no guia do usuário do cooperativo do dispositivo.
* Sua implementação deve usar a versão mais recente do serviço da Experience Cloud ID. Consulte a [Página inicial](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR) no guia do usuário do Serviço de identidade da Experience Cloud. Provavelmente, a maioria das implementações que usam tags na Adobe Experience Platform já implantou a ECID.
* Sua implementação deve chamar a função `setCustomerIDs` (ou SDK equivalente) sempre que um indivíduo puder ser identificado, como quando um usuário se conecta ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Consulte [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=pt-BR) no guia do usuário do Serviço de identidade da Experience Cloud.

## Limitações específicas ao gráfico de dispositivos

* As IDs herdadas do Analytics não são compatíveis. Somente os visitantes com Experience Cloud IDs são compilados.
* Se sua organização usar o Gráfico privado, novos dispositivos levarão até 24 horas para serem compilados.
* Se sua organização usar o Gráfico cooperativo, novos dispositivos que visitam seu site podem levar até duas semanas para serem unidos. Normalmente, o nível de compilação no CDA das duas últimas semanas é menor do que para os intervalos de datas com mais de duas semanas.
* Os gráficos de dispositivos de terceiros não são compatíveis.

## Próximas etapas

Assim que sua organização atender a todos os requisitos e entender as limitações, você poderá iniciar a [Configuração do Cross-Device Analytics](setup.md).
