---
description: Tempo de processamento de relatórios é uma configuração de conjunto de relatórios virtual que permite o processamento de dados de forma não destrutiva e retroativa.
title: Processamento de tempo do relatório
role: Admin
solution: Analytics
feature: VRS
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 68%

---

# Processamento de tempo do relatório

[!UICONTROL Processamento de tempo do relatório] é uma configuração de conjunto de relatórios virtual que permite que os dados no Analysis Workspace sejam processados de forma não destrutiva e retroativa.

[!UICONTROL O Processamento de tempo de relatório] afeta somente os dados no conjunto de relatórios virtual e não afeta nenhum dado ou coleta de dados no conjunto de relatórios base. A diferença entre o [!UICONTROL Processamento de tempo de relatório] e o processamento tradicional do Analytics é melhor entendida por meio do seguinte diagrama:

![Pipeline de processamento tradicional](assets/google1.jpg)

Durante o processamento de dados do Analytics, os dados fluem do pipeline de coleta de dados para uma etapa de pré-processamento, que prepara os dados para os relatórios. Esta etapa de pré-processamento aplica a lógica de expiração de visita e a lógica de persistência de eVar (entre outras coisas) aos dados conforme são coletados. A principal desvantagem deste modelo de pré-processamento é que ele exige que as configurações sejam feitas antes da coleta dos dados. Isso significa que qualquer alteração nas configurações de pré-processamento se aplica somente aos novos dados a partir desse momento. Isso será um problema se os dados chegarem fora de ordem ou se as configurações estiverem incorretas.

[!UICONTROL O Processamento de tempo de relatório] é uma maneira fundamentalmente diferente de processar os dados do Analytics para a geração de relatórios. Em vez de predeterminar a lógica de processamento antes da coleta de dados, o Analytics ignora o conjunto de dados durante a etapa de pré-processamento e aplica essa lógica sempre que um relatório é executado:

![Pipeline de processamento de tempo do relatório](assets/google2.jpg)

Esta arquitetura de processamento permite opções de relatórios muito mais flexíveis. Por exemplo, você pode alterar o período de tempo limite da visita para qualquer período desejado de forma não destrutiva e essas alterações são refletidas na persistência do eVar e nos contêineres do segmento para o período de geração de relatório completo. Além disso, você pode criar qualquer número de conjuntos de relatórios virtuais, cada um com diferentes opções de Processamento de tempo do relatório com base em um mesmo conjunto de relatórios base, sem alterar os dados no conjunto de relatórios base.

O [!UICONTROL Processamento de tempo do relatório] também permite que o Analytics evite que ocorrências em segundo plano iniciem novas visitas e que o [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=pt-BR) inicie uma nova visita sempre que um evento de inicialização de aplicativo for acionado.

## Opções de configuração

As seguintes opções de configuração estão disponíveis atualmente para conjuntos de relatórios virtuais com o Processamento de tempo do relatório ativado:

