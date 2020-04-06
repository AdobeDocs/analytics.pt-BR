---
description: Tempo de processamento de relatórios é uma configuração de conjunto de relatórios virtual que permite o processamento de dados de forma não destrutiva e retroativa.
title: Processamento de tempo do relatório
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Processamento de tempo do relatório

Tempo de processamento de relatórios é uma configuração de conjunto de relatórios virtual que permite o processamento de dados de forma não destrutiva e retroativa.

>[!NOTE] O Relatório de processamento de tempo está disponível apenas para a Analysis Workspace.

O Processamento de tempo do relatório afeta apenas os dados no conjunto de relatórios virtual e não afeta nenhum dado ou coleta de dados no conjunto de relatórios base. A diferença entre o Processamento de tempo do relatório e o processamento tradicional do Analytics é melhor entendida usando o seguinte diagrama:

![Google1](assets/google1.jpg)

Durante o processamento de dados do Analytics, os dados fluem pelo pipeline de coleta de dados e para uma etapa de pré-processamento, que prepara os dados para o relatórios. Essa etapa de pré-processamento aplica a lógica de expiração da visita e a lógica de persistência da eVar (entre outras coisas) aos dados conforme são coletados. A principal desvantagem desse modelo de pré-processamento é que ele requer que qualquer configuração seja feita antecipadamente antes da coleta dos dados. Isso significa que qualquer alteração nas configurações de pré-processamento se aplica somente aos novos dados a partir desse momento. Isso é problemático se os dados chegarem fora de ordem ou se as configurações estiverem incorretas.

O Processamento de tempo do relatório é uma maneira fundamentalmente diferente de processar os dados do Analytics para o relatórios. Em vez de predeterminar a lógica de processamento antes da coleta de dados, o Analytics ignora o conjunto de dados durante a etapa de pré-processamento e aplica essa lógica sempre que um relatório é executado:

![Google2](assets/google2.jpg)

Essa arquitetura de processamento permite opções de relatórios muito mais flexíveis. Por exemplo, você pode alterar o tempo limite de visita para qualquer duração desejada de forma não destrutiva e essas alterações são refletidas na persistência de eVar e nos container de segmento retroativamente como se você tivesse aplicado essas configurações antes de os dados serem coletados. Além disso, você pode criar qualquer número de conjuntos de relatórios virtuais, cada um com diferentes opções de Processamento de tempo de relatório com base no mesmo conjunto de relatórios base, sem alterar os dados no conjunto de relatórios base.

O Processamento de tempo do relatório também permite que o Analytics evite que ocorrências em segundo plano iniciem novas visitas e permite que o SDK [](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) móvel informe ao relatórios uma nova visita sempre que um evento de inicialização de aplicativo for acionado.

As seguintes opções de configuração estão disponíveis atualmente para conjuntos de relatórios virtuais com Processamento de tempo de relatório ativado:

