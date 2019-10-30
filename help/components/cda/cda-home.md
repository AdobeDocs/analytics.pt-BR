---
title: Análise entre dispositivos
description: O Cross-Device Analytics transforma seus dados em dispositivos focados em pessoas, unindo dados de dispositivos.
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Análise entre dispositivos

> [!NOTE] A documentação do Cross-Device Analytics está sujeita a alterações à medida que o recurso for sendo desenvolvido. Verifique regularmente se há atualizações.

O Cross-Device Analytics é um recurso que transforma o Analytics de uma exibição centrada no dispositivo para uma exibição centrada na pessoa. Esse recurso usa o Gráfico cooperativo do Adobe Experience Platform Identity Service ou o Gráfico privado para identificar quais dispositivos pertencem a indivíduos e agrupá-los. Como resultado, os analistas podem entender o comportamento do usuário que cruza navegadores, dispositivos ou aplicativos. Usando a CDA, você pode responder a perguntas como:

* Quantas pessoas interagem com minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu levar em conta as jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?

Quando os dispositivos são costurados, a persistência variável é transportada pelos dispositivos. Por exemplo, um usuário visita seu site pela primeira vez através de um anúncio em seu computador desktop. Esse usuário encontra seu aplicativo móvel, o instala e eventualmente realiza uma compra em seu dispositivo móvel. Com o Cross-Device Analytics, a receita pode ser atribuída ao anúncio que clicaram em seu computador desktop.

Consulte QI [da jornada: Página](http://adobe.ly/aacda) Flash do Analytics entre dispositivos para saber mais sobre os recursos e os recursos do Cross-Device Analytics.

## Pré-requisitos

A partir de setembro de 2019, o Cross-Device Analytics exige o seguinte. Trabalhe com equipes em sua organização e com seu Gerente de contas da Adobe para garantir que você atenda a todos os seguintes itens.

> [!IMPORTANT] Se todos os pré-requisitos não forem atendidos, a incapacidade de habilitar o Cross-Device Analytics ou os resultados serão insatisfatórios ao corrigir os dados.

* Os dados de sua organização devem residir no data center do Noroeste do Pacífico da Adobe. Está previsto o apoio a data centers em outras regiões do mundo.
* Entre em contato com o Gerente de conta de sua organização para estabelecer estes pontos chave:
   * Um contrato deve ser assinado com a Adobe que inclui o Adobe Analytics Ultimate.
   * Sua organização deve usar o Gráfico cooperativo do Adobe Experience Platform Identity Service ou o Gráfico privado. Consulte a Página [inicial](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) no guia do usuário do Device Co-op.
   * Sua organização deve concordar em permitir que a Adobe processe e armazene dados do Analytics nos servidores do Microsoft Azure. A Adobe usa o Azure para armazenar dados de gráficos de dispositivos e executar a identificação de dispositivos. Dessa forma, os dados do Adobe Analytics são transmitidos de um lado para o outro entre o data center da Adobe e a presença da Adobe no Microsoft Azure.
* A Análise entre dispositivos é ativada com base em conjunto de relatórios. Os conjuntos de relatórios que foram habilitados para CDA exigem o seguinte:
   * O conjunto de relatórios não pode ter mais de 100 milhões de ocorrências por dia. Este limiar aumentará nos próximos meses.
   * A Adobe recomenda que um conjunto de relatórios contenha dados entre dispositivos, ou seja, dados de vários tipos de dispositivos (Web, aplicativo etc). Algumas organizações se referem a esse conceito como um conjunto de relatórios "global", embora o CDA não precise ser estritamente global de uma perspectiva geográfica. A Análise entre dispositivos não funciona em conjuntos de relatórios, nem combina dados de vários conjuntos de relatórios.
* Sua implementação deve atender aos seguintes requisitos:
   * A versão mais recente do Serviço da Experience Cloud ID deve ser implantada. Consulte a Página [inicial](https://docs.adobe.com/content/help/en/id-service/using/home.html) no guia do usuário do Serviço de identidade da Experience Cloud. A maioria das implementações que usam o Adobe Experience Platform Launch provavelmente já têm a ECID implantada.
   * Chame a `setCustomerIDs` função sempre que um indivíduo puder ser identificado, como quando um usuário faz logon ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Consulte [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) no guia do usuário do Serviço de identidade da Experience Cloud.

## Limitações

O Cross-Device Analytics é um recurso inovador e robusto, mas tem limitações em como pode ser usado.

* O CDA só está disponível na Analysis Workspace.
* Não é possível executar a configuração em conjuntos de relatórios, conforme descrito nos pré-requisitos acima.
* Os conjuntos de relatórios do Adobe Analytics não podem mapear para mais de uma organização IMS. Como o CDA costuma os dispositivos em um determinado conjunto de relatórios, o CDA não pode ser usado para unir dados em várias organizações IMS.
* No momento, o CDA não é compatível com os Atributos do cliente. Os Atributos do cliente não podem ser usados para criar um conjunto de relatórios virtual CDA, em segmentos entre dispositivos ou para relatórios em um projeto de espaço de trabalho da Análise baseado em um conjunto de relatórios virtual CDA.
* O CDA requer o Gráfico cooperativo ou o Gráfico privado. Gráficos de dispositivos de terceiros não são suportados.
* IDs herdadas do Analytics não são compatíveis. Somente os visitantes com Experience Cloud IDs são agrupados.
* O Atendimento ao cliente ainda não oferece suporte total a esse recurso. O fórum [de Análises de](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) vários dispositivos pode ser usado para oferecer suporte a esse recurso, que inclui o envolvimento ativo e direto dos Gerentes de produtos da Adobe.
* O Cross-Device Analytics usa um conjunto de relatórios virtual e um processamento de tempo de relatório, que têm suas próprias limitações. Consulte Conjuntos [de relatórios virtuais e processamento](../vrs/vrs-about.md) de tempo de [](../vrs/vrs-report-time-processing.md) relatório para obter mais informações sobre essas limitações.
* Os novos dispositivos que visitam site podem levar até duas semanas para serem processados pelo Gráfico cooperativo ou Gráfico privado. O nível de sutura no CDA das duas últimas semanas é geralmente menor do que para intervalos de datas com mais de duas semanas. A Adobe pretende melhorar o Adobe Experience Platform Identity Service para agrupar novos dispositivos em tempo real no futuro.
* Os dados históricos no conjunto de relatórios virtual são alterados com base no reconhecimento e agrupamento de dispositivos pela Adobe. Os dados no conjunto de relatórios de origem não são alterados.

Assim que sua organização atender a todos os requisitos e entender as limitações, você poderá iniciar a [Configuração do Cross-Device Analytics](cda-setup.md).
