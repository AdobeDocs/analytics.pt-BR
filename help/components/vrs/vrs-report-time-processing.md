---
description: O processamento de tempo do relatório é uma configuração de conjunto de relatórios virtual que permite que os dados sejam processados de forma não destrutiva e retroativa.
seo-description: O processamento de tempo do relatório é uma configuração de conjunto de relatórios virtual que permite que os dados sejam processados de forma não destrutiva e retroativa.
seo-title: Processamento de tempo do relatório
title: Processamento de tempo do relatório
uuid: 1 a 1 d 82 ea -8 c 93-43 cc -8689-cdcf 59 c 309 b 1
translation-type: tm+mt
source-git-commit: 1e8d5af54ab22311e1c3967979c8bdc982a66d5b

---


# Processamento de tempo do relatório

O processamento de tempo do relatório é uma configuração de conjunto de relatórios virtual que permite que os dados sejam processados de forma não destrutiva e retroativa.

>[!NOTE]
>
>O Processamento de tempo do relatório está disponível somente para a Analysis Workspace.

O Processamento de tempo do relatório somente afeta os dados no conjunto de relatórios virtual e não afeta nenhum dado ou coleta de dados no conjunto de relatórios base. A diferença entre o Processamento de tempo do relatório e o processamento analítico tradicional é melhor entendida usando o seguinte diagrama:

![](assets/google1.jpg)

Durante o processamento de dados do Analytics, os dados fluem do pipeline de coleta de dados para uma etapa de pré-processamento, que prepara os dados para os relatórios. Esta etapa de pré-processamento aplica a lógica de expiração de visita e a lógica de persistência de eVar (entre outras coisas) aos dados conforme são coletados. A principal desvantagem deste modelo de pré-processamento é que ele exige que as configurações sejam feitas antes da coleta dos dados. Isso significa que qualquer alteração nas configurações de pré-processamento se aplica somente aos novos dados a partir desse momento. Isso será um problema se os dados chegarem fora de ordem ou se as configurações estiverem incorretas.

O Processamento de tempo do relatório é uma maneira fundamentalmente diferente de processar os dados do Analytics para a geração de relatórios. Em vez de predeterminar a lógica de processamento antes da coleta de dados, o Analytics ignora o conjunto de dados durante a etapa de pré-processamento e aplica essa lógica sempre que um relatório é executado:

![](assets/google2.jpg)

Esta arquitetura de processamento permite opções de relatórios muito mais flexíveis. Por exemplo, você pode alterar o tempo limite de visita para qualquer duração desejada de forma não destrutiva e essas alterações são refletidas em sua persistência de eVar e nos contêineres dos segmentos retroativamente como se você tivesse aplicado essas configurações antes da coleta dos dados. Além disso, você pode criar qualquer número de conjuntos de relatórios virtuais, cada um com diferentes opções de Processamento de tempo do relatório com base em um mesmo conjunto de relatórios base, sem alterar os dados no conjunto de relatórios base.

O Processamento de tempo do relatório também permite que o Analytics evite que ocorrências em segundo plano iniciem novas visitas e permite que o [SDK móvel](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) informe os relatórios para iniciar uma nova visita sempre que um evento de inicialização de aplicativo for acionado.

As seguintes opções de configuração estão disponíveis atualmente para conjuntos de relatórios virtuais com o Processamento de tempo do relatório ativado:

