---
description: O Analytics e o Audience Manager usam segmentos. No entanto, um segmento do Analytics não é exatamente a mesma coisa que um segmento do Audience Manager. Essas diferenças contribuem, em parte, para as discrepâncias que você verá nos relatórios do Analytics e do Audience Manager. Como resultado, é importante e útil tentar entender essas diferenças ao começar a trabalhar com segmentos em ambas as soluções.
title: Entender os segmentos no Analytics e no Audience Manager
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 12%

---

# Entender os segmentos no Analytics e no Audience Manager

O Analytics e o Audience Manager usam segmentos. No entanto, um segmento do Analytics não é exatamente a mesma coisa que um segmento do Audience Manager. Essas diferenças contribuem, em parte, para as discrepâncias que você verá nos relatórios do Analytics e do Audience Manager. Como resultado, é importante e útil tentar entender essas diferenças ao começar a trabalhar com segmentos em ambas as soluções.

## Segmentos do Audience Manager {#aam-segments}

Um segmento do Audience Manager é um grupo de visitantes (IDs de usuário) que se qualificam para um conjunto de características definidas unidas por regras lógicas. Há quatro critérios que determinam se um visitante (ID de usuário) faz parte de um segmento no Audience Manager:

* Regras definidas nos próprios segmentos e nas características que compõem cada segmento. Essas regras definem as condições que uma ID de usuário deve atender ou exibir para se qualificar para um segmento.
* Modelagem algorítmica. Usuários que qualificam-se para um segmento específico podem ser qualificados para outros segmentos com base no modelo e na análise algorítmica.
* Intervalos TTL (vida útil). A associação de segmento pode expirar após um intervalo definido ou continuar indefinidamente.
* Recenticidade e frequência. Definir quando e com que frequência os usuários têm uma interação (realização de características) pode ajudar a criar segmentos com base no nível real (ou percebido) de interesse em um site, seção ou criativo específico.

A associação do segmento do Audience Manager é fluida. Os usuários podem entrar ou sair de um segmento, dependendo se se qualificam para os critérios de segmento no momento atual. Isso significa que a população de um segmento do Audience Manager pode aumentar ou diminuir com o tempo.

Um segmento do Audience Manager é indicado como um público no Analytics.

Para obter mais informações, consulte [Dados de população de características e segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=pt-BR) e [Sinais, características e segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=pt-BR).

## Segmentos do Analytics {#analytics-segments}

Um segmento do Analytics é um mecanismo de filtragem para dados em seus relatórios. A filtragem pode ocorrer no nível do visitante, da visita ou da ocorrência, em vez de somente no nível do visitante como ocorre no Audience Manager. Há vários fatores importantes a serem considerados ao comparar um segmento do Analytics com um segmento do Audience Manager:

* Os segmentos do Analytics operam em um conjunto de dados diferente dos segmentos do Audience Manager. Durante a coleta de dados, o Analytics aplica várias etapas diferentes de pós-processamento aos dados que não estão disponíveis para o Audience Manager. O pós-processamento pode incluir persistência do eVar, regras de processamento, pesquisas (localização geográfica, dispositivo móvel), VISTA e muitas outras. O Audience Manager recebe dados pré-processados por meio do encaminhamento pelo lado do servidor (ou DIL).

  Discrepâncias de dados comuns ocorrem ao comparar segmentos baseados em dimensões que nunca expiram no Analytics, com a mesma dimensão no Audience Manager. Por exemplo, listVars ou eVars de merchandising que nunca expiram.

  Por exemplo, se eVar = blue e estiver definida para nunca expirar no Analytics, qualquer segmento no Analytics com o critério “eVar = blue” sempre incluirá esse visitante. Já no Audience Manager, esse visitante pode sair de um segmento definido de forma semelhante após um período definido.

* Segmentos do Analytics têm mais recursos do que segmentos do Adobe Audience Manager. Os segmentos do Audience Manager são sempre avaliados no nível do visitante. Os segmentos do Analytics podem ser definidos em um nível de visitante, visita ou ocorrência (ou em uma combinação desses níveis). Além disso, o Analytics oferece suporte a recursos avançados de segmentação que a Audience Manager não oferece, como a segmentação sequencial.

* Como mencionado anteriormente, os visitantes do Audience Manager podem entrar ou sair de um segmento, dependendo se se qualificam para os critérios do segmento no momento atual.

  Por outro lado, no Analytics, os visitantes serão incluídos ou excluídos de um segmento com base no intervalo de datas do relatório. Por exemplo, um único visitante fez uma compra no mês passado. No Adobe Audience Manager, esse visitante seria incluído em um segmento &quot;comprador&quot;, independentemente do intervalo de datas. No Analytics, um relatório baseado neste mês não incluiria o visitante no segmento. No entanto, um relatório com base neste mês e no último mês incluiria o visitante no segmento.

Consulte o [Guia de Segmentação do Analytics](/help/components/segmentation/seg-home.md) para obter mais informações.
