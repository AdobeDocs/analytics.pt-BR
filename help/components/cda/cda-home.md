---
title: Análise entre dispositivos
description: O Analytics de dispositivos cruzados altera seus dados de estar centrado no dispositivo para focalizar os dados do dispositivo em conjunto.
translation-type: tm+mt
source-git-commit: 40d8ecae1ac7e0a1df4a2df17f5104bee6ecf336

---


# Análise entre dispositivos

> [!NOTE] A documentação do Análise entre dispositivos está sujeita a alterações à medida que o recurso é desenvolvido. Consulte regularmente para atualizações.

O Analytics entre dispositivos é um recurso que transforma o Analytics de uma exibição centrada no dispositivo para uma visualização centrada em dispositivo. Esse recurso usa o Gráfico de identidade do Adobe Experience Platform Identity Service Co-op ou o Gráfico privado para identificar quais dispositivos pertencem a indivíduos e agrupam eles juntos. Como resultado, os analistas podem entender o comportamento do usuário que cruza navegadores, dispositivos ou aplicativos. Usando a CDA, você pode responder a perguntas como:

* Quantas pessoas interagem com minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu levar em conta as jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?

Quando os dispositivos são empilhados, a persistência da variável é transmitida em todos os dispositivos. Por exemplo, um usuário visita site pela primeira vez através de um anúncio em seu computador desktop. Esse usuário encontra seu aplicativo móvel, o instala e, eventualmente, efetua uma compra em seu dispositivo móvel. Com o Analytics entre dispositivos, a receita pode ser atribuída ao anúncio que ele clicou em seu computador desktop.

Consulte [o IQ da jornada: Página de Spark entre dispositivos](http://adobe.ly/aacda) para saber mais sobre os recursos e recursos do Analytics entre dispositivos.

## Pré-requisitos

A partir de setembro de 2019, o Análise entre dispositivos requer o seguinte. Trabalhe com equipes em sua organização e seu Gerente de contas da Adobe para garantir que você cumpre todos os procedimentos a seguir.

> [!IMPORTANT] A falha em cumprir todos os pré-requisitos pode resultar na incapacidade de ativar a Análise entre dispositivos ou resultados insuficientes ao unir dados.

* Os dados de sua organização devem estar no centro de dados do Noroeste do Pacífico da Adobe. O suporte para centros de dados em outras regiões do mundo está planejado.
* Entre em contato com o Gerente de conta de sua organização para estabelecer estes pontos chave:
   * Um contrato deve ser assinado com a Adobe que inclui o Adobe Analytics Ultimate.
   * Sua organização deve usar o Gráfico de identidade do Adobe Experience Platform Identity Service ou Gráfico privado. Consulte a Página [inicial](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) no guia do usuário do Device Co-op.
   * Sua organização deve concordar em permitir que a Adobe processe e armazene dados do Analytics nos servidores do Microsoft Azure. A Adobe usa o Azure para armazenar dados de gráfico de dispositivos e executar o agrupamento de dispositivos. Assim, os dados do Adobe Analytics são passados entre o centro de processamento de dados da Adobe e a presença da Adobe no Microsoft Azure.
* O Análise entre dispositivos é ativado com base em conjunto de relatórios. Seu conjunto de relatórios exige o seguinte:
   * No momento, um conjunto de relatórios não pode ter mais de 100 milhões de ocorrências por dia. Esse limite aumentará nos próximos meses.
   * Um conjunto de relatórios «cross-device», que significa que todos os dados em dispositivos devem ser enviados para o mesmo conjunto de relatórios. Algumas organizações se referem a isso como um conjunto de relatórios "global", embora a CDA não precise ser global exclusiva de uma perspectiva geográfica. O Análise de dispositivos cruzados não funciona em conjuntos de relatórios.
* Sua implementação deve atender aos seguintes requisitos:
   * A versão mais recente do serviço da Experience Cloud ID deve ser implantada. Consulte a Página [inicial](https://docs.adobe.com/content/help/en/id-service/using/home.html) no guia do usuário do serviço de identidade da Experience Cloud. A maioria das implementações que usam o Adobe Experience Platform Launch provavelmente já tem o ECID implantado.
   * Chame a `setCustomerIDs` função sempre que um indivíduo puder ser identificado, como quando um usuário fizer logon ou abrir um e-mail. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Consulte [setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) no guia do usuário do serviço de identidade da Experience Cloud.

## Limitações

O Análise entre dispositivos é um recurso inovador e robusto, mas tem limitações de como pode ser usado.

* A CDA só está disponível por meio da Analysis Workspace.
* Não é possível fazer a divisão de uma organização por organizações IMS. Certifique-se de que você não está usando várias Organizações IMS na implementação.
* A divisão não pode ocorrer nos conjuntos de relatórios, conforme descrito em Pré-requisitos acima.
* No momento, a CDA não é compatível com Atributos do cliente. Os Atributos do cliente não podem ser usados para criar um conjunto de relatórios virtual CDA, em segmentos de dispositivos cruzados ou para relatórios em um projeto da Analysis Workspace baseado em um conjunto de relatórios virtuais da CDA.
* CDA exige um Gráfico de cooperativa ou Gráfico privado. Gráficos de dispositivo de terceiros não são suportados.
* Não há suporte para a ID do Analytics herdada. Apenas os visitantes com a Experience Cloud ID estão empilhados.
* O Atendimento ao cliente ainda não oferece suporte completo a esse recurso. O fórum [do Analytics entre dispositivos](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) pode ser usado para suporte a esse recurso, que inclui participação ativa e direta dos Gerentes de produtos da Adobe.
* O Análise entre dispositivos usa um conjunto de relatórios virtual e um processamento de tempo de relatório, que tem suas próprias limitações. Consulte [Conjuntos de relatórios virtuais](../vrs/vrs-about.md) e [processamento de tempo do relatório](../vrs/vrs-report-time-processing.md) para obter mais informações sobre essas limitações.
* Os novos dispositivos que visitam site podem levar até duas semanas para serem processados pelo Gráfico de cooperação ou Gráfico privado. O nível de agrupamento na CDA para as duas semanas mais recentes geralmente é menor do que para intervalos de datas mais antigos que duas semanas. A Adobe pretende melhorar o Adobe Experience Platform Identity Service para unir novos dispositivos em tempo real no futuro.
* Os dados históricos no conjunto de relatórios virtuais mudam com base na Adobe que reconhece e empilhando os dispositivos. Os dados no conjunto de relatórios de origem não são alterados.

Depois que a organização atender a todos os requisitos e compreender as limitações, você poderá começar [a definir a análise entre dispositivos](cda-setup.md).
