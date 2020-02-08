---
title: Análise entre dispositivos
description: O Cross-Device Analytics altera os dados que passam de focados em dispositivos para focados em pessoas, ao compilar os dados do dispositivo.
translation-type: tm+mt
source-git-commit: 98e09f543381d4a4ac9731a24dbabbf36c94d0a5

---


# Análise entre dispositivos

> [!NOTE] A documentação do Cross-Device Analytics está sujeita a alterações à medida que o recurso for sendo desenvolvido. Verifique regularmente se há atualizações.

O Cross-Device Analytics é um recurso que transforma o Analytics de uma exibição centrada no dispositivo para uma exibição centrada na pessoa. Esse recurso usa o Gráfico cooperativo ou o Gráfico privado do Serviço de identidade da do Adobe Experience Platform para identificar quais dispositivos pertencem a indivíduos e os compila juntos. Como resultado, os analistas podem entender o comportamento do usuário que passa pelos navegadores, dispositivos ou aplicativos. Usando a CDA, você pode responder a perguntas como:

* Quantas pessoas interagem com minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu levar em conta as jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?

Quando os dispositivos são compilados, a persistência variável é transferida entre os dispositivos. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra o aplicativo móvel, instala e eventualmente realiza uma compra pelo dispositivo móvel. Com o Cross-Device Analytics, a receita pode ser atribuída ao anúncio em que o usuário clicou no computador desktop.

Consulte a página [Journey IQ: Cross-Device Analytics Spark](http://adobe.ly/aacda) para saber mais sobre os recursos e as funções do Cross-Device Analytics.

## Pré-requisitos

A partir de setembro de 2019, o Cross-Device Analytics exige o seguinte. Trabalhe com as equipes em sua organização e com seu Gerente de conta da Adobe para atender a todos os itens a seguir.

> [!IMPORTANT] O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Os dados de sua organização devem residir no data center da Adobe do noroeste do Pacífico. Está previsto o suporte a data centers em outras regiões do mundo.
* Entre em contato com o Gerente de conta de sua organização para estabelecer estes pontos-chave:
   * Um contrato deve ser assinado com a Adobe incluindo o Adobe Analytics Ultimate.
   * Sua organização deve usar o Gráfico cooperativo ou Gráfico privado do Serviço de Identidade da Adobe Experience Platform. Consulte a [Página inicial](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) no guia do usuário do cooperativo do dispositivo.
   * Sua organização deve concordar em permitir que a Adobe processe e armazene os dados do Analytics nos servidores do Microsoft Azure. A Adobe usa o Azure para armazenar os dados de gráficos de dispositivos e realizar a compilação de dispositivos. Dessa forma, os dados do Adobe Analytics são transmitidos de um lado para o outro, entre o centro de processamento de dados da Adobe e a presença da Adobe no Microsoft Azure.
* O Cross-Device Analytics é ativada com base no conjunto de relatórios. Os conjuntos de relatórios que foram habilitados para CDA exigem o seguinte:
   * O conjunto de relatórios não pode ter mais de 100 milhões de ocorrências por dia. Esse limiar aumentará nos próximos meses.
   * A Adobe recomenda que um conjunto de relatórios contenha dados entre dispositivos, ou seja, dados de vários tipos de dispositivos (Web, aplicativo, etc). Algumas organizações se referem a esse conceito como um conjunto de relatórios &quot;global&quot;, embora o CDA não precise ser rigorosamente global de uma perspectiva geográfica. O Cross-Device Analytics não funciona em conjuntos de relatórios, nem combina dados de vários conjuntos de relatórios.
* Sua implementação deve atender os seguintes requisitos:
   * A versão mais recente do Serviço da Experience Cloud ID deve ser implantada. Consulte a [Página inicial](https://docs.adobe.com/content/help/en/id-service/using/home.html) no guia do usuário do Serviço de identidade da Experience Cloud. Provavelmente, a maioria das implementações que usam o Adobe Experience Platform Launch já implantou a ECID.
   * Chame a função `setCustomerIDs` sempre que um indivíduo puder ser identificado, como quando um usuário se conecta ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Consulte [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) no guia do usuário do Serviço de identidade da Experience Cloud.

## Limitações

O Cross-Device Analytics é um recurso inovador e robusto, mas tem limitações na forma de uso.

* O CDA está disponível somente na Analysis Workspace.
* Não é possível executar a configuração em conjuntos de relatórios, conforme descrito nos pré-requisitos acima.
* Os conjuntos de relatórios do Adobe Analytics não podem mapear para mais de uma organização IMS. Como o CDA compila os dispositivos em um conjunto de relatórios específico, o CDA não pode ser usado para compilar dados em várias organizações IMS.
* No momento, o CDA não é compatível com os Atributos do cliente. Os Atributos do cliente não podem ser usados para criar um conjunto de relatórios virtual do CDA, em segmentos entre dispositivos, ou para relatórios em um projeto da Analysis Workspace baseado em um conjunto de relatórios virtual do CDA.
   > [!TIP] Embora os Atributos do cliente não possam ser usados no CDA, ambos os recursos dependem da `setCustomerIDs` função. Esses dois recursos podem coincidir em conjuntos de relatórios separados (virtuais).
* O CDA requer o Gráfico cooperativo ou o Gráfico privado. Os gráficos de dispositivos de terceiros não são compatíveis.
* As IDs herdadas do Analytics não são compatíveis. Somente os visitantes com Experience Cloud IDs são compilados.
* O Atendimento ao cliente ainda não oferece suporte total a esse recurso. O [fórum do Cross-Device Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) pode ser usado para oferecer suporte a esse recurso, o que inclui o envolvimento ativo e direto dos Gerentes de produto da Adobe.
* O Cross-Device Analytics usa um conjunto de relatórios virtual e um processamento de tempo de relatório, que têm suas próprias limitações. Consulte [Conjuntos de relatórios virtuais](../vrs/vrs-about.md) e [Processamento de tempo de relatório](../vrs/vrs-report-time-processing.md) para obter mais informações sobre essas limitações.
* A API 1.4 não é suportada. Os conectores do Power BI e do Construtor de relatórios dependem da API 1.4 e, portanto, não são compatíveis com o CDA.
* Os novos dispositivos que visitam site podem levar até duas semanas para serem processados pelo Gráfico cooperativo. Normalmente, o nível de compilação no CDA das duas últimas semanas é menor do que para os intervalos de datas com mais de duas semanas. A Adobe pretende melhorar o Serviço de identidade da Adobe Experience Platform para compilar novos dispositivos em tempo real no futuro.
* Os dados históricos no conjunto de relatórios virtual são alterados com base no reconhecimento e na compilação de dispositivos pela Adobe. Os dados no conjunto de relatórios de origem não são alterados.

Assim que sua organização atender a todos os requisitos e entender as limitações, você poderá iniciar a [Configuração do Cross-Device Analytics](cda-setup.md).