<table id="table_C086C5FD10A84A1ABC081F5DE28F802D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Tempo limite de visita </p> </td> 
   <td colname="col2"> <p> A configuração de tempo limite de visita define a quantidade de inatividade que um visitante exclusivo deve ter antes que uma nova visita seja iniciada automaticamente. O padrão é 30 minutos. Por exemplo, se o tempo limite de visita for definido para 15 minutos, um novo grupo de visitas será criado para cada sequência de ocorrências coletadas, separadas por 15 minutos de inatividade. Essa configuração afeta não apenas a sua visita, mas também a forma como os contêineres do segmento de visitas são avaliados e a lógica de expiração de visita para todas as eVars que expiram na visita. Diminuir o tempo limite de visita provavelmente aumentará o número total de visitas em seus relatórios, ao passo que aumentar o tempo limite provavelmente diminuirá o número total de visitas em seus relatórios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Configurações de visita do aplicativo móvel </p> </td> 
   <td colname="col2"> <p> Para conjuntos de relatórios que contenham dados gerados por aplicativos móveis por meio dos <a href="https://www.adobe.io/apis/cloudplatform/mobile.html" format="html" scope="external">SDKs do Adobe Mobile</a>, estão disponíveis configurações de visita adicionais. Essas configurações não são destrutivas e afetam somente as ocorrências que foram coletadas por meio dos SDKs móveis. Essas configurações não têm impacto nos dados coletados fora do SDK móvel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Impedir ocorrências em segundo plano de iniciar uma nova visita </p> </td> 
   <td colname="col2"> <p> As ocorrências em segundo plano são coletadas pelos SDKs móveis quando o aplicativo está em segundo plano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Iniciar uma nova visita em cada inicialização de aplicativo </p> </td> 
   <td colname="col2"> <p> Além do tempo limite de visita, você pode forçar o início de uma visita sempre que um evento de inicialização de aplicativo for gravado dos SDKs móveis, independentemente da janela de inatividade. Essa configuração afeta a métrica de visitas e o contêiner do segmento de visitas, bem como a lógica de expiração de visita nas eVars. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Iniciar nova visita com evento </p> </td> 
   <td colname="col2"> <p>Uma nova sessão começa quando um evento é acionado, independente do fato de uma sessão ter ultrapassado o tempo limite. A sessão recentemente criada inclui o evento que a iniciou. Além disso, é possível usar vários eventos para começar uma sessão e uma nova sessão é acionada se qualquer um desses eventos for observado nos dados. Esta configuração afetará a contagem de visitas, o contêiner de segmentação de visitas e a lógica de expiração de visitas nas eVars. </p> </td> 
  </tr> 
 </tbody> 
</table>

O Processamento de tempo do relatório não suporta todas as métricas e dimensões disponíveis nos relatórios tradicionais do Analytics. Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

Além disso, o Processamento de tempo do relatório somente processa os dados provenientes do intervalo de datas do relatório (referido como “janela de datas” abaixo). Isso significa que os valores de eVar configurados como “nunca expiram” para um visitante antes do intervalo de datas do relatório não persistem nas janelas de relatórios e não aparecem nos relatórios. Isso também significa que as medições de lealdade do cliente são baseadas exclusivamente nos dados presentes no intervalo de datas do relatório e não em todo o histórico antes do intervalo de datas do relatório.

Abaixo está uma lista de métricas e dimensões que atualmente não são suportadas ao usar Processamento de tempo do relatório:

<table id="table_127AFE8FA1BE4F2BAB3975CA12A2FA47"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da métrica/dimensão </th> 
   <th colname="col2" class="entry"> Observações de processamento de tempo do relatório </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Analytics para o Target </p> </td> 
   <td colname="col2"> <p> Não suportado atualmente. O suporte futuro está planejado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Métricas/dimensões reservadas do Analytics para Marketing Cloud </p> </td> 
   <td colname="col2"> <p> Não suportado atualmente. O suporte futuro está planejado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Métrica de acesso único </p> </td> 
   <td colname="col2"> <p> Não suportado agora nem no futuro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Vars de lista </p> </td> 
   <td colname="col2"> <p> Não suportado atualmente. O suporte futuro está planejado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de contador </p> </td> 
   <td colname="col2"> <p> Não suportado agora nem no futuro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Variáveis de canais de marketing </p> </td> 
   <td colname="col2"> <p> Não suportado atualmente. O suporte futuro está planejado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensão de dias desde a última compra </p> </td> 
   <td colname="col2"> <p> Devido à natureza da janela de datas do Processamento de tempo de relatório, essa dimensão não é suportada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensão de dias antes da primeira compra </p> </td> 
   <td colname="col2"> <p> Devido à natureza da janela de datas do Processamento de tempo de relatório, essa dimensão não é suportada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensão da frequência de retorno </p> </td> 
   <td colname="col2"> <p> Devido à natureza da janela de datas do Processamento de tempo de relatório, essa dimensão não é suportada. </p> <p> Uma abordagem alternativa usando a métrica de contagem de visitas em um segmento é possível, ou usando a métrica de visitas em um relatório de histograma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensão de dias desde a última visita </p> </td> 
   <td colname="col2"> <p> Devido à natureza da janela de datas do Processamento de tempo de relatório, essa dimensão não é suportada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensão da página de entrada original </p> </td> 
   <td colname="col2"> <p> Devido à natureza da janela de datas do Processamento de tempo de relatório, essa dimensão não é suportada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de alocação linear </p> </td> 
   <td colname="col2"> <p> Não suportado atualmente. O suporte futuro está planejado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensão do domínio de referência original </p> </td> 
   <td colname="col2"> <p> Não suportado atualmente. O suporte futuro está planejado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Número da visita </p> </td> 
   <td colname="col2"> <p> Devido à natureza da janela de datas do Processamento de tempo de relatório, essa métrica não é suportada. </p> <p> Para relatar a quantidade de visitantes novos e repetidos em aplicativos móveis, você pode usar uma métrica calculada, incluindo visitantes/visitas com a métrica de Instalação de aplicativo para identificar novos visitantes ou visitas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Fontes de dados de ID de transação </p> </td> 
   <td colname="col2"> <p> Não suportado atualmente. O suporte futuro está planejado. </p> </td> 
  </tr> 
 </tbody> 