* **Tempo limite de visita:** a configuração de tempo limite de visita define a quantidade de inatividade que um visitante exclusivo deve ter antes que uma nova visita seja iniciada automaticamente. O padrão é 30 minutos. Por exemplo, se você definir o tempo limite de visita para 15 minutos, um novo agrupamento de visita será criado para cada sequência de ocorrências coletadas, separadas por 15 minutos de inatividade. Essa configuração afeta não apenas a contagem de visitas, mas também a forma como os container de segmento de visitas são avaliados e a lógica de expiração de visitas para qualquer eVars que expiram na visita. Diminuir o tempo limite da visita provavelmente aumentará o número total de visitas em seu relatórios, enquanto o aumento do tempo limite provavelmente diminuirá o número total de visitas em seu relatórios.
* **Configurações de visita de aplicativos móveis**: para conjuntos de relatórios que contenham dados gerados por aplicativos móveis por meio dos [SDKs do Adobe Mobile](https://www.adobe.io/apis/cloudplatform/mobile.html), estão disponíveis configurações de visita adicionais. Essas configurações não são destrutivas e afetam somente as ocorrências que foram coletadas pelos SDKs móveis. Essas configurações não afetam os dados coletados fora do SDK móvel.
* **Impedir ocorrências em segundo plano de iniciar uma nova visita:** as ocorrências em segundo plano são coletadas pelos SDKs móveis quando o aplicativo está em segundo plano.
* **Iniciar uma nova visita a cada inicialização do aplicativo:** além do tempo limite de visita, você pode forçar o início de uma visita sempre que um evento de inicialização de aplicativo for gravado dos SDKs móveis, independentemente da janela de inatividade. Essa configuração afeta a métrica de visitas e o contêiner do segmento de visitas, bem como a lógica de expiração de visita nas eVars.
* **Iniciar nova visita com evento:** uma nova sessão começa quando um evento é acionado, independente do fato de uma sessão ter ultrapassado o tempo limite. A sessão recém-criada inclui o evento que a iniciou. Além disso, você pode usar vários eventos para start de uma sessão e uma nova sessão é acionada se algum desses eventos for observado nos dados. Essa configuração afetará a contagem de visitas, o container de segmentação de visitas e a lógica de expiração de visita nas eVars.

O Processamento de tempo do relatório não suporta todas as métricas e dimensões disponíveis nos relatórios tradicionais do Analytics. Os conjuntos de relatórios virtuais que utilizam o Processamento de tempo do relatório só podem ser acessados na Analysis Workspace e não estão acessíveis no [!UICONTROL Reports & Analytics], na Ad Hoc Analysis, no Data Warehouse, no Report Builder, nos Feeds de dados ou na API de relatórios.

Além disso, o Processamento de tempo do relatório processa somente os dados que vêm do intervalo de datas do relatórios (conhecido como &quot;janela de datas&quot; abaixo). Isso significa que os valores de eVar definidos como &quot;nunca expiram&quot; para um visitante antes do intervalo de datas do relatórios não persistem nas janelas do relatórios e não aparecem nos relatórios. Isso também significa que as medidas de fidelidade do cliente se baseiam exclusivamente nos dados presentes no intervalo de datas do relatórios e não em todo o histórico anterior ao intervalo de datas do relatórios.

Abaixo está uma lista de métricas e dimensões que não são suportadas no momento ao usar o Processamento de tempo do relatório:

* **Analytics para Target:** não compatível no momento. O suporte futuro está planejado.
* **Métricas/dimensões reservadas do Analytics para Advertising Cloud:** não compatível no momento. O suporte futuro está planejado.
* **Métrica de acesso único:** não compatível permanentemente.
* **List Vars:** não compatível no momento. O suporte futuro está planejado.
* **Counter eVars**: não compatível permanentemente.
* **Variáveis de canais de marketing:** não compatível no momento. O suporte futuro está planejado.
* **Dimensão Dias desde a última compra:** devido à natureza da janela de datas Processamento de tempo do relatório, essa dimensão não é compatível.
* **Dimensão Dias antes da primeira compra:** devido à natureza da janela de datas Processamento de tempo do relatório, essa dimensão não é compatível.
* **Retornar dimensão de frequência:** devido à natureza da janela de datas do Processamento de tempo de relatório, essa dimensão não é suportada. Uma abordagem alternativa usando a métrica de contagem de visitas em um segmento é possível, ou usando a métrica de visitas em um relatório de histograma.
* **Dimensão Dias desde a última visita:** devido à natureza da janela de datas Processamento de tempo do relatório, essa dimensão não é compatível.
* **Inserir dimensão de original da página:** devido à natureza da janela de datas do Processamento de tempo de relatório, essa dimensão não é suportada.
* **eVars de alocação linear:** não compatível no momento. O suporte futuro está planejado.
* **Dimensão Domínio de referência original:** não compatível no momento. O suporte futuro está planejado.
* **Número de visitas:** devido à natureza da janela de datas do Processamento de tempo de relatório, essa métrica não é suportada. Como alternativa em aplicativos móveis, você pode usar uma métrica calculada, incluindo visitantes/visitas com a métrica Instalação do aplicativo para identificar novos visitantes ou visitas.
* **Fontes de dados de ID de transação:** não compatível no momento. O suporte futuro está planejado.

Abaixo está uma lista de dimensões e métricas afetadas, dependendo das configurações de Processamento de tempo do relatório selecionadas:

* Se &quot;Impedir ocorrências em segundo plano de iniciar uma nova visita&quot; estiver ativado, as seguintes alterações ocorrerão. Consulte [Sessões sensíveis ao contexto](vrs-mobile-visit-processing.md) para obter mais informações.
   * **Rejeições/taxa de rejeição:** as ocorrências em segundo plano que não são seguidas por uma ocorrência em primeiro plano não são consideradas uma rejeição e não contribuem para a taxa de rejeição.
   * **Tempo gasto em segundos por visita:** somente visitas que incluem ocorrências em primeiro plano contribuem para essa métrica.
   * **Tempo gasto por visita:** somente visitas que incluem ocorrências em primeiro plano contribuem para essa métrica.
   * **Dimensões e métricas de entrada/saída:** somente entradas e saídas de visitas com ocorrências em primeiro plano aparecem nessa dimensão.
   * **Métrica de visitantes únicos:** visitantes únicos não incluem visitantes que tiveram somente ocorrências em segundo plano no intervalo de datas do relatório.
* **Visitas:** as visitas refletem as configurações do conjunto de relatórios virtual, que podem ser diferentes do conjunto de relatório base.
* **Eventos serializados com IDs de evento:** os eventos que usam Serialização de eventos com uma ID de evento só são desduplicados para eventos que ocorrem dentro do intervalo de datas do relatório para um visitante. Esses eventos não são desduplicados em todas as datas ou visitantes globalmente, devido à janela de datas Processamento de tempo do relatório.
* **Compras/receita/pedidos/unidades:** quando a ID de compra é usada, essas métricas são apenas desduplicadas para as IDs de compra duplicadas que ocorrem dentro do intervalo de datas do relatório para um visitante, em vez de em todas as datas ou visitantes globalmente, devido à janela de datas do Processamento de tempo de relatório.
* **eVars não relacionadas ao merchandising/eVars reservadas:** os valores definidos em uma eVar persistem apenas se o valor tiver sido definido dentro do intervalo de datas do relatório devido à janela de data do processamento de tempo de relatório. Além disso, as expirações baseadas em tempo podem expirar uma hora antes ou depois se a persistência abranger uma mudança de horário de verão.
* **eVars de merchandising/eVars reservadas:** consulte acima. Além disso, para a sintaxe de conversão, onde a vinculação é definida como “qualquer evento”, é usado “qualquer ocorrência” no lugar disso.
* **Tipo de ocorrência:** essa dimensão especifica se uma ocorrência está em primeiro ou em segundo plano.
