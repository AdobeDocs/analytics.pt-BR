---
title: Análise entre dispositivos
description: Altere seus dados de focados em dispositivos para focados em pessoas unindo dados de dispositivos.
translation-type: tm+mt
source-git-commit: eb2bee26dd58dcff13b4ddf41c6f6ab337d8d374
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 72%

---


# Análise entre dispositivos

O Cross-Device Analytics é um recurso que transforma o Analytics de uma exibição centrada no dispositivo para uma exibição centrada na pessoa. Como resultado, os analistas podem entender o comportamento do usuário que passa pelos navegadores, dispositivos ou aplicativos. A Adobe oferece suporte a dois workflows abrangentes para vincular dados do dispositivo:

* [**Arranque **](field-based-stitching.md)baseado em campo: Permite escolher uma variável do Analytics como base para a identificação entre dispositivos em um conjunto de relatórios virtual. Usa a correspondência determinística para vincular dispositivos. A Adobe recomenda usar a sutura baseada em campo para a maioria dos casos de uso determinísticos correspondentes.
* [**Gráfico **](device-graph.md)de dispositivos: O CDA se comunica com um gráfico de dispositivos para unir dispositivos. O gráfico cooperativo usa correspondência determinística e probabística.

Usando o CDA, você pode responder perguntas como:

* Quantas pessoas interagem com a minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu levar em conta as jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?

Quando os dispositivos são compilados, a persistência variável é transferida entre os dispositivos. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra o aplicativo móvel, instala e eventualmente realiza uma compra pelo dispositivo móvel. Com o Cross-Device Analytics, a receita pode ser atribuída ao anúncio em que o usuário clicou no computador desktop.

Com um espírito de parceria e transparência, queremos que nossos clientes estejam cientes de nosso uso do Microsoft Azure em associação com o Cross-Device Analytics. A Adobe usa o Azure para armazenar os dados de gráficos de dispositivos e realizar a compilação entre dispositivos. Dessa forma, os dados do Adobe Analytics são transmitidos de um lado para o outro, entre o centro de processamento de dados da Adobe e as instâncias provisionadas da Adobe do Microsoft Azure.

See the [Journey IQ: Cross-Device Analytics Spark page](http://adobe.ly/aacda) to learn more about the capabilities and features of Cross-Device Analytics.

## Pré-requisitos

O uso do CDA requer todos os itens a seguir. [A sutura](field-based-stitching.md) baseada em campo e os métodos do gráfico [de](device-graph.md) dispositivos também têm seus próprios pré-requisitos específicos.

* Um contrato deve ser assinado com a Adobe incluindo o Adobe Analytics Ultimate.
* O Cross-Device Analytics é ativada com base no conjunto de relatórios. A Adobe recomenda um conjunto de relatórios que contenha dados entre dispositivos, ou seja, dados de vários tipos de dispositivos (Web, aplicativo etc.). Algumas organizações se referem a esse conceito como um conjunto de relatórios &quot;global&quot;, embora o CDA não precise ser rigorosamente global de uma perspectiva geográfica.

## Limitações

O Cross-Device Analytics é um recurso inovador e robusto, mas tem limitações na forma de uso. [A sutura](field-based-stitching.md) baseada em campo e os métodos do gráfico [de](device-graph.md) dispositivos também têm suas próprias limitações específicas.

* O CDA está disponível somente na Analysis Workspace.
* O Cross-Device Analytics não funciona em conjuntos de relatórios, nem combina dados de vários conjuntos de relatórios.
* Os conjuntos de relatórios do Adobe Analytics não podem mapear para mais de uma organização IMS. Como o CDA compila os dispositivos em um conjunto de relatórios específico, o CDA não pode ser usado para compilar dados em várias organizações IMS.
* No momento, o CDA não é compatível com os Atributos do cliente. Esses dois recursos podem coincidir em conjuntos de relatórios virtuais separados que fazem referência ao mesmo conjunto de relatórios de origem.
* O Cross-Device Analytics usa um conjunto de relatórios virtual e um processamento de tempo de relatório, que têm suas próprias limitações. Consulte [Conjuntos de relatórios virtuais](../vrs/vrs-about.md) e [Processamento de tempo de relatório](../vrs/vrs-report-time-processing.md) para obter mais informações sobre essas limitações.
* Não há suporte para a API 1.4. Os conectores do Power BI e do Report Builder dependem da API 1.4 e, portanto, não são compatíveis com o CDA.
* Os dados históricos no conjunto de relatórios virtual são alterados com base no reconhecimento e na compilação de dispositivos pela Adobe. Os dados no conjunto de relatórios de origem não são alterados.