</table>

Abaixo está uma lista das dimensões e métricas afetadas, dependendo das configurações de Processamento de tempo do relatório selecionadas:

<table id="table_491E48C55BC84917B4A8EACBF04C939F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da métrica/dimensão </th> 
   <th colname="col2" class="entry"> Observações de processamento de tempo do relatório </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Métrica de visitantes únicos </p> </td> 
   <td colname="col2"> <p> Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” estiver ativado, visitantes exclusivos não incluirão Visitantes que tiveram apenas ocorrências em segundo plano no intervalo de datas do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Visitas </p> </td> 
   <td colname="col2"> <p> As visitas refletem as configurações do conjunto de relatórios virtual, que podem ser diferentes do conjunto de relatório base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Eventos serializados com IDs de evento </p> </td> 
   <td colname="col2"> <p> Os eventos que usam Serialização de eventos com uma ID de evento são apenas desduplicados para eventos que ocorrem dentro do intervalo de datas do relatório para um visitante, em vez de em todas as datas ou visitantes globalmente, devido à janela de datas do Processamento de tempo de relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Compras/Receita/Pedidos/Unidades </p> </td> 
   <td colname="col2"> <p> Quando a ID de compra é usada, essas métricas são apenas desduplicadas para as IDs de compra duplicadas que ocorrem dentro do intervalo de datas do relatório para um visitante, em vez de em todas as datas ou visitantes globalmente, devido à janela de datas do Processamento de tempo de relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Rejeições/Taxa de rejeição </p> </td> 
   <td colname="col2"> <p> Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” estiver habilitado, as ocorrências em segundo plano que não forem seguidas por uma ocorrência em primeiro plano não serão consideradas uma rejeição e não contribuirão para a taxa de rejeição. Consulte <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Sessões sensíveis ao contexto</a> para obter mais detalhes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Segundos de tempo gasto por visita </p> </td> 
   <td colname="col2"> <p> Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” estiver ativado, apenas as visitas que incluírem ocorrências em primeiro plano contribuirão para essa métrica. Consulte <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Sessões sensíveis ao contexto</a> para obter mais detalhes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Tempo gasto por visita </p> </td> 
   <td colname="col2"> <p> Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” estiver ativado, apenas as visitas que incluírem ocorrências em primeiro plano contribuirão para essa métrica. Consulte <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Sessões sensíveis ao contexto</a> para obter mais detalhes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Entradas </p> </td> 
   <td colname="col2"> <p> Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” estiver ativado, somente as entradas das visitas que contêm uma ocorrência em primeiro plano serão consideradas. Consulte <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Sessões sensíveis ao contexto</a> para obter mais detalhes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de não merchandising/eVars reservadas </p> </td> 
   <td colname="col2"> <p> Os valores definidos em uma eVar persistem apenas se o valor tiver sido definido dentro do intervalo de datas do relatório devido à janela de data do processamento de tempo de relatório. </p> <p> Além disso, as expirações baseadas em tempo podem expirar uma hora antes ou depois se a persistência abranger uma mudança de horário de verão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de merchandising/eVars reservadas </p> </td> 
   <td colname="col2"> <p> Veja acima. </p> <p> Além disso, para a sintaxe de conversão, onde a vinculação é definida como “qualquer evento”, é usado “qualquer ocorrência” no lugar disso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensões de entrada e saída </p> </td> 
   <td colname="col2"> <p> Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” estiver ativado, somente entradas e saídas de visitas com ocorrências em primeiro plano aparecerão nesta dimensão. Consulte <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Sessões sensíveis ao contexto</a> para obter mais detalhes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Tipo de ocorrência </p> </td> 
   <td colname="col2"> <p> Essa dimensão especifica se uma ocorrência está em primeiro ou em segundo plano. </p> </td> 
  </tr> 
 </tbody> 
</table>