* **[!UICONTROL Tempo limite de visita]:** a configuração de tempo limite de visita define a quantidade de inatividade que um visitante único deve ter antes que uma nova visita seja iniciada automaticamente. O padrão é 30 minutos. Por exemplo, se o tempo limite de visita for definido para 15 minutos, um novo grupo de visitas será criado para cada sequência de ocorrências coletadas, separadas por 15 minutos de inatividade. Essa configuração afeta não apenas a sua visita, mas também a forma como os contêineres do segmento de visitas são avaliados e a lógica de expiração de visita para todas as eVars que expiram na visita. Diminuir o tempo limite de visita provavelmente aumentará o número total de visitas em seus relatórios, ao passo que aumentar o tempo limite provavelmente diminuirá o número total de visitas em seus relatórios.
* **[!UICONTROL Configurações de visita de aplicativos móveis]:** para conjuntos de relatórios que contenham dados gerados por aplicativos móveis por meio dos [SDKs móveis da Adobe Mobile](https://experienceleague.adobe.com/docs/mobile.html?lang=pt-BR), estão disponíveis configurações de visita adicionais. Essas configurações não são destrutivas e afetam somente as ocorrências que foram coletadas por meio dos SDKs móveis. Essas configurações não têm impacto nos dados coletados fora do SDK móvel.
* **[!UICONTROL Impedir ocorrências em segundo plano de iniciar uma nova visita]:** as ocorrências em segundo plano são coletadas pelos SDKs móveis quando o aplicativo está em segundo plano.
* **[!UICONTROL Iniciar uma nova visita a cada inicialização do aplicativo]:** além do tempo limite de visita, é possível forçar o início de uma visita sempre que um evento de inicialização de aplicativo for gravado dos SDKs móveis, independentemente da janela de inatividade. Essa configuração afeta a métrica de visitas e o contêiner do segmento de visitas, bem como a lógica de expiração de visita nas eVars.
* **[!UICONTROL Iniciar nova visita com evento]:** uma nova sessão começa quando um evento é acionado, independentemente de uma sessão ter ultrapassado o tempo limite. A sessão recentemente criada inclui o evento que a iniciou. Além disso, é possível usar vários eventos para começar uma sessão e uma nova sessão é acionada se qualquer um desses eventos for observado nos dados. Esta configuração afetará a contagem de visitas, o contêiner de segmentação de visitas e a lógica de expiração de visitas nas eVars.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Iniciando uma nova visita com o evento](https://video.tv.adobe.com/v/23129?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



## Limitações do Processamento de tempo de relatório

O Processamento de tempo de relatório não suporta todas as métricas e dimensões disponíveis nos relatórios tradicionais do Analytics. Os conjuntos de relatórios virtuais que utilizam o Processamento de tempo de relatório só podem ser acessados no Analysis Workspace e não estão acessíveis no Data Warehouse, no Report Builder, nos Feeds de dados ou na API de relatórios.

Além disso, o Processamento de tempo do relatório somente processa os dados provenientes do intervalo de datas do relatório (referido como “janela de datas” abaixo). Isso significa que os valores de eVar configurados como “nunca expiram” para um visitante antes do intervalo de datas do relatório não persistem nas janelas de relatórios e não aparecem nos relatórios. Isso também significa que as medições de lealdade do cliente são baseadas exclusivamente nos dados presentes no intervalo de datas do relatório e não em todo o histórico antes do intervalo de datas do relatório.

As seguintes dimensões e métricas não são compatíveis com o Processamento de tempo do relatório:

* **Analytics for Target**
* **Analytics para dimensões/métricas do Advertising Cloud**
* **eVars do contador**
* [**Dias Antes da Primeira Compra**](/help/components/dimensions/days-before-first-purchase.md)
* [**Dias desde a última compra**](/help/components/dimensions/days-since-last-purchase.md)
* [**Dias desde a última visita**](/help/components/dimensions/days-since-last-visit.md)
* **Página de entrada original**
* **eVars de alocação linear**
* **Listar Vars**
* [**Dimensões de Canais de marketing**](/help/components/dimensions/marketing-channel.md)
* [**Domínio referenciador original**](/help/components/dimensions/original-referring-domain.md)
* [**Frequência de retorno**](/help/components/dimensions/return-frequency.md)
* [**Acesso único**](/help/components/metrics/single-access.md)
* **Fontes de Dados de ID de Transação**
* [**Número da visita**](/help/components/dimensions/visit-number.md)

## Dimensões e métricas afetadas

Veja abaixo uma lista das dimensões e métricas afetadas, dependendo das configurações de Processamento de tempo do relatório selecionadas:

* Se &quot;Impedir ocorrências em segundo plano de iniciar uma nova visita&quot; estiver ativado, as seguintes alterações ocorrerão. Consulte [Sessões sensíveis ao contexto](vrs-mobile-visit-processing.md) para obter mais informações.
   * [**Rejeições**](/help/components/metrics/bounces.md) / [**Taxa de Rejeição:**](/help/components/metrics/bounce-rate.md) ocorrências em segundo plano que não são seguidas por uma ocorrência em primeiro plano não são consideradas uma rejeição e não contribuem para a taxa de rejeição.
   * [**Tempo gasto em segundos por visita:**](/help/components/metrics/time-spent-per-visit.md) somente visitas que incluem ocorrências em primeiro plano contribuem para essa métrica.
   * **Tempo gasto por visita:** somente visitas que incluem ocorrências em primeiro plano contribuem para essa métrica.
   * [**Métrica de entrada**](/help/components/metrics/entries.md) / [**Métrica de saída:**](/help/components/metrics/exits.md) somente entradas e saídas de visitas com ocorrências em primeiro plano aparecem nesta dimensão.
   * [**Dimensão de entrada**](/help/components/dimensions/entry-dimensions.md) / [**Dimensões de saída:**](/help/components/dimensions/exit-dimensions.md) somente entradas e saídas de visitas com ocorrências em primeiro plano aparecem nesta dimensão.
   * [**Métrica de visitantes únicos:**](/help/components/metrics/unique-visitors.md) visitantes únicos não incluem visitantes que tiveram somente ocorrências em segundo plano no intervalo de datas do relatório.
* [**Visitas:**](/help/components/metrics/visits.md) as visitas refletem as configurações do conjunto de relatórios virtual, que podem ser diferentes do conjunto de relatório base.
* **Eventos serializados com IDs de evento:** os eventos que usam Serialização de eventos com uma ID de evento só são desduplicados para eventos que ocorrem dentro do intervalo de datas do relatório para um visitante. Esses eventos não são desduplicados em todas as datas ou visitantes globalmente, devido à janela de datas Processamento de tempo do relatório.
* **Compras** / [**Receita**](/help/components/metrics/revenue.md) / [**Pedidos**](/help/components/metrics/orders.md) / [**Unidades:**](/help/components/metrics/units.md) quando a ID de compra é usada, essas métricas são apenas desduplicadas para as IDs de compra duplicadas que ocorrem dentro do intervalo de datas do relatório para um visitante, em vez de em todas as datas ou visitantes globalmente, devido à janela de datas do Processamento de tempo de relatório.
* [**eVars que não sejam de merchandising**](/help/components/dimensions/evar.md) / **eVars reservadas:** Os valores definidos em um eVar persistem apenas se o valor tiver sido definido dentro do intervalo de datas do relatório devido à janela de datas do Processamento de tempo de relatório. Além disso, as expirações baseadas em tempo podem expirar uma hora antes ou depois se a persistência abranger uma mudança de horário de verão.
* [**eVars de merchandising**](/help/components/dimensions/evar-merchandising.md) / **eVars reservadas:** Consulte acima. Além disso, para a sintaxe de conversão, onde a vinculação é definida como “qualquer evento”, é usado “qualquer ocorrência” no lugar disso.
* [**Tipo de ocorrência:**](/help/components/dimensions/hit-type.md) essa dimensão especifica se uma ocorrência está em primeiro ou em segundo plano.
* **Dimension com (tráfego baixo) ou &quot;Únicos excedidos&quot;:** O item de linha (tráfego baixo) é determinado de forma um pouco diferente ao usar o Processamento de tempo de relatório, e não há garantia de correspondência com o que é observado nos relatórios no Conjunto de relatórios base. Não há garantias de que os itens de linha de Dimension que não fazem parte do Tráfego baixo representem 100% dos dados desse item de linha. Essas diferenças podem se tornar mais pronunciadas quanto maior o número de valores únicos existentes em uma dimensão.
