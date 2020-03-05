---
description: O Analytics e o Audience Manager usam segmentos. Entretanto, um segmento do Analytics não exatamente a mesma coisa que um segmento do Audience Manager. Tais diferenças contribuem, em parte, com as discrepâncias que você verá em seus relatórios do Analytics e do Audience Manager. Como resultado, é importante e útil entender essas diferenças ao começar a trabalhar com segmentos em ambas as soluções.
title: Entender os segmentos no Analytics e no Audience Manager
uuid: 13f7d1d7-6a3f-42f1-822e-8d3523999efa
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Entender os segmentos no Analytics e no Audience Manager

O Analytics e o Audience Manager usam segmentos. Entretanto, um segmento do Analytics não exatamente a mesma coisa que um segmento do Audience Manager. Tais diferenças contribuem, em parte, com as discrepâncias que você verá em seus relatórios do Analytics e do Audience Manager. Como resultado, é importante e útil entender essas diferenças ao começar a trabalhar com segmentos em ambas as soluções.

## Segmentos do Audience Manager {#section_417DC4B5648547778A27E42CE1D09900}

Um segmento do Audience Manager é um grupo de visitantes (IDs de usuário) qualificados para um conjunto de características unidas por regras lógicas. Há quatro critérios que determinam se um visitante (ID de usuário) é parte de um segmento no Audience Manager:

* Regras definidas nos próprios segmentos e as características que constituem cada segmento. Essas regras definem as condições que uma ID de usuário tem que atender ou exibir para qualificar-se para um segmento.
* Modelagem algorítmica. Usuários que qualificam-se para um segmento específico podem ser qualificados para outros segmentos com base no modelo e na análise algorítmica.
* Intervalos de Time-to-live (TTL). A associação de segmento pode expirar depois de um intervalo definido, ou continuar por um tempo indeterminado.
* Recentidade e frequência. Definir quando e como os usuários têm uma interação (realização de característica) pode ajudar a criar segmentos com base no nível verdadeiro (ou inferido) de interesse em um site, uma sessão ou criação em particular.

A associação de segmento do Audience Manager é fluida. Os usuários podem entrar ou sair de um segmento dependendo de sua qualificação para os critérios do segmento no momento atual. Isso significa que a população de um segmento do Audience Manager pode aumentar ou diminuir ao longo do tempo.

Um segmento do Audience Manager é denotado como um público-alvo no Analytics.

Para obter mais informações, consulte [Dados de características e de preenchimento de segmentos no Construtor de segmentos](https://docs.adobe.com/content/help/pt-BR/audience-manager/user-guide/features/segments/segment-builder-data.html) e [Sinais, Características e segmentos](https://docs.adobe.com/content/help/pt-BR/audience-manager/user-guide/reference/signal-trait-segment.html).

## Segmentos do Analytics {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Um segmento do Analytics é um mecanismo de filtragem para dados em seus relatórios. A filtragem pode ocorrer no nível do visitante, da visita ou da ocorrência, em vez de somente no nível do visitante como ocorre no Audience Manager. Há vários fatores importantes a serem considerados ao comparar um segmento do Analytics a um segmento do Audience Manager:

* Segmentos do Analytics operam em um conjunto de dados diferente em relação a segmentos do Audience Manager. Durante a coleta de dados, o Analytics aplica várias etapas diferentes de pós-processamento aos dados. Tais etapas não estão disponíveis no Audience Manager. Dentre as etapas de pós-processamento, podem estar a persistência de eVar, regras de processamento, pesquisas (localização geográfica, dispositivo móvel), VISTA, entre outros. O Audience Manager recebe dados pré-processados por meio do encaminhamento pelo lado do servidor (ou por DIL).

   Discrepâncias comuns entre dados ocorrem ao comparar segmentos com base em dimensões que nunca expiram no Analytics, à mesma dimensão no Audience Manager. Por exemplo, listVars ou eVars de merchandising que nunca expiram.

   Por exemplo, se eVar = blue e estiver definida para nunca expirar no Analytics, qualquer segmento no Analytics com o critério “eVar = blue” sempre incluirá esse visitante. Já no Audience Manager, esse mesmo visitante pode ser excluído de um segmento definido de maneira semelhante, depois de um certo período de tempo.

* Segmentos do Analytics apresentam mais recursos em comparação a segmentos do AAM. Segmentos do Audience Manager sempre são avaliados no nível do visitante. Segmentos do Analytics podem ser definidos no nível de um visitante, de uma visita ou de uma ocorrência (ou em uma combinação desses três níveis). Além disso, o Analytics suporta recursos avançados de segmentação que o Audience Manager não suporta, como a segmentação sequencial.
* Conforme mencionado anteriormente, visitantes do Audience Manager podem participar ou sair de um segmento, dependendo de sua qualificação para os critérios do segmento no momento atual.

   Contrariamente, no Analytics, visitantes podem ser incluídos ou excluídos de um segmento com base no intervalo de datas do relatório. Por exemplo, suponhamos que um único visitante fez uma compra no mês anterior. No AAM, esse visitante seria incluído em um segmento “comprador”, independentemente do intervalo de datas. No Analytics, um relatório baseado nesse mês não incluiria o visitante no segmento. Entretanto, um relatório com base nesse mês e no mês anterior incluiria o visitante no segmento.

Consulte o [Guia de segmentação do Analytics](https://marketing.adobe.com/resources/help/pt_BR/analytics/segment/) para obter mais informações.
