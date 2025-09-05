---
title: Análise entre dispositivos
description: Saiba como alterar seus dados focados em dispositivos para focados em pessoas compilando os dados do dispositivo.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 59%

---

# Análise entre dispositivos

{{available-existing-customers}}

A Análise entre dispositivos (CDA) é um recurso que transforma a análise de uma visualização centrada em dispositivos em uma visualização centrada em pessoas. Como resultado, os analistas podem entender o comportamento do usuário que passa pelos navegadores, dispositivos ou aplicativos. A Adobe comporta dois fluxos de trabalho abrangentes para vincular dados do dispositivo:

* [**Compilação em campo**](field-based-stitching.md): opção de compilação recomendada porque ela usa apenas a correspondência determinística para vincular dispositivos.
A compilação em campo permite escolher uma variável do Analytics como base para a compilação entre dispositivos em um conjunto de relatórios virtual.

* [**Gráfico de dispositivos**](device-graph.md): o Cross-Device Analytics se comunica com um gráfico privado para compilar dispositivos.

Com o CDA, você pode responder a perguntas como:

* Quantas pessoas interagem com a minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu levar em conta as jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?

Quando os dispositivos são compilados, a persistência variável é transferida entre os dispositivos. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra o aplicativo móvel, instala e eventualmente realiza uma compra pelo dispositivo móvel. Com o Análise entre dispositivos, é possível atribuir a receita no dispositivo móvel ao anúncio em que ele clicou no computador desktop.

O Microsoft Azure é usado para a Análise entre dispositivos. A Adobe usa o Azure para armazenar os dados de gráficos de dispositivos e realizar a compilação entre dispositivos. Dessa forma, os dados do Adobe Analytics são transmitidos de um lado para o outro, entre o centro de processamento de dados da Adobe e as instâncias provisionadas da Adobe do Microsoft Azure.

Consulte a [página Análise entre dispositivos do Spark](https://express.adobe.com/page/8ZpjsX6Lp5XTM/) para saber mais sobre os recursos e as funções do Análise entre dispositivos.

## Pré-requisitos

O uso do Cross-Device Analytics requer os métodos [Compilação em campo](field-based-stitching.md) e [Gráfico de dispositivos](device-graph.md), e ambos têm pré-requisitos específicos.

* Um contrato deve ser assinado com a Adobe incluindo o Adobe Analytics Ultimate.
* Sua organização escolhe em quais conjuntos de relatórios habilitar o CDA. A Adobe recomenda conjuntos de relatórios que contenham dados entre dispositivos, ou seja, dados de vários tipos de dispositivos/navegadores/aplicativos. Algumas organizações se referem a esse conceito como um conjunto de relatórios &quot;global&quot;, embora o Cross-Device Analytics não precise ser rigorosamente global de uma perspectiva geográfica.

## Limitações

O Análise entre dispositivos é um recurso inovador e robusto, mas tem limitações na forma de uso. Os métodos de [Compilação em campo](field-based-stitching.md) e [Gráfico de dispositivos](device-graph.md) também têm limitações específicas.

* O Cross-Device Analytics só está disponível por meio do Analysis Workspace.
* O Análise entre dispositivos não funciona em conjuntos de relatórios, nem combina dados de vários conjuntos de relatórios.
* Os conjuntos de relatórios do Adobe Analytics não podem mapear para mais de uma ID de organização. Como o Cross-Device Analytics compila dispositivos em um conjunto de relatórios específico, o Cross-Device Analytics não pode ser usado para compilar dados em várias IDs de organização.
* O Cross-Device Analytics usa um pipeline de processamento complexo, com vários componentes dependentes. Esse pipeline é executado em paralelo com o fluxo de trabalho básico de relatórios do Analytics. Você pode esperar uma incompatibilidade de dados de aproximadamente 1% para o número total de ocorrências entre o conjunto de relatórios original e o conjunto de relatórios virtual do Cross-Device Analytics.
* O Análise entre dispositivos usa um conjunto de relatórios virtual e um processamento de tempo de relatório, que têm suas próprias limitações. Por exemplo, no momento, eles não são compatíveis com as variáveis de canais de marketing. Consulte [Conjuntos de relatórios virtuais](/help/components/vrs/vrs-about.md) e [Processamento de tempo de relatório](/help/components/vrs/vrs-report-time-processing.md) para obter mais informações sobre essas limitações.
* O Gráfico privado aproveita as mesmas sincronizações de ID que as sincronizações de ID usadas pelo recurso [Atributos do cliente](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) encontrado na Experience Cloud e na Adobe Analytics. No entanto, os conjuntos de relatórios virtuais do Cross-Device Analytics (com base no gráfico privado ou na compilação em campo) não são compatíveis com o restante da funcionalidade de Atributos do cliente. Em outras palavras, as dimensões baseadas em atributos do cliente não estão disponíveis para uso com os conjuntos de relatórios virtuais do Cross-Device Analytics.
* No momento, o Cross-Device Analytics não é compatível com o A4T.
* Não há suporte para a API 1.4. Os conectores do Power BI e do Report Builder dependem da API 1.4 e, portanto, não são compatíveis com o CDA.
* O monitoramento ativo do processo de compilação do Cross-Device Analytics pelo Adobe está limitado apenas aos conjuntos de relatórios de produção.
* O Cross-Device Analytics não é compatível com a [API de reparo de dados](https://developer.adobe.com/analytics-apis/docs/2.0/) do Adobe Analytics
* Os dados históricos no conjunto de relatórios virtual são alterados com base no reconhecimento e na compilação de dispositivos pela Adobe. Os dados no conjunto de relatórios de origem não são alterados.
* Os dados compilados obedecem uma latência de 8 a 12 horas.
* Os dados do histórico de mapeamento de um determinado dispositivo são armazenados por até um ano.
* Se um dispositivo atingir um número muito alto de entradas do histórico de mapeamento em um ano, o histórico de mapeamento será truncado. O limite exato depende da opção de compilação usada.
