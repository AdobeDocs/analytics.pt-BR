---
title: Gráfico de dispositivos
description: Entenda os pré-requisitos e as limitações da costura de dados usando o gráfico de dispositivos.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 60%

---

# Gráfico de dispositivos

O Cross-Device Analytics pode usar o Gráfico privado para compilar dados. O Gráfico privado é um repositório de IDs de dispositivos com hash específicas da sua organização. O CDA se comunica regularmente com o gráfico do dispositivo para vincular dispositivos.

## Pré-requisitos específicos do gráfico de dispositivos

Se você pretende implementar o Cross-Device Analytics usando o método de gráfico de dispositivo, as seguintes etapas são obrigatórias. Trabalhe com as equipes em sua organização e com a equipe de conta da Adobe para atender a todos os itens a seguir.

>[!WARNING]
>
>O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Todos os pré-requisitos estão listados na [página de visão geral](overview.md).
* Sua organização deve usar o [Gráfico privado do Serviço de Identidade da Adobe Experience Platform](https://business.adobe.com/products/experience-platform/identity-service.html). Consulte também a [Página inicial](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=pt-BR) no guia do usuário do Serviço de identidade.
* Sua implementação deve usar a versão mais recente do Serviço de ID de Experience Cloud (ECID). Consulte a [Página inicial](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR) no guia do usuário do Serviço de ID. Provavelmente, a maioria das implementações que usam [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR) na Adobe Experience Platform já tem o Serviço de ID implantado.
* Sua implementação deve chamar a função `setCustomerIDs` (ou SDK equivalente) sempre que um indivíduo puder ser identificado, como quando um usuário se conecta ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Consulte [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=pt-BR) no guia do usuário do Serviço de ID.

## Limitações específicas ao gráfico de dispositivos

* As IDs herdadas do Analytics não são compatíveis. Somente os visitantes com Experience Cloud IDs são compilados.
* Se sua organização usar o Gráfico privado, novos dispositivos levarão até 24 horas para serem compilados.
* Os gráficos de dispositivos de terceiros não são compatíveis.

## Próximas etapas

Assim que sua organização atender a todos os requisitos e entender as limitações, você poderá iniciar a [Configuração do Cross-Device Analytics](setup.md).
